#### What is it

It's a system level data structure
Provides the mechanism for parameters and return the addresses to subroutines
In high level programming languages, the use of the call stack is hidden from the programmer

Calls to subroutines are executed as follows:
- The parameters are saved onto the stack
- The address to which execution return after the end of the subroutine

Subroutines are executed as follows:

**Stack Frame**:
Top of stack

(stack frame for sub2)
Local vars for sub2
return address
parameters for sub2

(stack frame for sub1)
Local vars for sub1
return address
parameters for sub1
