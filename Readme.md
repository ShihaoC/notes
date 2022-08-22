# 大数据

## 八大数据类型

```java
数据类型：8大基本数据类型和引用类型
byte(Byte)、short(Short)、int(Integer)、long(Long)、float(Float)、double(Double)、char(Char)、boolean(Boolean)
引用类型：String、数组、对象
```

## 运算符

```java
算数运算符：+ - * / %
赋值运算符：= += -= *= /= %=
关系运算符：==(equals()方法) != > >= < <= !=
逻辑运算符： && || !
三目运算符：条件？为true的结果：false的结果
```

## 选择结构

```java
1、if选择结构
2、else if:适用于区间判断
3、switch:适用于等值判断
```

## 循环

```java
循环：重复完成同一事
      while：while(循环条件){循环操作}特点：先判断再执行
      do-while：do{循环操作}while(循环条件);先执行一遍再判断条件
      for：for(循环变量，循环条件，更新循环变量){循环操作} 先判断再执行，适用于循环次数固定的情况
```

## 二重循环特点

~~~java
	for(int i = 0;i<10;i++){
        for(int j = 0;j<10;j++){
            
        }
    }
特点：外层循环执行一次，内层循环执行一次
~~~

## 数组的定义方式【三种】

```java
1、数据类型[] 数组名 = new 数据类型[数组长度]
2、数据类型[] 数组名 = new 数据类型[]{值，值}
2、数据类型[] 数组名 = {值，值}
```

## 遍历数组方式

```java
//遍历数组
for(数据类型 变量名:数组名){
    
}
```

## 包（Package）

```java
包的作用：1、解决多个类重名问题；2、便于对类的管理
包的命名规范：
    1、全部小写字母，不能已圆点开头或结尾
    2、组织倒置域名.部门名.项目名.***
包的两个关键字：
    1、package：声明包，语法：package 包名
    [注意：声明包必须放在当前文件的第一条语句]
    2、import：导包，语法：import 包名.类名
        导入具体类：import 包名.类名
        导入一个包的所以类：import 包名.*
```

## 访问修饰符

| 关键字              | 作用域               |
| ------------------- | -------------------- |
| private：私有的     | 当前类               |
| 默认访问修饰符      | 当前包（本类，同包） |
| protected：受保护的 | 当前包以及子类       |
| public：公共的      | 其他类都可以访问     |

## Static:静态的

static:静态的【修饰属性和方法】
1、实例变量和类变量：
    实例变量：非static变量
    类变量：也叫静态变量，使用static修饰的变量
2、实例方法和类方法
    实例方法：非static修饰的方法
    类方法：也叫静态方法，使用static修饰的方法
    实例方法和静态方法的调用：
1、同一个类
        实例方法调用实例方法：方法名();
        实例方法调用静态方法：方法名();
        静态方法调用静态方法：方法名();
        静态方法调用实例方法：对象名.方法名();
2、不同类
        调用实例方法：都是对象名.方法名()
        调用静态方法：类名.方法名()
静态变量：可以被所有的实例对象共享【作为不同实例之间交流共享数据】
实例方法和静态方法注意事项
     1、实例方法和静态方法中都不能定义静态变量
     2、静态方法中不能使用super和this关键字
静态代码块和构造方法的执行顺序
  1、静态代码块：加载类时执行，只执行一次
  2、构造方法：创建对象时执行，可执行多次

## 局部变量和成员变量

- 成员变量：方法外定义的变量，有初始值，在整个类可以使用
  - 初始值：String null int 0
- 局部变量：方法内定义的变量，没有初始值，只能在创建该变量的方法中使用，如果局部变量和成员变量名一致，优先使用局部变量，如果要使用成员变量，则使用this.变量名调用

## Java三个特点

