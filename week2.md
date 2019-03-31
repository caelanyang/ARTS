### Algorithm

题目名称：[AddTwoNumbers](https://leetcode.com/problems/add-two-numbers/)

解决方案：[AddTwoNumbers.py](https://github.com/caelanyang/LeetCode/blob/master/AddTwoNumbers.py)

### Review

原文文章：

[Introduction to Linked List](http://geeksquiz.com/linked-list-set-1-introduction/)

[Linked List vs Array](https://www.geeksforgeeks.org/linked-list-vs-array/)

[Linked List Insertion](https://www.geeksforgeeks.org/linked-list-set-2-inserting-a-node/)

翻译文章：[数据结构系列-链表](https://ds.jiacheng.site/section-2-1.html)


### Tip

openGL 实现 overlay 混合模式的 shader 算法：

```glsl
mediump vec4 base = texture2D(inputImageTexture, textureCoordinate);
     mediump vec4 overlay = texture2D(inputImageTexture2, textureCoordinate2);
     
     mediump float ra;
     if (2.0 * base.r < base.a) {
         ra = 2.0 * overlay.r * base.r + overlay.r * (1.0 - base.a) + base.r * (1.0 - overlay.a);
     } else {
         ra = overlay.a * base.a - 2.0 * (base.a - base.r) * (overlay.a - overlay.r) + overlay.r * (1.0 - base.a) + base.r * (1.0 - overlay.a);
     }
     
     mediump float ga;
     if (2.0 * base.g < base.a) {
         ga = 2.0 * overlay.g * base.g + overlay.g * (1.0 - base.a) + base.g * (1.0 - overlay.a);
     } else {
         ga = overlay.a * base.a - 2.0 * (base.a - base.g) * (overlay.a - overlay.g) + overlay.g * (1.0 - base.a) + base.g * (1.0 - overlay.a);
     }
     
     mediump float ba;
     if (2.0 * base.b < base.a) {
         ba = 2.0 * overlay.b * base.b + overlay.b * (1.0 - base.a) + base.b * (1.0 - overlay.a);
     } else {
         ba = overlay.a * base.a - 2.0 * (base.a - base.b) * (overlay.a - overlay.b) + overlay.b * (1.0 - base.a) + base.b * (1.0 - overlay.a);
     }
     
     gl_FragColor = vec4(ra, ga, ba, 1.0);
```

### Share 

[编程语言的类型](https://jiacheng.site/post/2019/03/31/type-of-programming-language/)
