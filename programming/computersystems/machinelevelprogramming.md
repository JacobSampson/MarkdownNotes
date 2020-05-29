# Machine Level Programming

Complex Instruction Set Computer \(CISC\)

Reduced Instruction Set Computers \(RISC\)

**Intel x86 Processors**

* CISC

### Architecture

* Instruction set architecture
* One needs to understand to write assembly/machine code

### Microarchitecture

* Implementations of the architecture
  * Cache sizes, core frequency

### Code Forms

Machine Code: Byte-level programs

Assembly Code: Text representation of machine code

**Compilation**

1. C Program _text_
2. Asm program _text_
3. Object program _binary_
4. Executable program _binary_

## Assembly

### Data Types

* Integer: data of 1, 2, 3 or 8 bytes
  * Data values
  * Addresses
* Floating point: 4, 8, or 10 bytes
* Code: Byte sequences encoding series of instructions
* No aggregate types \(arrays, structures\)

### Operations

* Arithmetic operations
* Transfer data between memory and register
  * Load data from memory to register
  * Store register data to memory
* Transfer control
  * Unconditional jumps to/from
  * Conditional branches

`()`: Putting into memory location addressed by the `%`

`objdump -d`: Displays code as assembly

`gdb sum`, `disassemble`, `x/14xb sumstore`

**x86-64 Integer Registers**

| Register | Description | **Bytes 0-3** | **Bytes 0-1** | **Byte 0** |
| :--- | :--- | :--- | :--- | :--- |
| %rax | Return value | %eax | %ax | %al |
| %rcx | 4th arg | %ecx | %cx | %cl |
| %rdx | 3rd arg | %edx | %dx | %dl |
| %rbx |  | %ebx | %bx | %bl |
| %rdi | 1st arg | %edi | %di | %dil |
| %rsi | 2nd arg | %esi | %si | %sil |
| %rsp | Stack pointer | %esp | %sp | %spl |
| %rbp | Base pointer | %ebp | %bp | %bpl |
| %r8-15 | Last args/General purpose | %r8-15d | %r8-15w | %8-15b |

### Operands

#### Types

* Immediate: Constant integer data
  * `$`
* Register: One of 16
  * `%`
* Memory: 8 consecutive bytes of memory at address given by register

`movq`

* Cannot do memory to memory transfers with a single instruction
* * 

#### Complete Memory Addressing Modes

* Most General Form D\(Rb,Ri,S\): Mem\[Reg\[Rb\]+S\*Reg\[Ri\] +D\]
  * D: Constant displacement of 1, 2, or 4 bytes
  * Rb: Base register: Any of 16 integer registers
  * Ri: Index registers: Any except `%rsp`
  * S: Scale 1, 2, 4, or 8
* Special Cases
  * \(RB,Ri\): Mem\[Reg\[Rb\]+Reg\[Ri\]\]
  * D\(Rb,Ri\): Mem\[Reg\[Rb\]+Reg\[Ri\]+D\]
  * \(Rb,Ri,S\): Mem\[Reg\[Rb\]+S\*Reg\[Ri\]\]

`leaq src, dst`: set `dst` to address

| Command | Format | **Computation** |
| :--- | :--- | :--- |
| addq | Src,Dest | Dest + Src = Dest += Src |
| subq | Src,Dest | Dest - Src = Dest -= Src |
| imulq | Src,Dest | Dest = Dest \* Src |
| salq | Amt,Dest | Dest = Dest &lt;&lt; Amt _Also called shlq_ |
| sarq | Amt,Dest | Dest = Dest &gt;&gt; Amt _Arithmetic_ |
| shrq | Amt,Dest | Dest = Dest &gt;&gt; Amt _Logical_ |
| xorg | Src,Dest | Dest = Dest ^ Src |
| andq | Src,Dest | Dest = Dest & Src |
| orq | Src,Dest | Dest = Dest \| Src |

## Structured Programming

### Condition Codes

**Implicit**

* Set by arithmetic operations
* _Not_ set by `leaq` instruction

**Explicit**

* `cmpq b, a`
  * Like computing `a - b​` without setting destination
* `testq b, a`
  * Computing `a & b`

| Symbol | Description |
| :--- | :--- |
| CF | Carry Flag \(unsigned\) |
| ZF | Zero Flag |
| SF | Sign Flag \(signed\) |
| OF | Overflow Flag \(signed\) |

**Reading**

* set_x_ instructions

### Conditional

**Jumping**

* j_x_ instructions

**Moves**

* cmove_x_ instructions

## Procedure Calls

### Passing Control

### Passing Data

### Managing Local Data

_Stack-based_

* Stack allocated in frames
  * Need place to store arguments, local variables, and return pointer

`rbp`: Base pointer

`rsp`: Stack pointer

Caller: Calls the function

* _Caller Saved_: Caller saves temporary values in its frame before using

Callee: Function that is called

* _Callee Saved_: Callee saves temporary values in its frame before using
  * Callee restores them before returning to caller

### Recursion

## Structures

### Pointer Arithmetic

* Adding to a pointer increments by pointer type size

### Multidimensional Arrays

### Structured Data

* Block of memory holding all fields
  * Ordered according to declaration

**Alignment**

* Fields in structure may be aligned to a multiple based on the type size
  * Primitive data type required _k_ bytes
  * Addresses must be a multiple of _k_
* Structures
  * _k_ is the largest field

