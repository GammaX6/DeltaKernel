# DeltaLisp
DeltaLisp is an untyped Lisp made for use in Delta Kernel and vsh.

# Syntax
Parameters in a function are separated by space characters (" "). Strings (see below) can be used to counter this. The backslash is used as an escape character.

Unlike Scratch, Delta Kernel used 0-based indexing. This means that the first item of a list or string is 0, not one. For example, running `(c "hello" 1)` will output `e` instead of `h`.

## Data Types
Although DeltaLisp is an untyped language, there are still some basic datatypes used:

### Unquoted String (uStr)
Used in function names and strings that do not contain spaces. Usage in function params are discouraged for better code readability.
Example: `"print"` and `"hello"` in `(print hello)`

### String (str)
Strings are text surrounded by double apostrophes. This allows the usage of text containing space. It can also be used to call a function.
Example: `"hello world'` in `(print "hello world")`
Note that the function name above, `print` is a uStr. It is not recommended to use strings as function names to avoid confusion.

### List (list) (_planned_)
Lists are strings starting and ending with square brackets.
Example: `"["hello", "world"]"`

**Lists are under development and description from above is subjected to heavy change**

# Built-in Functions
Functions built into DeltaLisp.

## Basic Functions

### print
Adds the 1st argument into the console. Returns printed text. Not to be confused with [(say)](#say).
Usage: `(print text_to_print)`

### say
Displays text in argument 1 inside a speech bubble. Not to be confused with [(print)](#print).

### input
Uses Scratch's "ask" function with prompt being the 1st argument. It returns content user types in the input box.
Usage: `(input prompt)`

## Arithmetic Operators
Used to perform standard mathematical calculations.

### Basic Arithmetic
`(+)`, `(-)`, `(*)`, `(/)` performs basic arithmetic on the 2 inputs, and returns the result. Results are based on the respective Scratch functions, and thus no error handling is included. Please note that (+) does **not** join strings together (Use [`(join)`](#join) instead).
Usage: `(+ val_1 val_2)`

### Exponent
Calculates the value of argument 1 raised to the exponent of argument 2. Uses the following formula:
$$
\text{power} = 10^{\text{exp} \cdot \log(\text{base})}
$$
Usage: `(** base exp)`

### Floor Dividion
Divides the 1st argument by the second and rounds the quotient down to the nearest integer.
Usage: `(// dividend divisor)`

## Modulo
Performs a modulo operation on the two arguments. Returns NaN if either argument is not a number.
Usage: `(% dividend divisor)`

## Power
Raises the first argument to the power of the second argument. Functionally identical to [(**)](#p).
Usage: `(pow base exp)`

## Advanced Math
Contains functions not in arithmetic.

### math.abs
Returns the absolute value of a number.
Usage: `(abs target)`

### math.floor
Returns the floor of a number.
Usage: `(math.floor target)`

### math.ceil
Returns the ceiling of a number.
Usage: `(math.ceil target)`

### sqrt
Returns the square root of a number.
Usage: `(math.sqrt target)`

### math.nan
Returns "NaN"
Usage: `(math.nan)`

## Comparison Operators
Used to compare two values. They always return a boolean, `true` or `false`.

### Basic Comparison Operators
These return either "true" or "false" based on the operands.
They include `(==)`, `(!=)`, `(>)`, `(<)`, `(>=)`, `(<=)`.
Usage: `(== val_1 val_2)`

## Logical Operators
Used to combine conditional statements.

### and
Returns true only if both inputs are true, outputs false otherwise.
Usage: `(and bool bool)`

### or
Returns true if one or more inputs is true, outputs false otherwise.
Usage: `(or bool bool)`

### not
Reverses the Boolean and returns it. Outputs the input if it is not `true` or `false`.
Usage: `(not bool)`

## Membership Operators
Used to test if the input contains a specific value.

### in
Checks whether the 2nd argument contains the first and retuns a boolean.
Usage: `(in element container)`

### not_in
Checks whether the 2nd argument does not contains the first and retuns a boolean.
Usage: `(not_in element container)`

## String Functions
Functions to manipulate, format, inspect, and transform strings.

### Concatenation
Concatenates the 2 arguments.
Usage: `(. str_1 str_2)`

### Character Lookup
Retrieves the character at the specified 0-based index.
Usage: `(c str idx)

### String Slices
Extracts a substring from argument 1, starting at index specified by argument 2 and ending at that of argument 3.
Usage: `(: string start_idx end_idx)`

### len
Gets the length of a string.
Usage: `(len str)`

## Assignment Operators
Used to assign variables.

### set
Sets the value of a variable. The variable will automatically be created if no variable of such name exists. (set) returns the new value of the variable.
Usage: `(set var_name var_value)`

### rmv
Removes the specified variable and returns the variable name. Throws an error if variable does not exist.
Usage: `(rmv var_name)`

### get
Gets the value of the specified variable. Throws an error if variable does not exist.
Usage: `(get var_name)`

## Pen Functions

### pen.down
Places the pen on the screen.
Usage: `(pen.down)`

### pen.up
Lifts the pen off the screen.
Usage: `(pen.up)`

### pen.clear
Clears all pen drawings on the screen.
Usage: `(pen.clear)`
