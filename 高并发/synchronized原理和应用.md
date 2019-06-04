# synchronized原理
## synchronized应用
   synchronized 是重量级锁，可以利用synchronized实现同步，Java中每个对象都可以作为锁。具体表现为以下3种形式：
   - 对于普通同步方法，锁是当前实例对象。
   - 对于静态同步方法，锁是当前类的class对象。
   - 对于同步方法块，锁的是synchronized括号里配置的对象。

## 实现原理
   JVM基于进入和退出Monitor对象来实现方法同步和代码块同步，但两者的实现细节不一样。代码块同步是使用monitorenter和monitorexit指令实现的，而方法同步是使用另一种方式实现的。方法同步也可以使用这两个指令实现。
 - JVM要保证每个monitorenter和monitorexit配对
 - monitorenter编译后插入到同步代码块的开始位置，monitorexit插入到方法结束和异常处。
 - 任何对象都有一个monitor与之关联，当且一个monitor对象被持有后，它将处于锁定状态。
 - 线程执行到monitorenter指令时会尝试获取对象对应的monitor所有权即对象锁。
