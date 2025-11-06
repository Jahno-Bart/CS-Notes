## Big O Notation
 

It is a measure of the time complexity of an algorithm 
- It is a useful approximation to the actual number of steps in a computation 
**Measures how well an algorithm scales, given larger data sets to act upon, in the worst-case scenario** 
<br><br>

#### Constant Functions 

f(1) is a constant function – no matter how large n is, it stays the same 

In big O notation, we don't care about the constant, only how it scales. Therefore all constants are written as O(1) 
<br><br>

#### Linear Functions 

Takes the form of f(n) = an+ b where a and b are constants 
We only care about the dominant term – ignore b 
Linear complexity is where the execution time rises in direct proportion with the input size 

f(n) is called the order of magnitude function for a linear function And is written O(n) 
<br><br>


#### Polynomial Functions 

Takes the form of $f(n) = an^2 + bn + c$
As n becomes large, the $n^2$ term increases much faster than either of the other terms.  
We only care about the dominant term
$F(n^2)$ is called the order of magnitude function for a polynomial function, and is written O($n^2$) 
<br><br>


#### Logarithmic Functions
Takes the form $f(n) = log_2(n)$ (BASE 2)
Consider $n = 2^f(n)$ as the logarithm $f(n) = log_2(n)$
, f(n) increases very slowly in relation to n

Written O($logn$)

Divide and conquer algorithms work by halving the size of the problem at each pass
<br><br>


#### Pemutations

A permutation of n items is the number of ways the n items can be arranged

There are 2 types:
- Repetition allowed
- No repetition allowed

In a lock with 10 possibilities the problem is O($10^n$)
And that's an Exponential time complexity

When it's a permutation with no repetitions it is a Factorial Time Complexity
<br><br>


#### Time Complexity (Searches and Sorts)

An easy way to think about it is, how many times are we assigning something

- Big O for Linear Search is O(n)
- Big O for Binary Search is O($log_2(n)$)
- Big O for Bubble Sort is O($n^2$)
- Big O for Merge Sort is O(${nlogn}$)

Space Complexity is how much memory is used

- Big O for Linear Search is O(1)
- Big O for Binary Search is O(1)
- Big O for Bubble Sort is O(1)
- Big O for Merge Sort is O(n)




















