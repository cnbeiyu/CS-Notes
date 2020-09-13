# 	算法

## 排序

![img](https://www.runoob.com/wp-content/uploads/2019/03/0B319B38-B70E-4118-B897-74EFA7E368F9.png)

## 二叉树

# 网络

![image.png](https://i.loli.net/2020/09/03/naUgOu1PET7Qd6v.png)

## 网络层

因为网络层是整个互联网的核心，因此应当让网络层尽可能简单。网络层向上只提供简单灵活的、无连接的、尽最大努力交互的数据报服务。

使用 IP 协议，可以把异构的物理网络连接起来，使得在网络层看起来好像是一个统一的网络。

与 IP 协议配套使用的还有三个协议：

- 地址解析协议 ARP（Address Resolution Protocol）
- 网际控制报文协议 ICMP（Internet Control Message Protocol）
- 网际组管理协议 IGMP（Internet Group Management Protocol）

![image.png](https://i.loli.net/2020/09/03/DATzI2BVMpRKE5t.png)

## 运输层

## 应用层

# JAVA

## 四种访问修饰符

![image.png](https://i.loli.net/2020/09/01/4sH83xT2zCweVmf.png)

## 八种非访问修饰符

static ，静态修饰符，修饰类方法和类变量。 final 最终修饰符，修饰类、方法和变量，修饰的类不能够被继承，修饰的方法不能被重新定义，修饰的变量表示为不可修改的常量。 abstract ，抽象修饰符，用来创建抽象类和抽象方法。 synchronized 修饰符，用于线程编程。 transient 修饰符,用于跳过序列化对象中特定的敏感变量 volatile 修饰符，用于线程编程。

#### Final

1、final修饰类：当用final修饰一个类时，**表明这个类不能被继承。** 也就是说，如果一个类你永远不会让他被继承，就可以用final进行修饰。final类中的成员变量可以根据需要设为final，但是**要注意final类中的所有成员方法都会被隐式地指定为final方法。**
  在使用final修饰类的时候，要注意谨慎选择，除非这个类真的在以后不会用来继承或者出于安全的考虑，尽量不要将类设计为final类。
  2、final修饰方法：“使用final方法的原因有两个。第一个原因是把方法锁定，以防任何继承类修改它的含义；第二个原因是效率。在早期的Java实现版本中，会将final方法转为内嵌调用。但是如果方法过于庞大，可能看不到内嵌调用带来的任何性能提升。在最近的Java版本中，不需要使用final方法进行这些优化了。”
  因此，如果只有在想明确禁止该方法在子类中被覆盖的情况下才将方法设置为final的。注：类的private方法会隐式地被指定为final方法。
  3、final修饰变量：对于一个final变量，如果是基本数据类型的变量，则其数值一旦在初始化之后便不能更改；如果是引用类型的变量，则在对其初始化之后便不能再让其指向另一个对象。
  当final变量是基本数据类型以及String类型时，如果在编译期间能知道它的确切值，则编译器会把它当做编译期常量使用。也就是说在用到该final变量的地方，相当于直接访问的这个常量，不需要在运行时确定。

好处：

  1、final关键字提高了性能。JVM和Java应用都会缓存final变量。
  2、final变量可以安全的在多线程环境下进行共享，而不需要额外的同步开销。
  3、使用final关键字，JVM会对方法、变量及类进行优化。
  4、对于不可变类，它的对象是只读的，可以在多线程环境下安全的共享，不用额外的同步开销。

#### static

##### 1. 为什么要用static关键字？ 

 通常来说，用new创建类的对象时，数据存储空间才被分配，方法才供外界调用。但有时我们只想为特定域分配单一存储空间，不考虑要创建多少对象或者说根本就不创建任何对象，再就是我们想在没有创建对象的情况下也想调用方法。在这两种情况下，static关键字，满足了我们的需求。

##### 2. ”static”关键字是什么意思？Java中是否可以覆盖(override)一个private或者是static的方法？

“static”关键字表明一个成员变量或者是成员方法可以在没有所属的类的实例变量的情况下被访问。

Java中static方法不能被覆盖，因为方法覆盖是基于运行时动态绑定的，而static方法是编译时静态绑定的。static方法跟类的任何实例都不相关，所以概念上不适用。

##### 3. 是否可以在static环境中访问非static变量？

static变量在Java中是属于类的，它在所有的实例中的值是一样的。当类被Java虚拟机载入的时候，会对static变量进行初始化。如果你的代码尝试不用实例来访问非static的变量，编译器会报错，因为这些变量还没有被创建出来，还没有跟任何实例关联上。

##### 4. static静态方法能不能引用非静态资源？

不能，new的时候才会产生的东西，对于初始化后就存在的静态资源来说，根本不认识它。

##### 5. static静态方法里面能不能引用静态资源？

可以，因为都是类初始化的时候加载的，大家相互都认识。

##### 6. 非静态方法里面能不能引用静态资源？

可以，非静态方法就是实例方法，那是new之后才产生的，那么属于类的内容它都认识。

#### volatite

在多线程中保证变量的一个可见性，避免多线程下读取到脏数据。确保每次都从内存中读，而不是cpu寄存器。

源码点不进去看不了c语言实现

## 多线程

https://ke.qq.com/course/427525?taid=3691047649969669

并发编程三大特性：可见性，原子性，有序性

![image-20200902012147887](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200902012147887.png)

![image.png](https://i.loli.net/2020/09/01/q6LCwI9GWy8uUOe.png)

如果不是volatite修饰的话，其他线程会一直读工作内存

![image-20200831021606731](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200831021606731.png)

#### MESI缓存一致性协议

MESI缓存一致性协议：cpu（多核）使用**总线嗅探机制**感知主内存数据变化

总线嗅探弊端：有可能总线嗅探到变化后，其他cpu就立刻读到了改数据，而实际上还没有来得及写到主内存

![](https://i.loli.net/2020/09/01/9TE8DIR2CJAOU5B.png)

![](https://i.loli.net/2020/09/01/bXFrVR6awuvl3A7.png)

#### volatite

volatite：在最后到达总线前加一下lock，在加到内存后unlock。与总线加锁相比，优化了加锁位置（非在read时加锁），lock时间极短，大大提高并行性能。

volatile是java语言层面给出的保证，MSEI协议是多核cpu保证cache一致性

volatite可以保证可见性和有序性，但不能保证原子性，保证原子性还需借助**synchronized**这样的锁机制

![](https://i.loli.net/2020/09/01/OPXWkfJlh8v6Cbc.png)

#### 线程状态

![preview](https://pic3.zhimg.com/v2-20edff079dc147b795e08261be1161f4_r.jpg?source=1940ef5c)

一个线程只能处于一种状态，并且这里的线程状态特指 Java 虚拟机的线程状态，不能反映线程在特定操作系统下的状态。

##### 新建（NEW）

创建后尚未启动。

##### 可运行（RUNABLE）

正在 Java 虚拟机中运行。但是在操作系统层面，它可能处于运行状态，也可能等待资源调度（例如处理器资源），资源调度完成就进入运行状态。所以该状态的可运行是指可以被运行，具体有没有运行要看底层操作系统的资源调度。

##### 阻塞（BLOCKED）

请求获取 monitor lock 从而进入 synchronized 函数或者代码块，但是其它线程已经占用了该 monitor lock，所以出于阻塞状态。要结束该状态进入从而 RUNABLE 需要其他线程释放 monitor lock。

##### 无限期等待（WAITING）

等待其它线程显式地唤醒。

阻塞和等待的区别在于，阻塞是被动的，它是在等待获取 monitor lock。而等待是主动的，通过调用 Object.wait() 等方法进入。

| 进入方法                                   | 退出方法                             |
| ------------------------------------------ | ------------------------------------ |
| 没有设置 Timeout 参数的 Object.wait() 方法 | Object.notify() / Object.notifyAll() |
| 没有设置 Timeout 参数的 Thread.join() 方法 | 被调用的线程执行完毕                 |
| LockSupport.park() 方法                    | LockSupport.unpark(Thread)           |

##### 限期等待（TIMED_WAITING）

无需等待其它线程显式地唤醒，在一定时间之后会被系统自动唤醒。

| 进入方法                                 | 退出方法                                        |
| ---------------------------------------- | ----------------------------------------------- |
| Thread.sleep() 方法                      | 时间结束                                        |
| 设置了 Timeout 参数的 Object.wait() 方法 | 时间结束 / Object.notify() / Object.notifyAll() |
| 设置了 Timeout 参数的 Thread.join() 方法 | 时间结束 / 被调用的线程执行完毕                 |
| LockSupport.parkNanos() 方法             | LockSupport.unpark(Thread)                      |
| LockSupport.parkUntil() 方法             | LockSupport.unpark(Thread)                      |

调用 Thread.sleep() 方法使线程进入限期等待状态时，常常用“使一个线程睡眠”进行描述。调用 Object.wait() 方法使线程进入限期等待或者无限期等待时，常常用“挂起一个线程”进行描述。睡眠和挂起是用来描述行为，而阻塞和等待用来描述状态。

##### 死亡（TERMINATED）

可以是线程结束任务之后自己结束，或者产生了异常而结束。

## 设计模式



## 集合

## 面对对象

#### 封装

利用抽象数据类型将数据和基于数据的操作封装在一起，使其构成一个不可分割的独立实体。数据被保护在抽象数据类型的内部，尽可能地隐藏内部的细节，只保留一些对外的接口使其与外部发生联系。用户无需关心对象内部的细节，但可以通过对象对外提供的接口来访问该对象。

优点：

- 减少耦合：可以独立地开发、测试、优化、使用、理解和修改

- 减轻维护的负担：可以更容易被理解，并且在调试的时候可以不影响其他模块

- 有效地调节性能：可以通过剖析来确定哪些模块影响了系统的性能

- 提高软件的可重用性

- 降低了构建大型系统的风险：即使整个系统不可用，但是这些独立的模块却有可能是可用的

#### 继承

  继承实现了 **IS-A** 关系，例如 Cat 和 Animal 就是一种 IS-A 关系，因此 Cat 可以继承自 Animal，从而获得 Animal 非 private 的属性和方法。

  继承应该遵循里氏替换原则，子类对象必须能够替换掉所有父类对象。

#### 多态

多态分为编译时多态和运行时多态：

- 编译时多态主要指方法的重载
- 运行时多态指程序中定义的对象引用所指向的具体类型在运行期间才确定

运行时多态有三个条件：

- 继承
- 覆盖（重写）
- 向上转型

## 装箱拆箱

# Mysql

## sql执行流程

![](https://i.loli.net/2020/09/01/wnZRmf2YrTDMeqj.png)

## MVCC

https://www.bilibili.com/video/BV1xh411Z79d?p=16

![](https://i.loli.net/2020/09/01/dRa8m9XMFeUs2ny.png)

![](https://i.loli.net/2020/09/01/hlmpgAeNMFzBsC7.png)

MVCC不能解决幻读问题，因为select操作不会更新事务版本号，会使用快照read-view，但删改查会更新事务版本号。

幻读只有可串行化才可以解决，即所有事务串行执行，非并发。但是串行化效率过低一般不适用，一般通过JAVA同步并发和redis来解决，mysql可以用间隙锁解决。

## B+ Tree 索引

https://ke.qq.com/webcourse/index.html#cid=2868548&term_id=103072741&taid=9911706485245252&vid=5285890806944734006

![](https://i.loli.net/2020/09/02/YsrZtEM3J2eX619.png)

![](https://i.loli.net/2020/09/02/x7rTkyaYPozWvM2.png)

![](https://i.loli.net/2020/09/02/mEge1wrHKCo2lF6.png)

![](https://i.loli.net/2020/09/02/qrmwy5ZNzHAQocU.png)

使用二级索引的弊端：额外储存空间，增删改复杂，二级索引是主键索引的索引

## 锁与事务

锁是计算机协调多个进程或线程并发访问某一资源的机制

### 分类

从性能上分为**乐观锁**（版本控制实现）和**悲观锁**（等待实现）

从数据库操作上分为**读锁**和**写锁**（都属于悲观锁）

读锁（共享锁）：多个读操作同时进行不受影响

写锁（排他锁）：当前写操作没有完成前会阻断其他写锁和读锁

从数据操作粒度上分为**表锁**和**行锁**

### 三锁

#### 表锁

偏读，偏向MylSAM，开销小，加锁快，但锁冲突率大，并发度低。

MYISAM在执行select前会给涉及的表加读锁，在执行增删改前会加写锁。

读锁会阻塞写，但不会阻塞读。写锁会把读和锁都阻塞。

#### 行锁

偏写，偏向InnoDB，开销大，加锁慢，但锁冲突率低，并发度高。

InnoDB与MYISAM最大区别就是支持了事务和行锁。

### 事务

![image.png](https://i.loli.net/2020/09/01/WrDm19jaQt8VL3z.png)

#### 并发事务带来的问题

更新丢失：多个事务选择同一行，最后的更新会覆盖了其他食物做的更新。

脏读：事务A读取到了事务B已经修改但尚未提交的数据，并进行操作。此时如果B事务回滚，A读到的就是脏数据，不符合一致性。

不可重复读：事务A读取到了事务B已经提交的修改数据，不符合隔离性。

幻读：事务A读取到了事务B提交的新增数据，不符合隔离性。 

#### 事务隔离级别

mysql默认隔离级别是可重复读

![](https://i.loli.net/2020/09/01/8tVY97lCrqib5UW.png)

#### 间隙锁

间隙锁某些情况可以解决幻读的问题

间隙锁：通过范围加锁，即使数据不存在，执行update where xx >1 and xx<=100；这样其他session就无法插入这个范围的数据了

# Spring

## IOC

IOC容器的出现是为了解决维护复杂依赖关系对象时的繁琐性，其可以将对象的构建方式统一，并且自动维护对象的依赖关系，从而降低系统的实现成本。前提是需要提前对目标对象基于XML进行声明。

![](https://i.loli.net/2020/09/12/iL1CDjwctYZK7kf.png)

### 实体Bean的构建

spring.xml中保存了我们对Bean的描述配置，BeanFactory会读取这些配置然后生成对应的Bean。

1. 基于Class构建

   ~~~xml
   <bean class="com.cntwz.spring.Hello"></bean>
   ~~~

   这是最常规的方法，spring底层会基于class属性，通过反射进行构建，只能使用无参构造函数。

2. 构造方法构建

   ![](https://i.loli.net/2020/09/12/BIpj1HJbMNDlWCx.png)

   ~~~xml
   <bean class="com.cntwz.spring.Hello"></bean>
   	<constrctor-arg index="0" value="twz"/>
       <constrctor-arg name="sex" value="1"/>
   ~~~

3. 静态工厂方法构建

   ![image-20200912233642920](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200912233642920.png)

   ~~~xml
   <bean class="com.cntwz.spring.Hello" factory-method="build"></bean>
   ~~~

   基于build来构建，A/B测试可以用静态工厂方法

4. FactoryBean构建

   新建xxxFactoryBean类，继承FactoryBean,基于getObject()来匹配

   ![image-20200912235018182](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200912235018182.png)

   ~~~xml
   <bean id="driver" class="com.cntwz.spring.HelloFactoryBean">
   	<property name="jdbcUrl" value="jdbc:mysql://localhost:3306"></property>
   </bean>
   ~~~

   FactoryBean可以自定义创建类，可以用在mybatis，mysql之类的配置

### Bean的基本特性

1. 作用范围

   通过scope配置，单例or多例

2. 生命周期

   通过init-method,destory-method属性可以分别指定初始方法和销毁方法

   ![](https://i.loli.net/2020/09/13/oVCxv7PDRBX8Kcm.png)

3. 装载机制

   通过lazy-init属性可以设置Bean在何时加载，默认是false

   true：懒加载，延迟加载

   false：非懒加载，容器启动就创建对象

   什么时候用懒加载？

   懒加载会使容器启动更快，而非懒加载可以在容器启动时更快发现程序中的错误

### 依赖注入

依赖注入是IOC解决Bean复杂依赖的方式，有以下几种方式

1. set方法注入

   ~~~xml
   <bean class="com.cntwz.spring.Hello">
   	<property name="twz" ref="fineSpring"/>
   </bean>
   ~~~

2. 构造方法注入

   ~~~xml
   <bean class="com.cntwz.spring.Hello">
   	<constructor-arg name="twz">
   		<bean class="com.cntwz.xxx"/>
   	</constructor-arg>	
   </bean>
   ~~~

3. 自动注入（byName，byType）

   ~~~xml
   <bean id="helloAutowireConstructor"
   	class="com.twz.spring.xxx" autowire="byName">
   </bean>
   ~~~

   

4. 方法注入（lookup-method）

### IOC设计原理

IOC实现中，我们在xml中描述的Bean信息最后都会保存至BeanDefinition对象中，其与bean是一一对应关系，由此可见，xml bean中的属性最后都会体现在BeanDefinition中（除了id和name），id和name作为key帮助BeanDefinition注册，保存在BeanDefinitionRegistry中。

BeanDefinitionReader从xml中读取bean，创建BeanDefinition对象，再往BeanDefinitionRegistry注册。

![](https://i.loli.net/2020/09/13/WEIBLlCvxdAbepJ.png)

# JVM

## 基础



![](https://i.loli.net/2020/09/06/1Pn7kKYwTucZ9dH.png)

栈（线程私有）：JAVA线程执行方法的内存模型，一个线程对应一个栈，每个方法在执行的同时都会创建一个栈帧（用于存储局部变量表、操作数栈、动态链接、方法出口等信息）不存在垃圾回收，线程结束即释放，生命周期和现场一致。

本地方法栈（线程私有）：登记native方法，在Execution Engine执行时加载本地方法库

程序计数器（线程私有）：就是一个指针，指向方法去中的方法字节码（**用来存储指向下一条指令的地址**，也即将要指向的指令代码）是非常小的内存空间。

方法区（线程共享）：类的所有字段和方法字节码，以及一些特殊方法（如构造函数），接口代码也在这里定义。简单说，所有定义的方法的信息都在该区域，**静态变量+常量+类信息（构造方法/接口定义）+运行时常量池**都在此方法区。方法区别名叫Non-Heap（非堆），1.8后叫元空间。

堆（线程共享）：虚拟机启动时创建，用于存放对象实例，几乎所有的对象（包含常量池）都在堆上分配内存，当对象无法在该空间申请到内存是就会抛出OOM异常。同时也是垃圾收集器管理的主要区域。可以通过-Xmx -Xms来分部指定最大堆和最小堆

元数据区：元数据区取代了永久代（jdk1.8以前），本质和永久代类似，区别是元数据区不在JVM中，而在本地物理内粗，永久带在虚拟机中，逻辑结构属于堆，但物理上不属于堆。堆大小=年轻代+老年代。元数据区也有可能OOM

JDK1.6及以前：有永久代，常量池在方法区

JDK1.7：有永久代，但已经逐步“去永久代”

JDK1.8及以后：无永久代，常量池在元空间

为什么jdk1.8用元数据区取代了永久代？

官方解释：移除永久代是为了融合HotSpot JVM与**JRockit VM**而做出的努力，因为JRockit VM没有永久代



![](https://i.loli.net/2020/09/06/dhrlELG8BigM7yu.png)

![image-20200906163114953](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200906163114953.png)

执行引擎：

![image-20200906163718615](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200906163718615.png)

## 类加载

### 类加载过程

类加载：类加载器将class文件加载到虚拟机内存中。

JVM对class文件是按需加载（运行期间动态加载），非一次性加载。

![](https://i.loli.net/2020/09/06/4gAzpSbMn2lHVir.png)

加载：在硬盘上查找并通过IO读入字节码文件

连接：执行校验、准备、解析（可选）步骤

校验：校验字节码文件的正确性

准备：给类的静态变量分配内存，并赋予默认值

解析：类装载器装入类所引用的其他所有类

初始化：对类的静态变量初始化为指定的值，执行静态代码块

### 类加载器种类

启动类加载器：负责加载JRE核心类库，如jre目标下的rt.jar，charsets.jar等

扩展类加载器：辅助加载JRE扩展目录ext下的类包

系统类加载器：负责加载ClassPath路径下的类包

自定义加载器：负责加载用户自定义路径下的类包

![](https://i.loli.net/2020/09/06/wBSflmbJ1Oa2FoI.png)

### 类加载机制

双亲委派机制：指先委托父类加载器寻找目标类，在找不到的情况下在自己的路径中查找并载入目标类。（双亲就是向上委托的父加载器）

全盘负责委托机制：当一个ClassLoader加载一个类时，除非显示的使用另一个ClassLoader，该类所依赖和引用的类也由这个ClassLoader载入

双亲委派机制的优势：

- 沙箱安全机制：自己写的String.class类不会被加载，这样可以防止核心API类库被随意篡改
- 避免类的重复加载：当父亲已经加载了该类时，就没必要给子ClassLoader再加载一次

# 中间件

### Redis

#### 数据结构

![](https://i.loli.net/2020/09/01/gwCvVWKt1xBQDdZ.png)

#### 线程模型

单线程，NIO，异步事件处理

![](https://i.loli.net/2020/09/01/9BXfPkF1TtuMpsK.png)

#### 分布式redis

SETNX(SET if Not eXists)

仅当key不存在时设置value，成功返回1，失败返回0

设置超时时间，使用jedis set()的timeout参数，要保证原子性

##### redisson

成熟的分布式redis锁框架

![image-20200902004311127](C:\Users\By\AppData\Roaming\Typora\typora-user-images\image-20200902004311127.png)

#### 与Memcached对比

Memcached 仅支持字符串类型，而 Redis 支持五种不同的数据类型，可以更灵活地解决问题。

Redis 支持两种持久化策略：RDB 快照和 AOF 日志，而 Memcached 不支持持久化。

Memcached 不支持分布式，只能通过在客户端使用一致性哈希来实现分布式存储，这种方式在存储和查询时都需要先在客户端计算一次数据所在的节点。

Redis Cluster 实现了分布式的支持。

在 Redis 中，并不是所有数据都一直存储在内存中，可以将一些很久没用的 value 交换到磁盘，而 Memcached 的数据则会一直在内存中。

#### 淘汰策略

| 策略            | 描述                                                 |
| --------------- | ---------------------------------------------------- |
| volatile-lru    | 从已设置过期时间的数据集中挑选最近最少使用的数据淘汰 |
| volatile-ttl    | 从已设置过期时间的数据集中挑选将要过期的数据淘汰     |
| volatile-random | 从已设置过期时间的数据集中任意选择数据淘汰           |
| allkeys-lru     | 从所有数据集中挑选最近最少使用的数据淘汰             |
| allkeys-random  | 从所有数据集中任意选择数据进行淘汰                   |
| noeviction      | 禁止驱逐数据                                         |

#### Mybats

持久层框架，返回JAVA对象

Mybatis加载mapper的方式：package、url、resource、class，期中package优先级最高

Mybatis一级缓存默认开启，作用域sqlsession

## 消息队列

优点：解耦 异步 削峰

弊端：重复消费 、丢消息、消息积压、顺序消费

## Kafka

大数据项目几乎都是Kafka，百万级并发x

## RockerMQ

kafka的进化，几十万级并发