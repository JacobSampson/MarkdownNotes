# Microprocessor Architecture

## Instruction Set Architecture

## CISC

* Fewer instructions
* More complex hardware

### Y86-64

**Move Operations**

| Operation | Command |
| :--- | :--- |
| Register to Register | rrmovq rA, rB |
| Immediate to Register | irmovq V, rB |
| Register to Memory | rmmovq rA, D\(rB\) |
| Memory to Register | mrmovq D\(rB\), rA |

## RISC

* More instructions
* Simpler hardware
* More registers

### MIPS

**Registers**

* 32 available

**Instructions**

R-Type

I-Type

J-Type

Load

* lw, lh, lb
* _Sign extentsion_
  * lbs, lhs, lbu, lhu

Store

Architecture

1. Instruction set
2. Architecture set

Microarchitecture

1. Data-path
   * Operates on words of data
   * Includes memories, registers, ALU, muxes...
   * 
2. Control
   * Get current instruction from data-path and tell how to execute

Control

Data Bus

Address Bus

## Instruction Execution

### Classical

1. Fetch
2. Decode
3. Read
4. Execute
5. Write back

**Single-cycle Design**

* All 5 stages execute in one cycle
* Clock cycle time set according to worst-case instruction execution time
* Execution time = \# instructions  _\(cycles / instruction\)_  \(seconds / cycles\)

