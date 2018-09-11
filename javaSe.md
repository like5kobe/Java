### 手工编译java程序
 1. javac HelloWorld.java  编译成字节码
 2. java HelloWorld   解释执行
 3. java -c HelloWorld 查看字节码文件
 3. javap -verbose HelloWolrd 虚拟机装入的类的信息
 
### 数组
  数组在内存中的分配，在堆中开辟内存空间，栈中有一个指向堆的引用
  
### stringBuilder和stringBuffer  
   线程安全性的问题 Builder源码函数getChar()里没有同步锁（线程不安全）
 
### 变量的分类
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
 修饰变量的引用不可变，引用对象可以改变
 
 
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
    
  ### 多态
    
     由于虚拟机在编译期间只检查类型是否存在，不够严格，在运行期间需要使用对象的方法，如果父类对象不存在调用的方法，就会报错
    
  ### 接口
  
    java类是单继承，接口可以多继承  
    接口不可以实例化，使用匿名类直接new接口，实际上编译器隐式地实现了该接口，然后再实例化
    
  ### 集合框架
   1. 集合框架（collections framework）
在计算机领域，集合一般是指对象的集合，框架则是指有明确关系的集合的集合，其实这些新名词都是一个统称，归根结底集合也是一个类，只不过是一个可以储存并且处理多个其他对象的类，而框架就是类之间的整体关系。这是一种存储思想，其实说白了，可以把一个集合看成一个微型数据库，操作不外乎“增删改查”四种操作。

   2. 两大基类Collection与Map
在集合框架的类继承体系中，最顶层有两个接口：Collection表示一组纯数据，Map表示一组key-value对,Key和value都是对象（我们把基本数据类型也看成是对象），一般继承自Collection或Map的集合类，会提供两个“标准”的构造函数：
     2.1 没有参数的构造函数，创建一个空的集合类

     2.2 有一个类型与基类（Collection或Map）相同的构造函数，创建一个与给定参数具有相同元素的新集合类

因为接口中不能包含构造函数，所以上面这两个构造函数的约定并不是强制性的，但是在目前的集合框架中，所有继承自Collection或Map的子类都遵循这一约定。  

1. List Set都是继承Collection的接口，List元素有放入顺序，元素可以重复；Set元素放入无顺序，重复元素被覆盖
 Set：检索元素效率低下，删除和插入效率高，插入和删除不会引起元素位置改变。  
 List：和数组类似，List可以动态增长，查找元素效率高，插入删除元素效率低，因为会引起其他元素位置改变。   

2. Map单独存在，是一个适合存储键值对的集合。


    
     
     