1. 封装
   - 定义：隐藏内部细节，提供公共的的对外访问方法
   - 优点：隐藏类的内部信息方便加入控制语句
   - ​           只能通过规定的方法访问数据，方便修改实现
   - 体现：
     - 属性私有化，通过getXXX和setXXX方法进行访问
     - 对代码的封装【将公共的代码提取到方法中】
     - 对数据的封装【将变量提取到类中】
2. 继承
   - 定义：将子类共有信息抽取到父类
   - 关键字：extends
   - 优点：提高代码复用性
   - 子类不能继承父类那些成员
     - private修饰的成员
     - 构造方法
     - 使用默认访问修饰符不在同包的成员
   - 继承关系下的构造方法执行顺序
     先执行父类构造方法，再执行子类构造方法
     如果没有显示调用父类构造方法，则默认调用执行父类无参构造方法
     如果子类显式通过super关键字调用父类构造方法，则执行调用的父类构造方法
   - this和super关键字作用
     1. this关键字：指代当前类的对象
        1. 调用当前类的属性：this.属性名
        2. 调用当前类的放啊：this.方法名();
        3. 调用当前类的构造方法：this(参数);

     2. super关键字：指代父类对象
        1. 调用父类的属性：super.属性名
        2. 调用当前类的方法：super.方法名();
        3. 调用当前类的构造方法：super(参数)
3. 多态

   1. 概念：同一引用类型，通过不同的实例执行不同的操作

   2. 多态的实现要素

      1. 继承关系
      2. 父类引用指向子类对象
      3. 子类重写父类抽象方法

   3. 多态实现方式

      1. 父类引用作为形参
      2. 父类引用作为方法的返回值

   4. 抽象类和抽象方法

      

      ~~~java
      1、
      //抽象类：语法：
      public abstract class 类名{}
      //抽象类、抽象方法：语法
      public abstract 返回值类型 方法名(){}
      2、
      //抽象方法：特点
      1、抽象方法没有方法体
      2、抽象方法所在的类必须是抽象类
      3、抽象方法必须被子类重写，抽非子类是抽象类
      ~~~

   5. 向上转型和向下转型

      1. 向上转型：自动类型转换，子类转为父类类型
      2. 向下转型：强制转换，父类类型转为子类类型

   6. instanceof关键字

      1. 判断对象类型：对象 instanceof 类型
      2. 通常和向下转型结合使用

   7. 动态绑定和静态绑定

      1. 动态绑定（实例方法）
         1. 跟引用变量实际隐痛的对象进行绑定，调用的是重写后的方法
         2. 运行时由JVM决定

      2. 静态绑定（静态方法、实例变量、静态变量）
         1. 跟引用变量的声明类型进行绑定
         2. 编译时就已经进行绑定

   8. 多态的优点：提高代码的扩展性和和维护行性


## Override&Overload

Overload和Override特点
 Overload：参数列表不同，跟访问修饰符和返回值类型无关
 Override：子类中，方法名和参数列表形同，返回值是父类类型或是其子类
     子类访问修饰符不能严于父类

## 接口

1. 接口的语法
   1. 定义接口：public interface 接口名();
   2. 实现类实现接口：public class 类名 implements 接口名
