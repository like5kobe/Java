## 手工编译java程序
 1. javac HelloWorld.java  编译成字节码
 2. java HelloWorld   解释执行
 3. javap -verbose HelloWolrd 查看字节码文件
 
## 数组
  数组在内存中的分配，在堆中开辟内存空间，栈中有一个指向堆的引用
  
 ## stringBuilder和stringBuffer  
   线程安全性的问题 Builder源码函数getChar()里没有同步锁（线程不安全）
