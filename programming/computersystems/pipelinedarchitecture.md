# Pipelined Architecture

## Multi-Processing / Multi-Threading

#### Pipeline Stages

1. Fetch
   * Select current PC
   * Read instruction
   * Compute incremented PC
2. Decode
   * Read program registers
3. Execute
   * Operate ALU
4. Memory
   * Read or write data memory
5. Write back
   * Update register file

$$
Throughput\;(GIPS) = \frac {1\;instruction} {clock\;cycle\;(ps)} * \frac {1000\;ps} {1\;ns}
$$

* Latency is time to complete one instruction start to finish

### Dependencies

#### Data Dependency

* Insert `nop`, but inefficient

#### Control Dependency

* Instruction doesn't transfer control
  * Predict next jump is continue execution
* Procedure call and unconditional jump
  * Predict call/jump location
* Conditional branch
  * Predict branch is taken
    * Typically 60% correct
* Procedure return
  * Don't predict

### Overcoming Pipeline Hazards

**Calculating CPI**

$$
CPI = 1.0 + lp(load\;penalty) + mp(misprediction\;penalty) + rp(return\;penalty)
$$

* Return: 3
* Load: 1
* Misprediction: 2

$$
Penalty = Instruction\;frequency * Condition\;frequency * Stalls/Bubbles
$$

### Summary

Data Hazards

* Most handled by forwarding
  * No performance penalty
* Load/use hazards require one cycle stall

Control Hazards

* Cancel instructions when detect mispredicted branch
  * Two clock cycles wasted
* Stall fetch stage while `ret` passes through pipeline
  * Three clock cycles wasted

## Advanced Architecture

* Branch prediction works off a state machine transitioning from a continuous history of one path or another
* Small stack of return addresses that mirrors the program stack

