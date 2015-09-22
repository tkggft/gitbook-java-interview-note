# 多线程通信面试题
##Java多线程中调用wait() 和 sleep()方法有什么不同？
* wait()方法用于线程间通信，如果等待条件为真且其它线程被唤醒时它会释放锁

* sleep()方法仅仅释放CPU资源或者让当前线程停止执行一段时间，但不会释放锁

##如何在两个线程间共享数据？

* 通过共享对象(用wait和notify方法)

* 使用像阻塞队列这样并发的数据结构


##Java中notify 和 notifyAll有什么区别？

* notify()方法不能唤醒某个具体的线程，所以只有一个线程在等待的时候它才有用武之地

* notifyAll()唤醒所有线程并允许他们争夺锁确保了至少有一个线程能继续运行

##为什么wait, notify 和 notifyAll这些方法不在thread类里面？

* 由于wait，notify和notifyAll都是锁级别的操作，所以把他们定义在Object类中因为锁属于对象

* JAVA提供的锁是对象级的而不是线程级的

