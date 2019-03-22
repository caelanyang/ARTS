
Tip: OpenGL 从内存往GPU加载纹理的时候，对于某些宽高像素字节数不是4的整数倍的图片，图片的显示会出现问题，比如倾斜或拼接。

解决方法：

```c
glPixelStorei(GL_UNPACK_ALIGNMENT, 1);
glTexImage2D(, , , , , , , , imageData);
glPixelStorei(GL_UNPACK_ALIGNMENT, 4);

```
    
原因：openGL 纹理从内存传输到GPU的过程称为 unpack，为了提升效率，默认情况下 OpenGL 会四个字节四个字姐的读取传输数据，但是
如果图片的宽的像素字节数不是四的倍数，就会导致第二行的数据被读到第一行，数据最终会发生错乱，图片就回出现倾斜或拼接的问题。使用
以上代码让 OpenGL 一个字节一个字节来读取，读完后再设置回默认值。对于特殊的图片读取的效率会下降，但是能避免出现问题。
