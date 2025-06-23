# targilon6

targilon6 - 

The result of this code is less than 20,000 due to a race condition. Both threads are incrementing the same variable bar, but since the increment operation (bar++) is not atomic, some increments are lost when threads overlap in execution. This leads to an incorrect final count.

Itay Smouha 322819848
