# Memory

## Random-Access Memory \(RAM\)

* Basic storage unit is a _cell_ \(one bit per _cell_\)

### Volatile

SRAM: Static RAM

* 4 or 6 transistors per bit
* 1x access time, 100x cost
* No refresh, EDC \(maybe\)
* Cache memories

DRAM: Dynamic RAM

* 1 transistor per bit
* 10x access time, 1x cost
* Refresh, EDC
* Main memories, frame buffers

### Nonvolatile

* Retain memory if powered off
* Types
  * ROM: Read-only memory
  * PROM: Programmable ROM
  * EPROM: Erasable TOM
  * EEPROM: Electronically erasable ROM
  * Flash memory: EEPROMs with partial \(block-level\) erase capability
* Uses
  * Firmware
    * BIOS
    * Controllers for disks
    * Network cards
  * SSDs
  * Disk caches

## Memory

* Address: Indicates which _row_ of memory is read/written \(location\) $2^k$ for $k$ bits
* Data: Value read/written \(n-bits\)
* Word: Size of a row of data \(n-bits\)
* Depth: Number of rows
* Width: Number of columns
* Wordline: Assert based on address  to activate bit cells in a row
* Bitline: Kept at Z; when wordline is activated, drive to 1 or 0 by bit cell to read
  * When written, drives bit cell high or low

#### Static RAM

* Does not need refreshing
* Bit store in cross-coupled inverters
* Inverters can restore value if noise interferes
* _6 transistors per bit_

#### Dynamic RAM

* Bit stored as absence or presence of charge on a capacitor
* Reading destroys data
  * Must be rewritten
* must be refreshed every few milliseconds due to leaking charge

#### Traditional Bus Structure

* Connecting CPU and memory

Bus: Collection of parallel wires that carry address, data, and control signals

* Typically shared by multiple devices

#### Locality

* _Programs tend to use data and instructions with addresses near or equal to those they have used recently_
* Temporal locality
  * Recently referenced items are likely to be referenced again in the near future
* Spatial locality
  * Items with nearby addresses tend to be referenced close together in time

### Memory Cache

* Registers, L1 cache \(SRAM\), L2 cache \(SRAM\), L3 cache \(SRAM\), main memory \(DRAM\), local secondary storage \(local disks\), remote secondary storage \(e.g. web servers\)

Cache: Smaller, faster storage device that acts as a staging area for a subset of the data in a larger, slower device.

#### Cache Misses

* Cold \(compulsory\) miss
  * The cache is empty
* Conflict miss
  * Multiple data objects map to the same block
* Capacity miss
  * Occurs when the set of active cache blocks \(working set\) is larger than the cache

#### Page Table

* Array of page tables entries \(PTEs\) that maps virtual pages to physical pages
* Page hit: Reference to VM word that is in physical memory
* Page fault: Reference to VM word that is not in physical memory

Thrashing: SUM\(working set sizes\) &gt; main memory size

* Performance meltdown where pages are swapped \(copied\) in and out continuously

## Cache Memory

* Small, fast SRAM-based memories managed automatically in hardware
  * Hold frequently accessed blocks of main memory

Cache size = S  _E_  B

* S: Sets
* E: Lines per set
* B: Bytes per cache block

#### Cache Performance Metrix

Miss rate

* Misses / accesses = 1 - hit rate
  * Typically 3-10% for L1

Hit time

* Time to deliver a line in the cache to the processor
  * Includes time to determine whether the line is in the cache
  * Typically 4 clock cycles for L1 and 10 clock cycles for L2

Miss penalty

* Additional time required because of miss
  * Typically 50-200 cycles for main memory

Read throughput \(read bandwidth\): Number of bytes read from memory per second \(MB/s\)

Memory mountain: Measured read throughout as a fraction of spatial and temporal locality

* Compact way to characterize memory system performance

