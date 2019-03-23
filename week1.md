## Algorithm


题目：[TwoSum](https://leetcode.com/problems/two-sum/)

解答：[Solution](https://github.com/caelanyang/LeetCode/blob/master/TwoSum.py)


## Review

原文文章：[Optimization tricks in Python: lists and tuples
](https://rushter.com/blog/python-lists-and-tuples/)
翻译文章：[Python 内部的优化技巧: list 和 tuple](https://jiacheng.site/post/2019/03/23/python-list-tuple/)

点评：文章分析了 Python 两个列表类型 tuple 与 list 的异同，并指出尽管 tuple 在编程中没有 list 使用的广泛，但是由于其不可变的特性，其在 Python 内部还是有大量使用的。并且，Python内部在内存分配与重用方面，针对两者各自特点都有一定的优化，最后谈论了 list 是如何 resize 的。

## Tip

OpenGL 从内存往 GPU 加载纹理的时候，对于某些宽高像素字节数不是4的整数倍的图片，图片的显示会出现问题，比如倾斜或拼接。

解决方法：

```c
glPixelStorei(GL_UNPACK_ALIGNMENT, 1);
glTexImage2D(, , , , , , , , imageData);
glPixelStorei(GL_UNPACK_ALIGNMENT, 4);

```
    
原因：OpenGL 纹理从内存传输到GPU的过程称为 unpack，为了提升效率，默认情况下 OpenGL 会四个字节四个字姐的读取传输数据，但是
如果图片的宽的像素字节数不是四的倍数，就会导致第二行的数据被读到第一行，数据最终会发生错乱，图片就会出现倾斜或拼接的问题。使用
以上代码让 OpenGL 一个字节一个字节来读取，读完后再设置回默认值。对于特殊的图片读取的效率会下降，但是能避免出现问题。


## Share

文章分享：[控制反转漫谈](https://jiacheng.site/post/2019/03/23/about-the-ioc/)
