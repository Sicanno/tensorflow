# tensorflow
learning
tensorflow初学tips--基于莫烦视频
----
### 1.对tensorflow有了初步认识。 
使用图graph来表示计算任务，会话session来运行任务，即任务的`建立`和`运行`清楚的分为两个模块，对于设计者来说很方便。 <br>
### 2.tensorflow的基本语法知识。
对于变量variable进行创建和命名：state = tf.variable(0,name=’counter’)<br>
* 初始化init =tf.global_variables_initializer(),后面一定要sess.run(init)才算激活。                      
### 3.placehoder的使用，类似于变量的东西，但是placeholder是需要调用的时候从外界引入数字。
 Print(sess.run(output,feed_dict={input1:[4.],input2:[2.]}))  [从这里run的时候才把placeholder的值表示出来]
* 也就是说，placeholder这个变量不需要初始化，而是自己赋值。
### 4.建立相应的激励函数和层。
    Def add_layer(inputs,in_size,out_size,activation_funtion=???) 
      Weights=tf.Variable(tf.random_normal(in_size,out_size))
      Biases=tf.Variable(tf.zeros([1,out_size])+0.1)
      Wx_plus_b=tf.matmul(inputs,Weights)+biases
       If activation_function is None:
         Outputs=Wx_plus_b
            Else:<br>
             Outputs=activation_funtion(Wx_plus_b)
             Return output
### 5.tensorboard的视图化效果。
将神经网络以图表的形式表现出来。<br>
但是具体实施过程中最后copy网址时，“http://home-lyk:6006” 找不到网址，报错404.<br>
尝试了"http://localhost:6006” 等也没有解决。
