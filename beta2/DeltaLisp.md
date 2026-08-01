# DeltaLisp

DeltaLisp is an untyped Lisp made for use in Delta Kernel and Voidshell.

# Syntax
This section will detail on the basic Syntax of Delta Kernel.

## Parameter Separation
Parameters in a function are separated by spaces (" ").

## Data types
As mentioned above, Delta Kernel is an untyped language. However, there are still some basic datatypes that is used.

### Unquoted String (uStr)
Used in function names and strings that do not contain spaces. Usage in function params are discouraged for better code readability. It can also be used to create blank variables (`(set var "")`)
Example: `(print)'

### String (str)
Strings are text surrounded by double apostrophes. This allows the usage of text containing space. It can also be used to call a function.

## Built-in Functions

### print
Adds the 1st parameter into the console. Returns printed text.
Usage: `(print text_to_print|str/uStr)`

### input
Uses Scratch's "ask" function with the 1st parameter. It returns content user types in the input box.
Usage: `(input prompt|str/uStr)

### Basic Arithmetic
(+), (-), (*), (/) performs basic arithmetic on the 2 inputs, and returns the result. Results are based on the respective Scratch functions, and thus no error handling is included. Please note that (+) does **not** join strings together.
Usage: `(+ val_1|str/uStr val_2|str/uStr)`

### join
Returns the the 2 inputs joint together.

### exit
Exits the DeltaLisp REPL

### set
Sets the value of a variable. The variable will automatically be created if no variable of such name exists. (set) returns the new value of the variable.
Usage: `(set var_name|str/uStr var_value|str/uStr)`

### rmvar
Removes the specified variable and returns the variable name. Throws an error if variable does not exist.
Usage: `(rmvar var_name|str/uStr)`

## get
Gets the value of the specified variable. Throws an error if variable does not exist.
Usage: `(get var_name|str/uStr)`
