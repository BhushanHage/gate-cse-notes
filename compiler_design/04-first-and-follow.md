# Chapter 4: FIRST and FOLLOW Sets

## 1. Intuition
The FIRST and FOLLOW sets are essential concepts in compiler design, particularly in the context of syntax analysis and parsing. The FIRST set provides insight into what terminals can appear at the beginning of a string derived from a non-terminal, while the FOLLOW set indicates what terminals can appear immediately to the right of a non-terminal in some sentential form.

## 2. Basic Concepts
- **FIRST(X)** for a grammar symbol X is defined as the set of terminals that begin the strings derivable from X.
- **FOLLOW(A)** for a non-terminal A is the set of terminals that can appear immediately to the right of A in some sentential form, including the end of the string (denoted by $).

## 3. Detailed Explanation
- **Calculating FIRST**:
  1. If X is a terminal, then FIRST(X) = {X}.
  2. If X → ε, then ε is in FIRST(X).
  3. If X is a non-terminal, then you must look at the productions of X: for each production, derive the FIRST sets of the resulting symbols.

- **Calculating FOLLOW**:
  1. If A is the start symbol, then $ is in FOLLOW(A).
  2. If there is a production A → αBβ, then everything in FIRST(β) except for ε is in FOLLOW(B).
  3. If ε is in FIRST(β), then everything in FOLLOW(A) is also in FOLLOW(B).

## 4. Diagrams
- A visual diagram explaining the relationships between productions and their FIRST and FOLLOW sets can aid understanding. [Insert a diagram here showing a parsing table and its construction using FIRST and FOLLOW sets.]

## 5. Examples  
1. Given a grammar with the following productions:
   - E → T E'
   - E' → + T E' | ε
   - T → F T'
   - T' → * F T' | ε
   - F → ( E ) | id

   **FIRST sets**:  
   FIRST(E) = FIRST(T) = FIRST(F) = {(, id}  
   FIRST(E') = {+, ε}  
   FIRST(T') = {*, ε}  

   **FOLLOW sets**:  
   FOLLOW(E) = {), $}  
   FOLLOW(E') = {), $}  
   FOLLOW(T) = {+, ), $}  
   FOLLOW(T') = {+, ), $}  
   FOLLOW(F) = {*, +, ), $} 

## 6. Tables/Comparison  
| Symbol | FIRST           | FOLLOW         |
|--------|-----------------|----------------|
| E      | {(, id}        | {), $}         |
| E'     | {+, ε}         | {), $}         |
| T      | {(, id}        | {+, ), $}      |
| T'     | {*, ε}         | {+, ), $}      |
| F      | {(, id}        | {*, +, ), $}   |

## 7. GATE Focus
Understanding FIRST and FOLLOW sets is crucial for GATE aspirants, as questions often target syntax analysis and parsing efficiency. Expect concepts related to the determination of parsing tables.

## 8. PYQ Insight
In previous GATE exams, questions have directly tested students' abilities to compute these sets, usually providing a grammar and asking to identify FIRST or FOLLOW for certain non-terminals.

## 9. Shortcuts & Tricks
- For calculating FIRST sets, remember that if a non-terminal directly derives a terminal, it's straightforward; utilize ε carefully.
- In FOLLOW sets, always check the start symbol and remember to include FOLLOW information from productions leading to ε derivation.

## 10. Common Mistakes
- Overlooking ε in FIRST sets leading to misplaced terminal predictions.
- Misjudging FOLLOW sets, especially not including the start symbol’s FOLLOW.

## 11. Practice Questions
1. Calculate the FIRST and FOLLOW sets for the given grammar.
2. Determine the parse table using the constructed FIRST and FOLLOW sets.
3. Provide a grammar and ask for the predictive parsing decision based on FIRST/FOLLOW sets.

## 12. Quick Revision Notes
- FIRST sets indicate terminals that can start strings derived from non-terminals.
- FOLLOW sets indicate possible terminals to appear after non-terminals in strings.
- Both sets are critical for constructing parsing tables and ensuring syntax correctness in compilation.