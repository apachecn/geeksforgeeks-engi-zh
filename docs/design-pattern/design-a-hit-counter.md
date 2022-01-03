# 设计一个点击计数器

> 原文:[https://www.geeksforgeeks.org/design-a-hit-counter/](https://www.geeksforgeeks.org/design-a-hit-counter/)

设计一个点击计数器，计算过去 5 分钟内的点击次数。

**来源:** [微软面试体验](https://www.geeksforgeeks.org/microsoft-interview-experience-set-109-2-years-experienced/)

包括 Dropbox 在内的许多公司最近都在问“设计命中计数器”的问题，这个问题比看起来要难。它包括几个主题，如基本数据结构设计、各种优化、并发和分布式计数器。

它应该支持以下两个操作:**点击**和**获取点击**。

**命中(时间戳)**–显示给定时间戳的命中。

**getHits(时间戳)**–返回过去 5 分钟(300 秒)内收到的点击次数(来自 currentTimestamp)。

每个函数都接受一个时间戳参数(以秒为单位)，您可以假设对系统的调用是按时间顺序进行的(即时间戳是单调递增的)。您可以假设最早的时间戳从 1 开始。

示例:

```

HitCounter counter = new HitCounter();

// hit at timestamp 1.
counter.hit(1);

// hit at timestamp 2.
counter.hit(2);

// hit at timestamp 3.
counter.hit(3);

// get hits at timestamp 4, should return 3.
counter.getHits(4);

// hit at timestamp 300.
counter.hit(300);

// get hits at timestamp 300, should return 4.
counter.getHits(300);

// get hits at timestamp 301, should return 3.
counter.getHits(301);

```

**问 In:** 微软、亚马逊、Dropbox 等多家公司。

**1。简单解决方案(强力方法):**

我们可以用一个向量来存储所有的点击量。这两个函数是自我解释的。

```
vector<int> v;

/* Record a hit.
   @param timestamp - The current timestamp (in 
                      seconds granularity).  */

void hit(int timestamp)
{
    v.push_back(timestamp);
}

// Time Complexity : O(1)

/** Return the number of hits in the past 5 minutes.
    @param timestamp - The current timestamp (in
    seconds granularity). */
int getHits(int timestamp)
{
    int i, j;
    for (i = 0; i < v.size(); ++i) {
        if (v[i] > timestamp - 300) {
            break;
        }
    }
    return v.size() - i;
}

// Time Complexity : O(n)
```

**2。空间优化解决方案:**

我们可以使用队列来存储命中，并删除队列中无用的条目。它会节省我们的空间。
我们正在从队列中删除多余的元素。

```
queue<int> q;

/** Record a hit.
    @param timestamp - The current timestamp 
                   (in seconds granularity). */
void hit(int timestamp)
{
    q.push(timestamp);
}

// Time Complexity : O(1)

/** Return the number of hits in the past 5 minutes.
   @param timestamp - The current timestamp (in seconds
   granularity). */
int getHits(int timestamp)
{
    while (!q.empty() && timestamp - q.front() >= 300) {
        q.pop();
    }
    return q.size();
}
// Time Complexity : O(n)
```

**3。最优化的解决方案:**

如果数据是无序的，并且几次点击都带有相同的时间戳，那会怎样。

由于队列方法在没有有序数据的情况下无法工作，所以这次使用数组来存储每个时间单位中的命中数。

如果我们在过去 5 分钟内以 300 秒的粒度跟踪命中，请创建 2 个大小为 300 的阵列。
int[]hits = new int[300]；

TiMer[]times = new TiMer[300]；//最后一次计数命中的时间戳
给定一个传入，将其时间戳修改 300，以查看它在命中数组中的位置。

int idx =时间戳% 300；= >点击[idx]保持在这一秒钟内发生的点击次数

但是在我们将 idx 的命中次数增加 1 之前，时间戳实际上属于[idx]正在跟踪的第二次命中。
时间戳[i]存储上次计数命中的时间戳。
如果时间戳[i] >为时间戳，则应该丢弃该命中，因为它不是在过去 5 分钟内发生的。
如果时间戳[i] ==时间戳，那么命中数[i]增加 1。
如果时间戳[I]current time–300。

```
vector<int> times, hits;

times.resize(300);
hits.resize(300);

/** Record a hit.
   @param timestamp - The current timestamp
   (in seconds granularity). */
void hit(int timestamp)
{
    int idx = timestamp % 300;
    if (times[idx] != timestamp) {
        times[idx] = timestamp;
        hits[idx] = 1;
    }
    else {
        ++hits[idx];
    }
}

// Time Complexity : O(1)

/** Return the number of hits in the past 5 minutes.
    @param timestamp - The current timestamp (in 
    seconds granularity). */
int getHits(int timestamp)
{
    int res = 0;
    for (int i = 0; i < 300; ++i) {
        if (timestamp - times[i] < 300) {
            res += hits[i];
        }
    }
    return res;
}
// Time Complexity : O(300) == O(1)
```

**如何处理并发请求？**

当两个请求同时更新列表时，可能会出现竞争情况。有可能最先更新列表的请求最终可能不会被包括在内。

最常见的解决方案是使用锁来保护列表。每当有人想要更新列表时(通过添加新元素或删除尾部)，容器上会被锁定。操作完成后，列表将被解锁。

当您没有大量请求或者性能不是问题时，这非常有效。在某些时候，放置锁的成本很高，当并发请求太多时，锁可能会阻塞系统，成为性能瓶颈。

**分发计数器**

当单台机器流量过大，性能成为问题时，这是考虑分布式解决方案的最佳时机。分布式系统通过将系统扩展到多个节点显著降低了单台机器的负担，但同时增加了复杂性。

假设我们将访问请求平均分配给多台机器。我想先强调一下平均分配的重要性。如果特定的机器获得的流量比其他机器多得多，系统就不能充分利用，在设计系统时考虑这一点非常重要。在我们的例子中，我们可以获得用户电子邮件的散列并通过散列进行分发(直接使用电子邮件不是一个好主意，因为某些字母可能比其他字母出现得更频繁)。

为了计算数量，每台机器都独立工作，从过去的一分钟开始计算自己的用户。当我们请求全局号码时，我们只需要将所有计数器加在一起。

**参考文献:**我原本是在[这里](https://leetcode.com/discuss/interview-question/178662/Design-a-Hit-Counter/)发表的。
https://aonecode.com/getArticle/211