# Exception Control Flow

## Exceptions

Control Flow: CPU reading and executing a sequence of instructions

### Exceptional Control Flow

**Low Level Mechanisms**

1. Exceptions
   - Change in control flow in response to a system event
   - Implemented using combination of hardware and OS software

**Higher Level Mechanisms**

1. Process context switch
   - Implemented by OS software and hardware timer
2. Signals
   - Implemented by OS software and hardware timer
3. Nonlocal jumps
   - Implements by C runtime library



**Exception**: Transfer of control to the OS kernel in response to some event

**Asynchronous Exceptions (Interrupts)**: Caused by events external to the processor

**Synchronous Exceptions**: Caused by events that occur as a result of executing an instruction

- Traps
  - Intentional
  - *System calls, breakpoint traps, special instructions*
  - Returns control to next instruction
- Faults
  - Unintentional but possibly recoverable
  - *Page faults, protection faults, floating point exceptions*
  - Either re-executes faulting instruction or aborts
- Aborts
  - Unintentional and unrecoverable
  - *Illegal instructions, parity error, machine check*
  - Aborts current program



## Handling Interrupts



## Processes

Process: Instance of a running program

1. Logical control flow
   - Each program seems to have exclusive use of CPU
   - Provided by kernel mechanisms called *context switching*
2. Private address space
   - Each program seems to have exclusive use of main memory
   - Provided by kernel mechanisms called *virtual memory*

### Multiprocessing

- Illusion of running many processes simultaneously
- Single processor executes multiple processes concurrently
  - Process executions interleaved
  - Address spaces managed by virtual memory system
  - Register values for nonexecuting processes saved in memory

#### Modern

- Multicore processors
  - Multiple CPUs on single chip
  - Shared main memory (and some caches)
  - Can execute a separate process

#### Concurrent Processes

- Each process is logical control flow
- Two processes run *concurrently* if their flows overlap in time
  - Otherwise, *sequential*
- Control flow passes from one process to another via a *context switch*

