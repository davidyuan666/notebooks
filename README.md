# TF 的几个概念
Session 
Graph 图计算

# Session管理计算资源
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
 
 


