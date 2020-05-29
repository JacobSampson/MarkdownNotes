# JavaScript

## JavaScript

### Console

`console.log()`

### Data Types

1. Number
2. String
3. Boolean
4. Null
   * Intentional absence of a value: `null`
5. Undefined
   * Represents absence of value, different than `null`: `undefined`
6. Symbol
   * Unique identifiers, used in more complex coding
7. Object

`var`: cannot start with numbers or keywords

* Automatically assigned `undefined`

`let`: signals a variable can be reassigned a different value

* Automatically assigned `undefined`

`const`: constant

* Throws a TypeError
* _Must_ be assigned a value when declared
  * SyntaxError

`var`: declares a new variable  
`let`: reassign able  
`const`: constant

Short circuit evaluation  
`let <var> = <var> || <value>;`

* Assigns value based on whether a variable evaluates to true

Ternary operator  
`<expression> ? <action> : <action>;`

* If expression evaluates to true, first action executes and second if false

_Variables have an inherent truth value if assigned_ _0, ""/'', null, undefined, and NaN evaluate to false_

### Conditionals

`if`, `else`, `else if`... `switch`

Comparison Operators `<`, `>`, `<=`, `>=` `===`: is equal to `!===`: is NOT equal to

* Can be used with strings

Logical Operators `&&`, `||`, `!`

### Functions

`function <name>(<var>, <var>, ... ) { ... }`

Default parameters `...(<var> = <value>, ...`

Return `return <value>;`

* Default return value is `undefined`

Function expressions

* Assign to variable
  * Common to use `const` for type
* Called an _anonymous function_
* Omit function name
* Cannot be called before declaration

Arrow Functions  
`() =>` `<var> = (<params>) => { ... };`

* Functions with one parameter do not need parenthesis
* Single-line blocks do not require curly braces or a return

### Scope

### Arrays

`[]`

* Can be mixed datatypes
* Can access individual characters in a string \(`<string>[<index>]`\)
* Returns `undefined` if not an index
* Can changed elements in a `const` array

Nested arrays

### Loops

`for (let <var> = 0; <var> < <value>; <var>++) { ... }` `while` `do ... while`

### Iterators

`foreach(<value> => { ...});`  
`map(<value> => { ...});`  
`filter(<value> => { ...});`

* Can pass in a function as the parameter
* Return to assign to element

`.reduce((accumulator, currentValue) => { ... }, <initial value>)`

### Objects

`<object>.<field>`

`<object>[<property name>]`

* Used for fields that have numbers, spaces, or special characters

Functions  
`<function name>: function () { ... }`

Looping  
`for (let <object> in <object>) { ... }`

`this` keyword  
`_`: signifies the object should not be altered

Getters and Setters  
`get <field> { ... }`

De-structured Assignment  
`<var> { <field> } = <obj>`

`Object.assign(object, fields)`

## Code

### General

```javascript
typeof <var>
.name // Original name of function
```

### Strings

```javascript
// Properties
.length

// Methods
.toUpperCase()
.startsWtih('') // boolean
.trim() // Removes whitespace from both sides
```

String Interpolation `${<var>}`

* use backticks: \`\`

### Math and Number

```javascript
// Math
.random() // Random number between 0 and 1
.floor()
.ceil()

// Number
.isInteger()
```

### Arrays

```javascript
// Properties
.length

// Methods
.push(<value>, ...) // Add items to end
.pop() // Removes last item
.shift() // Removes first item
.unshift() // Add item to beginning
.join()
.slice() // Part, first element to last, exclusive
.splice()
.concat()
.indexOf()
```

### Iterators

```javascript
.forEach // Goes through each element
.map // Returns new array
.filter

.findIndex // Index of first element that evaluates to true
.reduce // Returns a single value
```

### Object

```javascript
delete <object>.<field>;
```

### Promises

* Await on response to execute concurrently

`Promise.all([])`: assign array of requests to variable array of responses