2. 接口的特性
   1. JDK1.8之前
      1. 接口中的所有属性都是静态常量(public static final)，必须显式初始化
      2. 就恶口中的所有方法都默认是公共的抽象方法(public abstract)
      3. 接口没有构造方法，不可以被实例化，但可以被实现 >>>常作为类型使用
      4. 实现类必须实现接口中的所有方法
      5. 实现类可以实现多个接口【多个接口用逗号隔开】
   2. JDK1.8之后
      1. 接口中可以有多个默认方法(有方法体)
         1. 关键字 default >>> public default 返回值类型 方法名(形参列表){方法体}
         2. 作用，解决了接口与其他实现类之间耦合度过高，修改接口，所有实现类必须随之修改的问题
         3. 默认方法可以被机车给，通过实例调用
         4. 如果一个类实现了多个接口，多个接口都是定义相同的默认方法，则实现类会出现编译错误 >>>解决方法
            1. 方案一：实现类需要覆盖重写接口的默认方法
            2. 方案二：可以使用super类调用指定接口默认方法【接口名.super.方法名()】
         5. 默认接口可以有多个
      2. 接口中可以声明多个静态方法
         1. 接口中的静态方法必须是public,public 可以省略，但是static不能省略
         2. 静态方法不能被继承及覆盖，只能被具体所在的接口调用
         3. 接口中的静态方法可以有多个
   3. 抽象类和接口异同点
      1. 相同点
         1. 代表系统的抽象层
         2. 都不能被实例化
         3. 都能包含抽象方法
      2. 不同点
         1. 一个类只能继承一个抽象类，一个类可以实现多个接口
         2. 抽象类可以包含普通方法、静态方法和抽象方法；JDK1.8之前：接口只能包含抽象方法；JDK1.8之后：可以有抽象方法、默认方法和静态方法
      3. 使用原则
         1. 接口
            1. 接口：has - a的关系
            2. 接口用系统和外界交互的窗口
            3. 接口一旦指定就不允许随意修改
            4. 接口便于共呢个扩展和维护
         2. 抽象类
            1. 抽象类：is - a的关系
            2. 抽象类可以完成部功能的实现，还有部分可用作系统的扩展点
            3. 抽象类便于复用
   4. 接口的作用
      1. 提高程序的可维护性和可扩展性
      2. 提高程序的规范性
      3. 提高程序的安全性
   5. 面向对象设计原则
      1. 多用组合，少用继承
      2. 这对接口编程
      3. 针对扩展开放，针对改变关闭

## 异常

1. 异常：程序运行过程中发生的不正常事件，会中断正在运行的程序

2. 异常处理

   1. 概念：Java编程语言使用的异常处理机制为程序提供错误处理的能力
   2. 异常信息
      1. 在catch中处理异常【加上自定义处理信息 -- system.out.println("提示")】
      2. 调用异常对象方法处理信息
         1. void printStackTrace()  >> 输出异常堆栈信息
         2. String getMessage() >> 返回异常信息描述字符串，书printStackTrace()输出信息
   3. 异常处理方式
      1. try-catch-finally
         1. 语法：try{可能出现异常的代码}
            			catch(异常类型 对象名){处理异常的操作}
               			finally{始终执行的代码}
         2. 多重catch注意事项
            1. catch按顺序进行匹配
            2. catch只会执行第一个匹配的异常类型
            3. catch顺序，先子类异常，再父类异常
         3. finally不执行的唯一情况是 退出Java虚拟机
         4. try-catch中存在return时执行顺序，先执行funally再执行return
      2. throw和throws对比
         1. throw
            1. 抛出异常
            2. 位于方法体，作为单独的语句使用
            3. 抛出一个异常对象，且只能有一个
         2. throws
            1. throws声明异常
            2. 必须放在方法参数后，不能单独使用
            3. 声明抛出异常类型，可以声明多个异常类型

3. 异常体系结构

   ![](D:\XMind\Snipaste_2022-08-06_10-43-46.png)

## 集合框架的结构

```java
Collection接口 ：存储一组无序不唯一的对象
  list 子接口 ：存储一组有序不唯一的对象
      ArrayList实现类 ：底层数据结构是数组，实现长度可变
      LinkedList实现类 ：底层数据结构是链表
  set  子接口 ：存储一组无序唯一的对象
      HashSet实现类
      TreeSet实现类
Map接口：键值对
HashMap:实现类
TreeMap:实现类
```

## Collection、List、Set集合存储特点

~~~java
Collection:存储一组无序不唯一的数据
List:存储一组有序不唯一的数据
Set:存储一组无序唯一的数据
~~~

## ArrayList和LinkedList的区别

~~~
ArrayList实现类 ：底层数据结构是数组，实现长度可变
LinkedList实现类 ：底层数据结构是链表
~~~

