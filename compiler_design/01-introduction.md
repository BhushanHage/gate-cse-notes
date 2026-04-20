# Chapter 1: Introduction & Phases of Compiler

## 1. INTUITION (Very Simple Start)

Think of a **compiler** like a **translator at the United Nations**.

- A programmer writes a program in **high-level language** like C, C++, Java.
- The computer cannot directly understand this language.
- The compiler acts like a translator:
  - reads the program,
  - understands its meaning,
  - and converts it into **machine code** or an intermediate form.

### Real-life analogy
Suppose you write a recipe in English, but your assistant understands only French.  
A translator converts your English recipe into French so the assistant can follow it.

That is exactly what a compiler does:
- **Source code** = your program
- **Compiler** = translator
- **Target code** = machine-readable code

## 2. BASIC CONCEPTS

### What is a Compiler?
A **compiler** is a program that translates a source program written in one language into another language, usually into machine code.

### Source language
The language in which the program is written initially.  
Example: C, C++, Java, Python.

### Target language
The language produced after translation.  
Example: machine code, assembly code, bytecode.

### Why do we need a compiler?
Because computers understand only:
- binary instructions,
- not human-friendly programming languages.

### Compiler vs Interpreter
A beginner often confuses these. We will distinguish them properly:

- **Compiler**: translates the entire program at once.
- **Interpreter**: translates and executes line by line.

### Important term: Error detection
Compiler also checks:
- syntax errors,
- semantic errors,
- lexical errors.

## 3. DETAILED EXPLANATION

A compiler is not a single-step machine. It works in **phases**.

### Main idea
The compiler breaks the job into smaller parts:
- each phase handles a specific task,
- output of one phase becomes input to the next phase.

This modular design makes the compiler easier to build and debug.

### Phases of a Compiler

A typical compiler has the following phases:

1. **Lexical Analysis**
2. **Syntax Analysis**
3. **Semantic Analysis**
4. **Intermediate Code Generation**
5. **Code Optimization**
6. **Code Generation**

There are also two important supporting activities:
- **Symbol Table Management**
- **Error Handling**

### Compiler Workflow

Source Program -> Lexical Analysis -> Syntax Analysis -> Semantic Analysis -> Intermediate Code Generation -> Code Optimization -> Code Generation -> Target Program

### 1. Lexical Analysis
This phase reads the input character by character and groups them into meaningful units called **tokens**.

Example:
```c
a = b + 10;
```
Tokens:
- `a` → identifier
- `=` → assignment operator
- `b` → identifier
- `+` → plus operator
- `10` → number
- `;` → semicolon

Think: **Characters → Tokens**

### 2. Syntax Analysis
This phase checks whether the token sequence follows the grammar of the language.

Example:
```c
a = b + 10;
```
This is syntactically correct.

But:
```c
a = + b 10;
```
This is not valid syntax.

Think: **Tokens → Structure**

The parser builds:
- parse tree
- syntax tree

### 3. Semantic Analysis
Even if a statement is syntactically correct, it may still be meaningless.

Example:
```c
int x;
x = "hello";
```
Syntax may be okay, but semantically it is wrong because an integer variable is assigned a string.

Think: **Meaning check**

### 4. Intermediate Code Generation
The compiler converts the source program into an intermediate representation, which is easier to optimize and translate.

Example:
```c
a = b + c * d;
```

Intermediate code might be:
```text
t1 = c * d
t2 = b + t1
a = t2
```

### 5. Code Optimization
The intermediate code is improved so that it runs faster or uses fewer resources.

### 6. Code Generation
Finally, the optimized code is converted into target machine code or assembly code.

### Supporting Components

#### Symbol Table
A data structure that stores information about identifiers:
- variable name
- type
- scope
- memory location

#### Error Handler
This component detects and reports errors in the source program.

Possible errors:
- lexical errors
- syntax errors
- semantic errors
- runtime-related issues discovered during compilation

## 4. DIAGRAMS (VERY IMPORTANT)

### A. Compiler Phase Diagram

