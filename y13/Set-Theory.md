### Sets
 
Inf hotel paradox – It emphasises that although its infinite it can be counted. Every person is given a room from room 1, so the person is n and room number is n + 1. 


What is a set:  (Uses curled braces) 

A set is a well-defined collection of objects. 
    > Objects in the sets are members or elements 
    > A set is unordered 
    > Each member in a set is unique 
A set is usually denoted by a capital letter 
    > A member is usually denoted by a lower case 


Example: C = {red, orange, yellow, green, blue, indigo, violet} 

<br><br>

**Why sets?**

It formalises the idea of grouping objects together and viewing them as a single entity 
This way, a set becomes an abstraction
The laws governing sets from part of the basis for Boolean algebra
Many programming languages support sets as an abstract data type

O = {1, 3, 5, 7, 9} 

D = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100} 

 
Empty Set – {} – A set with no members
There is only one empty set 

 

If S is a set, then the expression x∈S means ‘x is a member of the set S’ 

<br><br>

### **Set Comprehension:** 

A set can be defined by stating the properties held by the members, but not by the non-members 

‘|’ = such that 

S = { x | x ∈ N ∩ x is even } 

Compact version: 

S = { x ∈ N | x is even } 
 

<br><br>

### **Set Operations:** 

![[Pasted image 20251025161548.png]]

**Union**: Combines two or more sets to create a new set containing all elements from the original sets.  Set of all members that are in A or B or in both.  

![[Pasted image 20251025161759.png]]
**Intersection:**
Returns a new set containing only the elements that are common to the original sets. Set of all members in both A and B.  

 
**Difference:**
Returns a new set containing only the elements that are in one set but not in the other. Set of all members that are in A but not B. 

 

Examples: 

A = {t,e,a,m}  B = {h,e,a,t}  C = {h,a,m} 

Union: A U C => {t,e,h,a,m} 

Intersection: B n A => {e,a, t} 

Difference: B \ A => {h} 

<br><br>


### Subsets

A is a subset of B when every member of A is also a member of B 

A is not a subset of B if atleast tone member of A is not a member of B 

A is a proper subset of B, when A is a subset of B but A != B 

  

### Cartesian Product 

The cartesian product of two sets A and B is the set of all the **ordered pairs** (a, b), such that a is an element of A and b is an element of B 

Cartesian product notation: 
A x B  =>  read as ‘A cross B’ 

1. A = {1,2} and B = {4,8}
   What is A X B? 
   A X B = {1,4}, {1, 8}, {2, 4}, {2, 8} 
<br><br>
 

### Cardinality 

The cardinality of a finite set is the number of elements in a set
The cardinality of a set A is denoted by |A| 
The cardinality of the set A, where A = {2,4,6,8} is 4 

 
**Finite set**: Contains an exact number of distinct members
The cardinality of a finite set is the number of members in the set 

 

**Infinite Set:** Contains an infinite number of distinct members 
A countably infinite set is one whose members can be counted using the infinite set N. 