## 实用类



## 构造方法的语法、作用、使用场合

- 语法：public 类名 (参数列表){ }
- 作用：对象初始化
- 场合：创建对象

## 类和对象的关系

- 关系：类是对象的抽象，对象的类的具体实例

## 创建对象调用属性和方法的语法

- 语法：类名 对象名 = new 类名();
  - 对象名.属性名 = 值；
  - 对象名.方法名();

## 方法的注意事项

- 方法不能嵌套
- 方法返回值类型如果为void 则没有返回值
- 方法返回值类型必须和返回值一致

## 输入输出流

~~~Java
//示例
public class test{
    public void main(String[] args){
        //输入流对象
       	Reader reader = null;
        Writer writer = null;
        //输出流对象
        BufferedWriter bufferedwriter = null;
        BufferedReader bufferedreader = null;
        try{
            //实例化子类
            reader = new FileReader("PATH");
            bufferedreader = new BufferedReader(reader);
            writer = new FileWriter("PATH");
            bufferedwriter = new BufferedWriter(writer);
            String str = null;
            //读取操作
            while((str = bufferedreader.readLine()) != null){
				bufferedwriter.write(str);                
            }
        }catch(IOException e){
            throw new RuntimeException(e);
        }finally{
            //关闭流
        }
    }
}
~~~

## 对象序列化

~~~java
//示例
//要序列化的类必须实现Serializable接口
public class Student implements Serializable{
    ......
}
//测试类
public class test {
    public static void main(String[] args) {
        //创建对象
        Student stu = new Student(1001,"张三",20);
        //文件输出流【写入文件】
        FileOutputStream fos = null;
        ObjectOutputStream oos = null;
        //文件输入流【读取文件】
        FileInputStream fis = null;
        ObjectInputStream ois = null;
        try {
            //实例化输出流
            fos = new FileOutputStream("D:\\application\\student.txt");
            oos = new ObjectOutputStream(fos);
            //对象流将对象写入对象中
            oos.writeObject(stu);
            //书信输出流
            oos.flush();

            System.out.println("对象写入成功");
            //对象流读取进行显示
            fis = new FileInputStream("D:\\application\\student.txt");
            ois = new ObjectInputStream(fis);
            Student s1 = (Student) ois.readObject();
            s1.show();
        } catch (IOException e) {
            System.out.println("对象写入失败");
            throw new RuntimeException(e);
        } catch (ClassNotFoundException e) {
            System.out.println("读取失败");
            throw new RuntimeException(e);
        } finally {
            try {
                //关闭数据流
                if(oos != null) oos.close();
                if(fos != null) fos.close();
                if(fis != null) fis.close();
                if(ois != null) ois.close();
            } catch (IOException e) {
                throw new RuntimeException(e);
            }
        }
    }
}
~~~

## Java内存

```Java
内存：
栈内存：运行的方法，局部变量也存储在其中
堆内存：new出来的对象存放在堆内存中
方法区：字节码文件[.class]加载到方法区
【当Java文件编译后生成字节码文件，加载到方法区，
   JVM自动调用执行main方法，main方法会进入栈内存运行
    main方法执行完毕弹栈】
```

## 冒泡排序

~~~Java
int [] arr = {1,2,3,4};
//从大到小排序
for(int i = 0; i < arr.length-1 ; i ++){
    for(int j = 0; j < arr.length - i - 1 ; j++){
        if(arr[j] < arr[j+1]){
            int temp = arr[j];
            arr[j] = arr[j+1];
            arr[j+1] = temp;
        }
    }
}
~~~

## 多线程

1. 程序、进程和线程

   1. 程序：有序指令的集合
   2. 进程
      1. 正在运行的程序，软件在内存中的运行过程
      2. 进程会在内存中开辟空间存储资源信息
   3. 线程：进程中的独立运行单元
      1. 进程中的一个任务
      2. 线程不占用内存空间，共享进程的空间和资源