```text
+------------------+
|  Source Program  |
+------------------+
         |
         v
+------------------+
| Lexical Analysis |
+------------------+
         |
         v
+------------------+
| Syntax Analysis  |
+------------------+
         |
         v
+------------------+
| Semantic Analysis|
+------------------+
         |
         v
+----------------------------+
| Intermediate Code Gen.     |
+----------------------------+
         |
         v
+------------------+
| Code Optimization|
+------------------+
         |
         v
+------------------+
| Code Generation  |
+------------------+
         |
         v
+------------------+
|  Target Program   |
+------------------+
```

### B. Front End and Back End

Front End: Lexical Analysis, Syntax Analysis, Semantic Analysis, Intermediate Code Generation
Back End: Code Optimization, Code Generation

## 5. EXAMPLES

### Simple Example
Statement:
```c
x = a + b;
```

Steps:
1. Lexical analysis: `x`, `=`, `a`, `+`, `b`, `;`
2. Syntax analysis: checks assignment structure
3. Semantic analysis: checks whether `a`, `b`, and `x` are declared and compatible
4. Intermediate code:
   ```text
t1 = a + b
x = t1
```
5. Optimization: may remove unnecessary temporary if possible
6. Code generation: machine instructions

### GATE-level Example
Question type:
> Which of the following is not a compiler phase?

Options may include:
- lexical analysis
- syntax analysis
- linking
- code generation

Correct answer: **linking**

## 6. TABLES / COMPARISON

### Compiler vs Interpreter

| Feature | Compiler | Interpreter |
|---|---|---|
| Translation | Whole program at once | Line by line |
| Speed | Faster execution after compilation | Slower execution |
| Error reporting | Reports errors after scanning whole program | Stops at first error often |
| Output | Object / machine code | No separate object code |
| Examples | C, C++ | Python shell, Ruby interpreter |

### Analysis vs Synthesis

| Phase Type | Purpose | Examples |
|---|---|---|
| Analysis | Break source program into parts | Lexical, Syntax, Semantic |
| Synthesis | Create target program | Optimization, Code generation |

## 7. GATE FOCUS

### 🔥 HIGH weight
- Compiler phases
- Compiler vs interpreter
- Front end vs back end
- Role of symbol table
- Error handling basics

### ⚡ MEDIUM weight
- Output of each phase
- Source to target translation flow
- Intermediate code idea

### ✅ LOW weight
- Historical/compiler implementation details
- Non-exam-specific compiler construction background

## 8. PYQ INSIGHT

GATE often asks:
- identify the phase responsible for a task,
- choose the correct order of compiler phases,
- distinguish compiler from interpreter,
- identify whether a component belongs to front end or back end.

### PYQ-style examples
1. Which phase creates tokens? Answer: Lexical Analysis
2. Which phase checks type compatibility? Answer: Semantic Analysis
3. Which phase is responsible for machine code generation? Answer: Code Generation
4. Which phase uses grammar rules? Answer: Syntax Analysis

## 9. SHORTCUTS & TRICKS

### Easy memory trick for compiler phases:
**L S S I O C**
- Lexical
- Syntax
- Semantic
- Intermediate code generation
- Optimization
- Code generation

Say:
**“Little Students Study In Our College”**

## 10. COMMON MISTAKES

- Confusing syntax with semantics
- Thinking compiler directly generates machine code without intermediate steps
- Mixing up compiler and interpreter
- Forgetting symbol table is a support component
- Assuming linking is part of compiler phases

## 11. PRACTICE QUESTIONS

1. What is the main role of a compiler?
2. Which phase converts source program into tokens?
3. Which phase checks whether identifiers are declared properly?
4. Arrange the compiler phases in correct order.
5. What is the difference between compiler and interpreter?
6. Is linking a compiler phase? Explain briefly.
7. Which phase is responsible for generating intermediate code?
8. What is the role of symbol table?
9. Why is code optimization needed?
10. Give one example of a semantic error.

## 12. QUICK REVISION NOTES

- Compiler translates source code to target code.
- Major phases: Lexical, Syntax, Semantic, Intermediate Code Generation, Optimization, Code Generation.
- Front end = analysis.
- Back end = synthesis.
- Symbol table stores identifier information.
- Error handling is needed in all phases.
- Compiler is not the same as interpreter.

End the chapter with a short note that the next chapter will cover lexical analysis in detail.