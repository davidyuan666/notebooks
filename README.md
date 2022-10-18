# TF 的几个概念
Session 
Graph 图计算

# Session管理计算资源
```
print(定义tensor)
v1 = tf.constant(value=1,name='v1',shape=(1,2),dtype=tf.float32)
v2 = tf.constant(value=2,name='v1',shape=(1,2),dtype=tf.float32)
print(定义计算)
add = v1 + v2
print(创建session)
with tf.Session() as sess:
    # 执行计算
    sess.run(add)
    
 通过session来管理TF资源
 
```

# Graph 管理计算电路

```
# 新增计算图
new_graph = tf.Graph()
with new_graph.as_default():
    # 在新增的计算图中进行计算
    v1 = tf.constant(value=3, name='v1', shape=(1, 2), dtype=tf.float32)
    v2 = tf.constant(value=4, name='v2', shape=(1, 2), dtype=tf.float32)
    add = v1 + v2
#  通过graph=new_graph指定Session所在的计算图
with tf.Session(graph=new_graph) as sess:
    sess.run(tf.global_variables_initializer())
    print(sess.run(add))
# 在默认计算图中进行计算
v1 = tf.constant(value=1,name='v1',shape=(1,2),dtype=tf.float32)
v2 = tf.constant(value=2,name='v2',shape=(1,2),dtype=tf.float32)
add = v1 + v2
# 通过graph=tf.get_default_graph()指定Session所在默认的计算图
with tf.Session(graph=tf.get_default_graph()) as sess:
    sess.run(tf.global_variables_initializer())
    print(sess.run(add))

# 输出：[[7. 7.]]
# 输出：[[3. 3.]]

```

# Tensor 概念
Tensor表示一个变量，是基本的计算单元，其中每一个tensor包含name, value, type 和 dimension信息，将其理解成object



# 使用ghostScript对PDF文档进行修复
由于pdf是由postscript进行渲染的，那么通过ghostscript工具可以对pdf文档进行编辑处理，包括转变为image等操作
ImageMagick是第三方的图片处理软件，功能要比GD强大。建议两者都安装，并不冲突。
imagick是php的一个扩展模块，它调用ImageMagick提供的API来进行图片的操作。
Ghostscript是一套建基于Adobe、PostScript及可移植文档格式（PDF）的页面描述语言等而编译成的免费软件。
Ghostscript最初是以商业软件形式在PC市场上发售，并称之为“GoScript”。但由于速度太慢（半小时一版A4），销量极差。后来有心人买下了版权，并改在Linux上开发，成为了今日的Ghostscript。
已经从Linux版本移植到其他操作系统，如其他Unix、Mac OS X、VMS、Windows、OS/2和Mac OS classic。
ImageMagick无法直接实现pdf文档到图片的转换，需要借助于gostscript软件包

参数说明\n：
    "-dQUIET",    安静的意思，指代执行过程中尽可能少的输出日志等信息。（也可以简写为“-q”）\n
    "-dNOSAFER",    通过命令行运行 \n
    "-dBATCH",    执行到最后一页后退出 \n
    "-dNOPAUSE",    每一页转换之间没有停顿 \n
    "-dNOPROMPT",    没有相关提示            \n           
    "-dFirstPage=1",    从第几页开始 \n
    "-dLastPage=5",     到第几页结束  \n
    "-sDEVICE=pngalpha",    转换输出的文件类型装置，默认值为x11alpha \n
    "-g720x1280",    图片像素(-g<width>x<height>)，一般不指定，使用默认输出 \n
    "-r300",    图片分辨率（即图片解析度为300dpi），默认值好像是72(未测试证实) \n
    "-sOutputFile=/opt/shanhy/error1png/%d.png",    图片输出路径，使用%d或%ld输出页数 \n

    