2. 多线程

   1. 概念：一个进程中运行了多个线程，用来完成不同的工作，则称之为多线程，多线程交替占用CPU资源，而非真正的并行执行
   2. 优点
      1. 充分利用CPU的资源，提升代码的性能
      2. 简化编程模型，更好的软件设计和架构
      3. 带来良好的用户体验
   3. 主线程
      1. 负责整个Java程序运行的入口线程-----Main方法
      2. 产生其他子线程
      3. 必须是最后完成执行，因为他执行各种关闭动作
   4. 注意事项：不能无限开启多线程，线程数超过CPU能处理的极限，电脑运行速度会急剧下降

3. 线程

   1. 创建线程的两种方式
      ~~~Java
      //（一）继承Thread类：实现步骤
      //1、继承Thread类
      public class MyThread extends Thread{
          //2、重写run方法
          @override
          public void run(){
              //启动线程
              //线程类名 对象名 = new 线程类名();
              //对象名.start();
          }
          //特点：操作简单，可直接操作线程对象；无法继承其他的类，Java属于单继承
      }
      ~~~

      ~~~java
      //（二）实现Runnable接口
      //1、实现接口
      public class MyRunnable implements Runnable{
          //实现run方法
          @override
          public void run(){
              //启动线程
              //Thread thread = new Thread(new 线程名,"线程别名")
          }
          //特点：可以继承其他类；可以实现共享资源
      }
      ~~~

   2. 调用run()和start()的区别

      1. run():属于正常的方法调用，单线程执行，只有一条主线程执行路径
      2. start():表示启动线程，多线程执行，多条执行路径，主线程和子线程并行交替执行

   3. 线程状态

      1. 创建状态：创建线程对象时的状态
      2. 就绪状态：调用start()方法，等待抢占CPU资源
      3. 运行状态：抢占到CPU，执行run方法
      4. 阻塞状态：通过调用sleep等方法，线程进入阻塞状态
      5. 死亡状态：线程自然结束或强制结束

   4. Thread类常用方法
      ~~~Java
      void setPriority(int 线程级别)
          //设置线程的级别【默认值是5】，值1-10优先级高的线程获取CPU资源
          //MAX:线程对象.setPriority(Thread.MAX_PRIORITY);
          //MIN:线程对象.setPriority(Thread.MIN_PRIORITY);
      static void sleep(long 休眠时间)
          //在指定的毫秒数内让当前正在执行的线程休眠：单位/毫秒  Thread.sleep(时间)
          //睡眠时间后线程进入可运行状态
      void join(long 时间)
          //暂停当前线程，等待其他线程运行
          //1、没有参数：表示等待其他线程运行结束再执行 2、有参数，暂停指定时间，时间结束则开始执行
      static void yieId()
          //暂停正在执行的线程对象，并执行其他线程
          	//暂停当前线程吗，允许其他具有相同优先级的线程获得运行机会
          	//该线程处于就绪状态，不转为阻塞状态
          //线程礼让。【重新获得CPU机会】
      void interrupt() //中断线程
      boolean isAlive() //测试线程是否处于活动状态
          
      ~~~

4. 线程安全问题

   1. 什么是线程安全：多个线程操作同一共享资源，将引发数据不安全
   2. 原因：多线程共同操作数据时，引发的冲突（如延迟时，操作未全部完成等等）
   3. 如何解决线程安全
      1. 第一种方式：同步方法：使用synchronized修饰的方法控制对类成员变量的访问
         1. 访问修饰符 synchronized返回值类型 方法名(参数列表){}
         2. synchronized 访问修饰符 返回值类型 方法名(参数列表){}
      2. 第二种方式：同步代码块：使用synchronized关键字修饰的代码块
         1. synchronized(syncObject){代码}
         2. 参数 syncObject为需要同步的对象，通常为this
