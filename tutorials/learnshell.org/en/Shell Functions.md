Tutorial
--------

Like other programming languages, the shell may have functions. A function is a subroutine that implements a set of commands and operations. It is useful for repated tasks.

    # basic construct
    function_name {
    command...
    }

Functions are called simply by writing their names. A function call is equivalent to a command. Parameters may be passed to a function, by specifying them after the function name. The first parameter is referred to in the function as $1, the second as $2 etc.

    function function_B {
      echo Function B.
    }
    function function_A {
      echo $1
    }
    function adder {
      echo $(($1 + $2))
    }

    # FUNCTION CALLS
    # Pass parameter to function A
    function_A "Function A."     # Function A.
    function_B             # Function B.
    # Pass two parameters to function adder
    adder 12 56             # 68

Exercise
--------
In this exercise, you will need to write a function called ENGLISH_CALC which can process sentences such as:

'3 plus 5', '5 minus 1' or '4 times 6' and print the results as:  '3 + 5 = 8', '5 - 1 = 4' or '4 * 6 = 24' respectively.

Tutorial Code
-------------
#!/bin/bash
# enter your function code here

# testing code
ENGLISH_CALC 3 plus 5
ENGLISH_CALC 5 minus 1
ENGLISH_CALC 4 times 6

Expected Output
---------------
3 + 5 = 8
5 - 1 = 4
4 * 6 = 24

Solution
--------
#!/bin/bash
# enter your function code here

# testing code
function ENGLISH_CALC {
case $2 in
plus) echo "$1 + $3 = `expr $1 + $3`";;
minus) echo "$1 - $3 = `expr $1 - $3`";;
times) echo "$1 * $3 = `expr $1 \* $3`";;
divide) echo "$1 / $3 = `expr $1 / $3`";;
*) invalid
esac
}

ENGLISH_CALC 3 plus 5
ENGLISH_CALC 5 minus 1
ENGLISH_CALC 4 times 6
