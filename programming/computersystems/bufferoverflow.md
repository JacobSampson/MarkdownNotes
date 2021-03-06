# Buffer Overflow

## Memory layout

**Stack**

* Runtime stack
  * Local variables

**Heap**

* Dynamically allocated
  * `malloc`, `calloc`, `new`

**Data**

* Statically allocated data

**Text/Shared Libraries**

* Executable machine instructions
* Read only

## Buffer Overflow

Exceeding the memory size allocated for an array

* _Unchecked lengths on string inputs_
* _Particularly for bounded character arrays on the stack \(stack smashing\)_

Can inject code into padded region of allocated memory

**Worm**

* Can run by itself

**Virus**

* Added onto exiting code

### Attacks

1. Avoid overflow vulnerabilities in code
   * Check argument lengths...
2. System-level protections
   * Randomized stack offsets
   * Nonexecutable code segments
     * Mark as _read-only_ or _writable_ and _non-executable_...
3. Stack canaries
   1. Place special value on stack just beyond buffer
   2. Check for corruption before exiting function

**Return-oriented Programming Attacks**

Strategies

* Use exiting code
* String together fragments to achieve overall desired outcome
* _Does not overcome stack canaries_
* Construct program from _gadgets_
  * Sequence of instructions ending in `ret`
  * Code positions fixed from run to run
  * Code is executable

