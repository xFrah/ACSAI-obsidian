## Thread structure
### WIP

## Thread creation
Threads are created using the `pthread_create` function. This function takes four arguments:
- A pointer to a `pthread_t` variable, which will be used to identify the thread.
- A pointer to a `pthread_attr_t` variable, which contains the attributes for the thread. If `NULL` is passed, the default attributes will be used.
- A pointer to the function that the thread will execute.
- A pointer to the arguments that will be passed to the function.

## Join
You know what this is.

## Mutex
We can instantiate mutexes, lock them, unlock them, and destroy them. Or trylock them.
There are different types of mutexes:
- Normal mutexes: They are the default type of mutexes. They are not recursive, so if a thread locks a mutex twice, it will deadlock.
- Recursive mutexes: They can be locked multiple times by the same thread. They must be unlocked the same number of times they were locked.
- Error-checking mutexes: They are like normal mutexes, but they check for errors. If a thread tries to unlock a mutex that it didn't lock, it will return an error. If a thread tries to relock a mutex, it will return an error.

Mutexes can be implemented using Test-and-set instrucitons, which is an atomic operation used for trying to modify a resource. If we successfully modified the resource, the test-and-set will return 1, otherwise it will return 0. So by using this we can know if we acquired the lock or not. (We use this in a while loop, so that the tas is retried, but only if we detect that the lock is no longer aquired, by a simple read)
```c
while (tas(&lock) == 1) {
    while (lock == 1) {
        // spin
    }
}
```

### Read-write locks
They are used when we have multiple threads reading a resource and only one thread writing to it. We can use a mutex to protect the resource, but it is inefficient because we are blocking all the threads. So we can use read-write locks, which allow multiple threads to read the resource at the same time, but only one thread to write to it.

## Semaphores
The difference between semaphores and mutexes is that semaphores have no owner. They are counters. They can be used to control access to a resource. They can be used to signal that a resource is available.
- sem_wait: Decreases the semaphore counter. If the counter is 0, it will block.
- sem_post: Increases the semaphore counter. If there are threads waiting, it will unblock one of them.

## Barrier
A barrier is a synchronization point. It is used to make sure that all the threads have reached a certain point before continuing.
It can be implemented using a mutex and a counter. The counter needs to be increased atomically using the mutex. When the counter reaches the number of threads, the threads can continue.

It can be implemented with semaphores too by using them like a mutex, we can make sure that only one thread is increasing the counter at a time.

## Condition variables
Basically we can wait on a certain condition to become true. And we can signal that the condition has become true from a thread, so that the threads stop waiting.

We can implement a barrier with this: We have a condition variable that signals that every thread has reached the barrier, which will be broadcasted when a thread sees that the counter has reached the number of threads.

## Starvation
When a thread is capable of continuing its execution but it is not allowed to do so because of the lack of resources.