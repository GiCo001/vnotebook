# 对比 Exception 和 Error，另外，运行时异常运行时异常与一般异常有什么区别？


***Exception 和 Error 都是继承了 Throwable 类，在 Java 中只有 Throwable 类型的实例才可以被抛出（throw）或者捕获（catch），它是异常处理机制的基本组成类型。Exception 和 Error 体现了 Java 平台设计者对不同异常情况的分类。***
- Exception 是程序正常运行中，可以预料的意外情况，可能并且应该被捕获，进行相应处理 。Exception 又分为检查型异常（IOException 在源代码里必须显式地进行捕获处理，这是编译期检查的一部分） 和 非检查型异常（NPE ，不需要显式捕获 运行时可能会抛出）

-  Error 是指在正常情况下，不大可能出现的情况，绝大部分的 Error 都会导致程序（比如 JVM 自身）处于非正常的、不可恢复状态。既然是非正常情况，所以不便于也不需要捕获，常见的比如 OutOfMemoryError 之类，都是 Error 的子类。


***运行时异常即为不检查异常，类似 NullPointerException、ArrayIndexOutOfBoundsException 之类，通常是可以编码避免的逻辑错误，具体根据需要来判断是否需要捕获，并不会在编译期强制要求。***




![关系表](images/20190220173950455_1378793371.png)


