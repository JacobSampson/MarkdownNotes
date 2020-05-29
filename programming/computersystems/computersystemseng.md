# Computer Systems Engineering

## C Introduction

### Compiler

`gcc`

​ `-o`: changes the output file name

​ `-Wall`: include warnings

_Optimization_

​ `-O0`: conversion from source code to object code

_Check the first warning/error_

### Basic

```c
#include <stdio.h>
#include "header.h"

int main(void) {
    return 0;
}

void example_function() {

}
```

`#define`: create macros

* Preprocessor effectively does a search and replace
* Best to use to create _CONSTANTS_

Function Declarations: commonly put in the header file

### Primitive Types

#### Integer Types

* `char`: by default, 1 byte
* `short`, `int`, `long`: size is architecture dependent
* `long long`

#### Floating Types

* `float`, `double`
* `long double`

#### Booleans

* false = 0
* true = not-0

### Command Line Arguments

`argc`: number of command-line tokens

`argv`: array of strings, command line tokens

* Program name is `argv[0]`

### Arrays

* No _length_ property
* Size must be known at compile time

### Strings

* Array of characters
* End in `\0` \(null character\)
* `<string.h>`contains useful functions

### Input/Output

#### Printing

`printf(string, var...)`

* `%s`: string
* `%d`: decimal
* `%i`: integer
* `%c`: character

`fprintf(file, string, var...)`

* `printf` equivalent to `fprintf(stdout...)`

### Struct

* Analogous to a class with only public fields
* combine with `typedef` to specify as a type

```c
struct name {
    field;
    field;
};

typedef struct {

} name;

name.field
```

### Pointers

* Variables can contain values \(even a struct\)
* Variables can be a pointer to values \(even a primitive\)

Declare with `int *var`

Dereference to set/check value: `*var = value`

Get the memory address `&var`

`*void` indicates a pointer of no particular type

* Shouldn't pass the whole struct but rather a pointer to a struct
* Access fields with either `(*var).field` or `var->field`

`&`: Reference

`*`: Dereference

## Data Representation and Arithmetic

### Number Systems

Bit: 0 or 1

Nibble: 4-bit binary number

Byte: 8-bit binary number

* Unsigned and signed

#### Decimal

Base 10

* 0-9

#### Binary

Base 2

* 0-1
* Represented as `0b00000000`

#### Octal

Base 8

* 0-7

#### Hexadecimal

Base 16

* 0-9, A-F
* Represented as `0x00`

#### _Conversion_

Division: Divide a number of larger base by the lower base and assign the remainder as the LSB up to the MSB

Summation: Use the positional numbering system to multiply the digit by the power of the position

Substitution: Rule of threes \(binary to octal\), rule of fours \(binary to hex\)...

### Data

#### Byte

* 0-255
* 8 bits
* Two hexadecimal characters

`hexdump -C` shows the bytes of a file in hex

#### Word

* _Word size_: minimal size of integer, memory address
* Word oriented memory organizations
* Addresses specify byte locations by pointing at first byte in word
  * Differ by size of word

#### _Byte Ordering_

Big Endian: least significant byte has highest address

Little Endian: least significant byte has lowest address

#### Strings

* Digit _i_ has code `0x30` + _i_
* Should be null-terminated `\0`

### Bitwise Operators

* Apply to any integral data types
  * `long`, `int`, `short`, `char`

`&`: And

`|`: Or

`^`: XOR

`~`: Not

`<<`: Left shift

* Fill with 0's on the right

`>>`: Right shift

* Logical shift: Fill with 0's on left
* Arithmetic shift: Replicate most significant bit on left

### Logic Operators

`&&`: And

`||`: Or

`!`: Not

## Bitwise

### Unsigned

* Can define integer as unsigned: `12345U`

**Addition**

Sum = A ^ B ^ C

Cout = \(A & B\) \| \(\(A ^ B\) & Cin\)

**Subtraction**

_Check whether first number &lt; second number_

_Check if leftmost carryout is 0_

**Multiplication**

Power of 2

* $u &lt;&lt; k = u \* 2^k$

**Division**

Power of 2

* $u &gt;&gt; k = floor\(u / 2^k\)$
  * Negative divisions floor more negative

**Fractional**

* _Binary point_ is an imaginary decimal point created when dividing numbers
  * Not represented in the binary representation of the digits
* Bits to the right of _binary point_ represent fractional powers of 2
  * Find remainder by taking the binary value of the bits right of the _binary point_ and multiplying by 2 ^ number of shifts?

### Signed

Signed Magnitude: First bit indicates sign

Two's Complement: First bit indicates sign. Negatives are the positive flipped + 1

**Arithmetic**

_Last two carry outs are different if overflow_

_Check if the two numbers have the same sign but the sum has a different sign it's an overflow_

* If mix of unsigned and signed in a single expression, signed values are implicitly cast to unsigned

## Floating Point Numbers

Three parts: $\(-1\)^s M 2^E$

* Sign bit \(s\)
* Significand \(M\): whole part
* Exponent \(E\): exponent part

Precision

* Single: 32 bit float
* Double: 64 bit
* Extended precision: 80 bit \(Intel only\) long double
* Quadruple precision: 128 bits long double, double double...

### Normalized

* Precision limited by fractional bits
* Magnitude limited by exponential bits

**Exponent**

* Encoded as a biased value
* Bias: $2^{k-1} -1$ where k is number of bits in exponent
  * $E = Exp - Bias$

**Significand** \(Mantisa\)

* 1.xxxx
  * 1 is assumed
* Min: 1.0000...
* Max: 1.1111...

### Denormalized

* M = 0.xxxx
* Exponent value = 0
  * $E = 1 - Bias$

**Cases**

* Exp = 0, Frac == 0
* Exp = 0, Frac != 0
* Exp = 111....1, Frac = 000.0
  * Infinity \(+/-\)
* Exp = 111...1, Frac != 000.0
  * NaN

**Rounding**

1. Compute exact results
2. Find closest value
3. Depending on half way
   * Round to nearest if not half way
4. Round to 0 on least significant digit for half-way

Guard: last bit of result

Sticky: OR remaining bits

Round: first bit removed

* Increment if rounded bit and sticky or guard bit

### Multiplication

Sign: `S1 ^ S2`

Significand: $M1 \* M2$

Exponent: $E1 + E2$

* If M &gt;= 2, shift M right, increment E
* If E out of range, overflow
* Round M to fit `frac` precision

