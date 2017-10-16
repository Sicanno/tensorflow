# tensorflow
learning
tensorflow初学总结--基于莫烦视频
----
1.对tensorflow有了初步认识。
----
使用图graph来表示计算任务，会话session来运行任务，即任务的建立和运行清楚的分为两个模块，对于设计者来说很方便。<br>
2.tensorflow的基本语法知识。
---------
对于变量variable进行创建和命名：state = tf.variable(0,name=’counter’)
初始化init =tf.global_variables_initializer(),后面一定要sess.run(init)才算激活
启动默认图的两种方式：(1)<br>
                      sess =tf.Session()<br>
                      。。。<br>
                      sess.close()<br>
                      
                   (2)<br>
                      with tf.Session() as sess:<br>
                          result =sess.run([product])<br>
                          print result<br>
                      
3.placehoder的使用，类似于变量的东西，但是placeholder是需要调用的时候从外界引入数字。
-------
  input 1=tf.placeholder(tf.float32)<br>
  Input2=tf.placeholder(tf.float32)<br>
  Output =tf.multiply(input1,input2)【windows的mul要写成multiply]<br>
  With tf.Session()as sess:<br>
 Print(sess.run(output,feed_dict={input1:[4.],input2:[2.]}))[从这里run的时候才把placeholder的值表示出来]<br>
*也就是说，placeholder这个变量不需要初始化，而是自己赋值。<br>
4.建立相应的激励函数和层。
-----
  Def add_layer(inputs,in_size,out_size,activation_funtion=???)<br>
   Weights=tf.Variable(tf.random_normal(in_size,out_size))<br>
    Biases=tf.Variable(tf.zeros([1,out_size])+0.1)<br>
     Wx_plus_b=tf.matmul(inputs,Weights)+biases<br>
       If activation_function is None:<br>
          Outputs=Wx_plus_b<br>
              Else:<br>
               Outputs=activation_funtion(Wx_plus_b)<br>
                   Return output<br>
5.tensorboard的视图化效果。
-----
可以将定义的输入层、输出层，loss，权重和偏置转化为一个graph，也就是可以将神经网络以图表的形式表现出来。<br>
但是具体实施过程中最后copy网址时，“http://home-lyk:6006” 找不到网址，报错404，<br>
尝试了http://localhost:6006”等也没有解决。<br>
