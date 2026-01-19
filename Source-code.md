## 1. Source Code

**Source code** is a program written by a programmer in a programming language.  
It **cannot be directly executed by the CPU**.

Key points:
- CPUs can only execute **machine code**
- Source code must be **translated** before execution
- Source code is:
  - Human-readable
  - Portable between systems (before translation)
  - Written using formal syntax rules

---

## 2. Programming Languages

### Machine Code
- Lowest-level language
- Written in **binary (0s and 1s)**
- Directly understood by the processor
- **Processor dependent**
- Extremely difficult for humans to read or write

---

### Low-Level Languages

#### Assembly Language
- Uses **mnemonics** (e.g. ADD, LOAD)
- Closely related to machine code
- One-to-one correspondence with machine instructions
- Platform and processor specific
- Requires an **assembler** to translate it

Advantages:
- Efficient use of hardware
- Fast execution

Disadvantages:
- Difficult to write
- Hard to maintain
- Not portable

---

### High-Level Languages

Examples:
- Python
- Java
- C#
- Visual Basic
- PHP

Characteristics:
- More abstract from hardware
- Easier to read, write, and maintain
- Use keywords such as:
  - if
  - while
  - for
  - print
- Follow strict **syntax rules**

Advantages:
- Faster development
- Easier debugging
- Portable across platforms (before translation)

Disadvantages:
- Require translation
- Less direct control over hardware

---

## 3. Integrated Development Environments (IDEs)

An **IDE** is software that helps programmers develop programs more efficiently.

Common IDE features:
- Syntax highlighting
- Auto-completion
- Error detection
- Debugging tools
- Breakpoints
- Step-through execution

IDEs help:
- Reduce syntax errors
- Speed up development
- Improve code quality

---

## 4. Translation and Execution

### Why Translation Is Needed

- The CPU **only understands machine code**
- Source code must be translated into **binary instructions**
- Translation produces **machine-executable code**

---

## 5. Machine Code and Object Code

### Machine Code
- Binary instructions executed directly by the processor
- Processor dependent
- Different CPUs require different machine code

---

### Object Code

- Produced by a compiler or assembler
- Usually not yet a complete program
- May reference external libraries

A **linker**:
- Combines multiple object files
- Resolves external references
- Produces a final executable file

Exam note:  
Object code often requires linking before execution.

---

## 6. Types of Translators

There are **three main types**:
1. Compiler
2. Interpreter
3. Assembler

---

## 7. Compilers

A **compiler** translates the **entire source program** into machine code **before execution**.

### Compilation Process

1. Lexical analysis  
   - Breaks source code into tokens  
   - Removes comments and whitespace  

2. Syntax analysis  
   - Checks grammar and structure  
   - Builds a parse tree  
   - Detects syntax errors  

3. Semantic analysis  
   - Checks meaning  
   - Verifies variable declarations and data types  

4. Code generation  
   - Produces machine code or object code  

5. Optimisation  
   - Improves efficiency  
   - Reduces execution time and memory usage  

---

### Compilation Errors

- All errors are reported **after compilation**
- If errors exist:
  - Program will not run
  - Source code must be corrected
  - Entire program must be recompiled

---

### Characteristics of Compiled Programs

- Faster execution
- No translation required at run time
- Executable is platform specific
- Source code is protected

---

## 8. Interpreters

An **interpreter** translates and executes code **line by line**.

Process:
1. Reads one line
2. Checks syntax
3. Translates to machine code
4. Executes immediately

---

### Error Handling

- Syntax errors stop execution immediately
- Errors are reported as soon as they occur
- Runtime errors cause the program to crash

---

### Characteristics of Interpreted Programs

Advantages:
- Immediate error reporting
- Easier debugging
- Faster development cycle

Disadvantages:
- Slower execution
- Interpreter must be installed
- Uses more memory

---

## 9. Bytecode and Virtual Machines

Many modern languages use **bytecode**.

Process:
1. Source code compiled into bytecode
2. Bytecode executed by a **virtual machine (VM)**

Benefits:
- Faster than pure interpretation
- Platform independent
- Example: Java Virtual Machine (JVM)

---

## 10. Compiler vs Interpreter

### Compiler

Advantages:
- Faster execution
- Optimised code
- No translator needed at run time
- Source code protection

Disadvantages:
- Errors shown after compilation
- Recompilation required after changes
- Platform dependent

---

### Interpreter

Advantages:
- Immediate error feedback
- Easier debugging
- Platform independent (with interpreter)

Disadvantages:
- Slower execution
- Interpreter required
- Higher memory usage

---

## 11. Assemblers

An **assembler** translates **assembly language** into machine code.

Characteristics:
- One-to-one instruction translation
- Platform specific
- Removes comments
- Replaces symbolic labels with memory addresses

Compared to compilers:
- Simpler translation
- Less optimisation
- More hardware control

---


