## 手工编译java程序
 1. javac HelloWorld.java  编译成字节码
 2. java HelloWorld   解释执行
 3. java -c HelloWorld 查看字节码文件
 3. javap -verbose HelloWolrd 虚拟机装入的类的信息
 
## 数组
  数组在内存中的分配，在堆中开辟内存空间，栈中有一个指向堆的引用
  
 ## stringBuilder和stringBuffer  
   线程安全性的问题 Builder源码函数getChar()里没有同步锁（线程不安全）
 
## 变量的分类
 类变量（静态变量):在类实例化之前就可以被访问 
 成员变量：定义时可以不用初始化，通过创建对象实例时的构造方法进行初始化操作
 局部变量：必须进行显示的初始化，否则编译错误
