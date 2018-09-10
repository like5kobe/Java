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
 
### 构造方法
 new+构造方法 创建一个对象
 初始化成员变量的值
 
### 访问修饰符protected
 
  子类与父类在同一包中：被声明为 protected 的变量能被同一个包中的任何其他类访问；
  子类与基类不在同一包中：那么在子类中，子类实例可以访问其从父类继承而来的 protected 方法，而不能通过父类实例来访问protected方法。
  同子类重写了父类的方法，可以在兄弟类中访问，否则与父类一样不能访问

### 非访问修饰符final

 被修饰的类不能被继承
 被修饰的方法可以被继承和重载，但不能被重写
 
### super
 
 子类在实例化的过程中隐式地调用的父类无参构造方法super()
 如果子类有显示地调用父类的有参构造方法，那无参的构造方法即不存在（在子类的构造方法第一行执行）
 
### Object类
  
  所有类的祖先，没有明确类继承于哪一个类，那就必然继承Object类  
  toString（）方法，默认是输出对象在内存中的地址，通过重写该方法，输出想要的值  
  equals()方法
     1. 在Object类中 比较的是两个对象是否指向同一块内存地址
     2. 在进行字符串比较时，由于String类重写了equals()方法，所以比较的是内存中存放的值是否相同  
     
     public boolean equals(Object anObject) {  
        if (this == anObject) {    
            return true;                  
        }   
        if (anObject instanceof String) {  
            String anotherString = (String)anObject;   
            int n = value.length;  
            if (n == anotherString.value.length) {  
                char v1[] = value;   
                char v2[] = anotherString.value;  
                int i = 0;    
                while (n-- != 0) {  
                    if (v1[i] != v2[i])     
                        return false;             
                    i++;          
                }        
                return true;   
            }    
        }  
        return false;  
         }  
    
