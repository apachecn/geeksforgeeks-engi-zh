# 像四方一样设计城市导向系统

> 原文:[https://www . geeksforgeeks . org/design-scalable-system-like-four square/](https://www.geeksforgeeks.org/design-scalable-system-like-foursquare/)

**城市指南服务的目的**

城市指南将是允许用户搜索和找到靠近用户位置的服务。你可以认为这项服务将类似于 Foursquare。在开始设计系统之前，定义系统的用途会很好。也就是说，在设计过程之前，需求应该是清晰明确的。城市指南服务的目的是根据用户的位置向他们呈现位置。你可以找到任何地方，如餐馆、剧院、电影院等。建议将从附近位置开始到远处位置，但系统也将支持基于专用位置搜索地点。

**要求和系统边界**

如果你想设计一个系统，你必须首先定义需求和系统边界。在开始设计之前，您将拥有服务设计文档，并从头开始定义所有需求。由于城市指南服务的目的是创建架构良好的城市指南服务，它必须能够根据您的搜索查询和位置推荐地点。所以我们的系统会支持这些功能；

–用户必须能够创建帐户。
–用户必须能够登录系统。
–用户必须能够从系统中注销。
-用户登录或注销时，必须能够搜索餐馆、剧院、咖啡馆、电影院等场所。
–用户必须能够在登录后向地点添加评论。
-用户必须能够喜欢或不喜欢的地方。
–用户必须能够添加一个新位置，并且系统管理员应该对其进行审查。
–用户必须能够向地点添加图片。
–如果用户拥有权限，他们必须能够更新或删除位置。

–系统必须能够建议从最相关到不太相关的地方。
-系统必须能够根据用户的查询和位置建议地点。
–系统必须能够根据人气和用户评论建议地点。
-系统必须能够监控。
–系统必须能够通过发送推送通知来推荐新地点。
-系统应高度可用。
–系统应高度可靠。
–系统应耐用。
–系统应具有弹性。
–系统应具有极高的成本和性能效率。

基本上系统应该支持 5 个重要支柱，它们是:

–可用性
–可靠性
–弹性
–耐用性
–性价比

这些是我们应该一起考虑的支柱，因为它们是相互耦合的。简而言之，可用性意味着系统应该始终可用。可靠性意味着系统应该按预期工作。弹性意味着如果出现任何问题，系统将如何以及何时自我恢复。在我们删除之前，持久性是系统每个部分都应该存在的支柱。性价比也是一个重要的话题，它将基本上关系到在成本效率下使用服务。可以举例说明，如果系统将建立在 AWS 上，并且足以使用 t2 微 EC2 实例，就没有任何理由使用更大的 EC2 实例并支付额外的费用。

请注意，每个系统都将日益增长，因此系统在未来会变得更加复杂(就像 5 年后一样)，但重要的是，如果您有明确定义的需求和结构，就不会有太多的工作向您的系统添加新组件。

当定义系统边界和功能需求时，需要考虑云或承诺选项。云服务有很多优势，如成本效益、高速性能、备份解决方案、维护、无限存储容量等等..你的系统可以；

–100%承诺(您自己的数据中心/服务器)
–100%云(AWS、Google Cloud、Azure)
–承诺和云的混合(您可以在迁移过程中同时拥有两者)

容量估计首先很重要(尤其是对于承诺服务)，因此您可以估计需要多少台服务器，或者如何分离您的服务以及您将使用哪个数据库？还要注意的是，您的系统将是读重的，读流量将多于写流量。

让我们假设 5 年后城市指南系统将有 1000 万个位置，每天的查询次数将达到 10000。您可以估计系统每年都会增长，并且可以估计缓冲区。这意味着你将保留 1000 万个地方的元数据和图片信息。如果我们假设照片平均大小为 25 KB，每个地方平均有 5 张照片；

容量大约等于 1000 万* 5 * 25 KB +(用户元数据信息)+(位置元数据信息)。建议为数据提供复制和备份解决方案，以防止数据丢失，这样数据将比我们估计的大大约 3 倍。

此计算只是如何定义系统容量的一个简单示例，我们不会计算每日下载/上传容量和元数据容量，但您应该考虑此计算(以及每日读/写容量估计)以进行服务/数据库扩展。

**API ESTIMATION**
城市指南服务可以同时支持 REST 或 SOAP 策略。你也可以想想 GRPC 这是来自谷歌的新战略，GRPC 最大的优势是使用更小的带宽和资源。如果我们继续使用 REST，将有四个主要的 API 来设计系统。

–AddPlace(api _ dev _ key，名称，描述，经度，纬度，类别，图片):这个 API 返回带有新添加的地点信息的 HTTP 响应。(如果成功，则接受 202)

–delete place(API _ dev _ key，placeID):它可以根据您的响应返回 HTTP 响应 200 (OK)或 204 (No Content)。

–UpdatePlace(API _ dev _ key，updatePlaceRequest):updatePlaceRequest 将有一个 placeID 来知道我们正在更新哪个位置。

–GetPlace(search _ query，userlocation，categoryfilter = null，sortby = ' distance | | popularity '，page = 1，distanceRadius = 5，maximum_return_count = 20):返回带有位置元数据的 JSON。结果将根据用户查询和位置进行排序。

**设计和数据库模式**

保存数据将分为两部分。第一个将涉及保持静态内容，如位置图片。如果我们正在构建我们的服务 AWS，我们可以使用 S3 来保存静态内容，在 S3 前面，我们可以使用 Cloudfront 作为 CDN。Cloudfront 将充当缓存，它将帮助系统快速返回响应。如果您正在按照承诺构建您的系统，那么您需要有映像存储。S3 是一个 AWS 提供，它将帮助我们的系统以安全的方式保持静态媒体内容。对于元数据(地点、图片、用户)，我们可以使用 SQL 和 NoSQL。NoSQL 是轻松扩展系统的最佳方式。另一方面，如果我们考虑到 SQL 的关系和约束，扩展 SQL 数据库是非常困难的。

–**地点:** ID，AddedBy，Name，Lat，Lng，Category，Description，AddedDate，LikeCount，DisLike count
–**用户:** ID，用户名，密码，电子邮件，注册日期，lastloginde
–**评论:** ID，喜欢，不喜欢，评论，评论日期
–**用户地点评论:** ID，评论，用户 ID，地点 ID

8 个字节将足以保留位置标识和用户标识。此外，我们将保持经度和纬度为 8 字节。数据将根据 placeID、lat 和 lng 进行索引。我们将根据地点位置和用户位置向地点表发送查询。所以查询会评估；

(地点经度在用户经度–半径和用户经度+半径之间，地点纬度在用户纬度–半径和用户纬度+半径之间)

这种方式不是最佳方式，因为我们需要计算纬度和经度。我们可以使用网格来解决性能问题。我们可以把整个世界分成更小的网格。这确保了我们只能处理网格的邻居。由于这种方法，我们只关注用户位置网格及其相邻网格。地图是使用网格的最佳选择。关键是 gridID。值是这个网格中的所有位置。所以查询会评估；

(用户纬度–半径和用户纬度+半径和网格之间的纬度所在的位置(相邻网格)

请注意，我们当然会有更多数据库表，这些只是示例。遵循数据库设计过程的规范化规则会很好。

我们也可以根据来划分系统；

–userid
–regional id
–location id

使用用户标识和区域标识会产生分发问题。一些地区可能比其他地区有更多的位置，在这种情况下，系统将不会均匀分布。我们可以根据 locationID 和 regionID 进行分区。

**系统设计考虑因素**

如果我们在设计一个系统，我们需要的基本概念是；

–客户端
–服务
–网络服务器
–应用服务器
–媒体文件存储
–数据库
–缓存
–复制
–冗余
–负载平衡
–分片

如上所述，复制过程是一个提供高可用性、高可靠性和实时体验的宝贵过程。复制和备份是我们之前提到的两个重要概念。复制是处理服务或服务器故障的一个非常重要的概念。复制可以应用于数据库服务器、网络服务器、应用服务器、媒体存储等..事实上，我们可以复制系统的所有部分。(像 Route53 这样的一些 AWS 服务，它们本身是高度可用的，所以您不需要考虑 Route53、负载平衡器等的复制..)请注意，复制还有助于系统缩短响应时间。您可以想象，如果我们将传入的请求分成更多的资源，而不是一个资源，系统可以轻松地满足所有传入的请求。此外，每个资源的副本的最佳数量为 3 个或更多。您可以通过将数据保存在不同的可用性区域或 AWS 中的不同区域来提供冗余。我们可以将相同的数据保存在三个不同的资源上，由于这个过程，如果一台服务器死亡，系统会自动继续复制工作。复制的另一个优点是系统可以在系统更新时继续运行。在复制过程中，主服务器将负责读写操作；而从机负责读取操作。

负载平衡是指在一组服务和服务器之间分配请求。当我们谈到复制和分片时，传入的请求必须被定向，这是由负载平衡器完成的。我们可以使用循环方法来重定向传入的请求，但是在这种情况下可能会有问题。循环停止向失效的服务器发送请求，但是循环不能停止向流量大的服务器发送请求。我们可以准备智能循环算法来解决这个问题。此外，我们可以使用一致哈希来重定向传入的请求。一致哈希确保系统变得更加均匀分布。

使用负载平衡器进行分片的可能问题是，当系统死亡时，我们如何重建系统。可能的方法是暴力。这种方法很慢，因为我们需要从一开始就重建整个系统。我们可以通过使用反向索引方法来消除这个问题。我们可以有另一个索引服务器来保存所有关于反向索引的信息。反向索引映射所有位置。我们需要建立一个地图，关键是服务器标识和值是所有的地方。

对于缓存策略，我们可以通过使用缓存服务器来使用全局缓存机制。我们可以使用 Redis 或 memcache，但是缓存策略最重要的部分是如何提供缓存回收。如果我们使用全局缓存服务器，我们将保证每个用户在缓存中看到相同的数据，但是如果我们使用全局缓存服务器，会有时间延迟。作为缓存策略，我们可以使用 LRU(最近最少使用)算法。

对于媒体文件缓存，正如我们之前提到的，我们将使用 CDN。CDN 位于不同的边缘位置，因此响应时间比直接从 AWS S3 获取媒体内容要短。

我们可以有各种排名机制，最受欢迎的，最相关的，最新的等等……正如你所知，我们可以有很多服务器，我们需要从这些服务器获取数据。由于这个原因，我们需要聚合函数来组合所有这些数据，以获得最理想的解决方案。

**系统的基本编码**

```
// Java Program to illustrate the Design
public enum UserStatus{
    LOGIN,
    LOGOUT
    ...
}

public enum ReviewStatus {
    LIKE,
    DISLIKE
}

public enum LocationStatus{
    PUBLIC,
    PRIVATE,
    ...
}

public enum LocationCategory {
    EVENT,
    EDUCATION,
    FOOD,
    HEALTH,
    ENTERTAINTMENT,
    ....
}

public class AddressDetails {
    private String street;
    private String city;
    private String country;
    private double latitude;
    private double longitude;
    ...
}

public class AccountDetails {
    private Date createdTime;
    private AccountStatus status;
    private boolean updateAccountStatus(AccountStatus accountStatus);
    ...
}

public class Comment {
    private Integer id;
    private User addedBy;
    private Date addedDate;
    private String comment;

    public boolean updateComment(String comment);
    ...
}

public class Location {
      private Integer id;
    private User createdBy;
    private LocationCategory locationCategory;
    private LocationStatus locationStatus;

    private HashSet<Integer> pictures;
    private HashSet<Integer> userLikes;
    private HashSet<Integer> userDisLikes;
    private HashSet<Integer> userComments;
    ...
}

public class User {
    private UserStatus userStatus;
    private Double latitude;
    private Double longitude;
    private AccountDetails accountDetails;
    private UserRelations userRelations;

    public List<User> searchLocation(query);
    ...
}

public LoginUser extends Users{
    private int id;
    private String password;
    private String nickname;
    private String email;

    private boolean updatePassword();
    public boolean addPlace(Place place);
    public boolean updatePlace(Place place);
    public boolean addComment(Integer placeID, String comment);
    public boolean reviewPlace(Integer placeID, ReviewStatus status);
    ....
}
```

**参考:https://developer.foursquare.com/docs/resources/**

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。