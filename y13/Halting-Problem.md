## Halting Problem

**Computable** -> A problem is defined as being computable if there is algorithm that can solve every instance of it in a finite number if steps
<br><br>

Limits are imposed by:
- Algorithmic complexity
- Hardware
<br><br>

**Tractable Problem** -> A problem that has a polynomial-time solution or better is called a tractable

**Intractable** -> A problem that does not have a polynomial time solution
<br><br>
Time complexities in order:
1. Constant   $O(1)$
2. Logarithmic  $O(logn)$
3. Linear   $O(n)$
4. Polynomial   $O(x^n)$
5. Exponential  $O(x^n)$
6. Factorial  $O(n!)$
<br><br>

#### Heruistic Method 

A heuristic approach is one which tries to find a solution which may not be perfect, but which is adequate for its purpose
<br><br>

### The Halting Problem

This is the problem of determining for a given input, whether a program will finish running or continue for ever

It is not possible to devise a program H which can show without running the program that, given any program and its inputs, it will halt or continue forever

It is, however, often possible to show that given a specific algorithm it will halt for any input

**The significance of the problem -> There are some problems that cannot be solved by computer**
