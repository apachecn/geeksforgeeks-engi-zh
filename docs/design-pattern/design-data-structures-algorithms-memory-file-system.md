# 设计内存文件系统的数据结构和算法

> 原文:[https://www . geesforgeks . org/design-data-structures-algorithms-memory-file-system/](https://www.geeksforgeeks.org/design-data-structures-algorithms-memory-file-system/)

解释用于设计内存文件系统的数据结构和算法。尽可能在代码逻辑中举例说明。

**问于:亚马逊**

最简单的文件系统由文件和目录组成。每个目录包含一组文件和目录。由于文件和目录共享如此多的特性，我们已经实现了它们，使得它们继承自同一个类，Entry。

**用 Java 实现主逻辑**

```
// Entry is superclass for both File and Directory
public abstract class Entry
{
    protected Directory parent;
    protected long created;
    protected long lastUpdated;
    protected long lastAccessed;
    protected String name;

    public Entry(String n, Directory p)
    {
        name = n;
        parent = p;
        created= System.currentTimeMillis();
        lastUpdated = System.currentTimeMillis();
        lastAccessed = System.currentTimeMillis();
    }

    public boolean delete()
    {
        if (parent == null)
            return false;
        return parent.deleteEntry(this);
    }

    public abstract int size();

    /* Getters and setters. */
    public long getcreationTime()
    {
        return created;
    }
    public long getLastUpdatedTime()
    {
        return lastUpdated;
    }
    public long getLastAccessedTime()
    {
        return lastAccessed;
    }
    public void changeName(String n)
    {
        name = n;
    }
    public String getName()
    {
        return name;
    }
}

// A class to represent a File (Inherits
// from Entry)
public class File extends Entry
{
    private String content;
    private int size;

    public File(String n, Directory p, int sz)
    {
        super(n, p);
        size = sz;
    }
    public int size()
    {
        return size;
    }
    public String getContents()
    {
        return content;
    }
    public void setContents(String c)
    {
        content = c;
    }
}

// A class to represent a Directory (Inherits
// from Entry)
public class Directory extends Entry
{
    protected Arraylist<Entry> contents;

    public Directory(String n, Directory p)
    {
        super(n, p);
        contents = new Arraylist<Entry>();
    }
    public int size()
    {
        int size = 0;
        for (Entry e : contents)
            size += e.size();

        return size;
    }
    public int numberOfFiles()
    {
        int count = 0;
        for (Entry e : contents)
        {
            if (e instanceof Directory)
            {
                count++; // Directory counts as a file
                Directory d = (Directory) e;
                count += d. numberOfFiles ();
            }
            else if (e instanceof File)            
                count++;            
        }
        return count;
    }

    public boolean deleteEntry(Entry entry)
    {
        return contents.remove(entry);
    }

    public void addEntry(Entry entry)
    {
        contents.add(entry);
    }

    protected ArrayList<Entry> getContents()
    {
        return contents;
    }
}
```

或者，我们可以实现目录，使其包含单独的文件和子目录列表。这使得 nurnberOfFiles()方法稍微干净一点，因为它不需要使用 instanceof 运算符，但是它确实禁止我们按照日期或名称对文件和目录进行干净的排序。

对于数据块分配，我们可以使用位掩码向量和线性搜索(参见“实用文件系统设计”)或 B+树(参见参考资料或维基百科)。

**参考文献:**
[【https://www.careercup.com/question?id=13618661】](https://www.careercup.com/question?id=13618661)
[https://stackoverflow . com/questions/14126575/数据结构-用于构建文件系统](https://stackoverflow.com/questions/14126575/data-structures-used-to-build-file-systems)

本文由 Somesh Awasthi 先生供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。