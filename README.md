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

