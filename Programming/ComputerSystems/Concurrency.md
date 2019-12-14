# Concurrency

*Classical problem classes*

- Races: Outcome depends on arbitrary scheduling decisions elsewhere in the system
- Deadlock: Improper resource allocation prevents further progress
- Livelock/Starvation/Fairness: External events and/or system scheduling can prevent sub-task progress



#### Iterative Servers

- Process one request at a time
- Server can be blocked by hanging client connection

#### Concurrent Servers

- Multiple concurrent flows to serve multiple clients at the same time

1. Process-based Servers
   - Spawn separate process for each client
2. Event-based
   - Programmer manually interleaved multiple logical flows
   - All flows share the same address space
   - *I/O multiplexing*
3. Thread-based
   - Kernel automatically interleaves multiple logical flows
   - Each flow shares the same address space
   - Hybrid of process-based and event-based



## Processes

### Creating and Terminating

- Running: Either executing or waiting to be executed
- Stopped: Process execution is suspended and with not be scheduled until further notice (signals)
- Terminated: Process is stopped permanently

`pid_t getpid(void`): Returns PID of current process

`pid_t getppid(void)`: Returns PID of parent process



`void exit(int status)`: Terminates with an exit status

- Convention: Normal is 0 and nonzero on error
- Called once but never returns



`int fork(void)`: Returns 0 to the child process, child's PID to parent process

- Called once, returns twice

- Child is almost identical to parent
  - Gets copy of the parent's virtual address space and open file descriptors



### Reaping Child Process

- Performed by parent on terminated child (`wait` or `waitpid`)

- Parent is given exit status information
- Kernel then deleted child process
- If the parent terminates without reaping a child, then the orphaned child will be reaped by `init`process (pid = 1)
  - Only need explicit reaping in long-running processes
    - Shells, servers, etc...

`&`: Run process in background



`int wait(int *child_status)`

- Parent reaps a child
- Suspends current process until one of its children terminates
- Returns PID of the child process that terminated
- If `child_status != NULL` the integer it points to will be set to a value that indicates reasons the child terminated and the exit status



## Threads

- Uses threads instead of processes

- Traditional view of a process
  - Process context
  - Code, data, and stack
- Alternate view of a process
  - Thread + code, data, and kernel context



### Threads vs Processes

#### Similarities

- Each has own logical control flow
- Each can run concurrently
- Each is context switched

#### Differences

- Threads share all code and data (except local stack)
- Threads are somewhat less expensive
  - Process control (creating and reaping) twice as expensive



### Posix Threads (Pthreads) Interface

Pthreads: Standard interface for ~60 functions

`pthread_create`

`pthread_join`

`pthread_self`

`pthread_cancel`

`pthread_exit`: Terminates all threads (`RET` terminates current thread)

`pthread_mutex_init`

`pthread_mutex_[un]lock`



#### Issues

- Must run in "detached" to avoid memory leak
  - A thread is either *joinable* or *detached*
  - *Joinable* thread can be reaped and killed by other threads
    - Must be reaped (`pthread_join`) to free memory resources
  - *Detached* thread cannot be reaped or killed by other threads
    - Resources are automatically reaped on termination
  - Default is joinable
    - `pthread_detach(pthread_self())` to make detached
- Careful about unintended sharing
  - *Passing pointer to main thread's stack*
- All functions must be *thread-safe*



### Summary

**Process-based**

- Hard to share resources, easy to avoid unintended sharing
- High overhead in adding/removing clients

**Thread-based**

- Easy to share resources
- Medium overhead
- Not much control over scheduling
- Difficult to debug
  - Event ordering not repeatable