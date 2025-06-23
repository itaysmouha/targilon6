# targilon6

targilon6 - https://github.com/itaysmouha/targilon6.git

Itay Smouha 322819848


## code before synchornized

The result of this code is less than 20,000 due to a race condition. Both threads are incrementing the same variable bar, but since the increment operation (bar++) is not atomic, some increments are lost when
threads overlap in execution. This leads to an incorrect final count.

## code after synchronized

The synchronized keyword in Java ensures that only one thread at a time can execute a synchronized method on the same object. It acts like a lock around the method, preventing other threads from entering it until 
the current thread is done.
This is crucial for shared data (like the bar variable), where multiple threads may try to read and update the same value at the same time.
With synchronized, Java ensures that each bar++ is executed fully before another thread can enter the method.
This prevents interference and guarantees the final result is exactly 20000.

## Difference between synchronized void and synchronized(this) versions

In the "public synchronized void baz()" version:
This is a synchronized instance method. It implicitly locks on the current object (this), ensuring that only one thread at a time can execute the entire method on that object.

In the "synchronized(this)" version:
This version locks explicitly on the current object (this), but only around the block inside the method. It achieves the same effect in this case, since the whole method is just that one line.
synchronized(this) blocks are useful when you only want to lock part of a method or use a different lock object.




