# Computing Theory - Comprehensive Lecture Notes

## Table of Contents
1. [Lecture 1: Introduction](#lecture-1-introduction)
2. [Lecture 2: Automata (Finite State Machines)](#lecture-2-automata-finite-state-machines)
3. [Lecture 3: NFA to DFA](#lecture-3-nfa-to-dfa)
4. [Lecture 4: Regular Expressions](#lecture-4-regular-expressions)
5. [Lecture 5: Applications of FA](#lecture-5-applications-of-fa)
6. [Lecture 6: CFG](#lecture-6-cfg)
7. [Lecture 7: CNF](#lecture-7-cnf)
8. [Lecture 8: PDA](#lecture-8-pda)
9. [Lecture 9: CYK Algorithm](#lecture-9-cyk-algorithm)
10. [Lecture 10: Turing Machines](#lecture-10-turing-machines)
11. [Lecture 11: Hierarchy](#lecture-11-hierarchy)
12. [Lecture 12: TM Variations](#lecture-12-tm-variations)
13. [Lecture 13: Complexity](#lecture-13-complexity)

---

## Lecture 1: Introduction

### Learning Outcomes

At the end of this topic, you should be able to:
- Contribute to the achievement of Level 2 learning outcomes
- Meet prerequisite requirements for Level 3 modules
- Understand formal models of computation
- Develop skills in automata, regular expressions, and context-free grammars
- Develop lifelong learning skills for computational capabilities and limitations

### Categories in Theory of Computation

| Category | Description | Focus |
|----------|-------------|-------|
| **Automata Theory** | Study of abstract machines and computational problems | Modeling computation |
| **Formal Language Theory** | Describing languages as sets of operations over alphabet | Language structure |
| **Computability Theory** | Extent to which problems can be solved on a computer | Solvability limits |
| **Complexity Theory** | Efficiency of problem solving | Resource requirements |

### Automata Memory Types

| Memory Type | Description | Example |
|-------------|-------------|---------|
| **None** | Finite state machines | DFA, NFA |
| **Single Stack** | Pushdown automaton | PDA |
| **Semi-infinite Tape** | Turing machine | TM |

### Diagrammatic Representation of Automaton

```
┌─────────────────┐
│   Control Unit │ ← Can be in finite number of states
└────────┬────────┘
         │
         ↓
    Transition Function
```

### Grammars

| Aspect | Description |
|--------|-------------|
| **Purpose** | Specify syntax rules |
| **Components** | Symbols, words, rules |
| **Example Rule** | `<sentence> → <noun-phrase> <predicate>` |
| **Application** | Programming language syntax |

### Languages

| Symbol | Description | Example |
|--------|-------------|---------|
| **L** | Language over alphabet Σ | L = {0, 01, 011, 0111, ...} |
| **Σ*** | Kleene star (all strings including λ) | Σ* = Σ⁰ ∪ Σ¹ ∪ Σ² ∪ ... |
| **Σ⁺** | Kleene plus (all strings excluding λ) | Σ⁺ = Σ* - {λ} |

### Kleene Star vs Kleene Plus

| Operation | Definition | Example |
|-----------|------------|---------|
| **Kleene Star (Σ*)** | All strings including empty string | {λ, a, b, aa, ab, ba, bb, ...} |
| **Kleene Plus (Σ⁺)** | All strings excluding empty string | {a, b, aa, ab, ba, bb, ...} |

### Key Terms

| Term | Definition |
|------|------------|
| **Alphabet (Σ)** | Set of symbols |
| **String** | Finite sequence of symbols from Σ |
| **Language (L)** | Subset of Σ* |
| **Kleene Star** | Σ* = All possible strings including λ |
| **Kleene Plus** | Σ⁺ = All possible strings excluding λ |
| **Grammars** | Rules for generating strings |
| **Automata** | Abstract computational models |
| **Computability** | Fundamental limits of computation |

---

## Lecture 2: Automata (Finite State Machines)

### Finite State Machine (FSM)

| Characteristic | Description |
|----------------|-------------|
| **Memory** | Fixed and very limited |
| **Operation** | Driven by input, halts when input finishes |
| **State** | Current state, changes based on input |
| **Output** | Simple, often accept/reject |

### Components of FSM

| Component | Description |
|-----------|-------------|
| **States** | Instantaneous description of system |
| **Transitions** | Changes between states |
| **Input** | Drives the state changes |
| **Output** | Result (accept/reject) |

### Transition Table

| Component | Description |
|-----------|-------------|
| **Rows** | States |
| **Columns** | Input symbols |
| **Entries** | Next states |
| **Start State** | Marked with arrow |
| **Final States** | Marked with star (*) |

### DFA Definition

A deterministic finite automaton is a quintuple:

M = (Q, Σ, δ, q₀, F)

| Symbol | Meaning |
|--------|---------|
| **Q** | Finite set of states |
| **Σ** | Alphabet (finite set of symbols) |
| **δ** | Transition function (Q × Σ → Q) |
| **q₀** | Initial state (q₀ ∈ Q) |
| **F** | Set of final states (F ⊆ Q) |

### DFA Examples

| Type | Language | States |
|------|----------|--------|
| **Ending with 100** | Strings ending with 100 | q₀, q₁, q₂, q₃ |
| **Starting with aba** | Strings starting with aba | q₀, q₁, q₂, q₃, q₍ |
| **Substring bab** | Strings containing bab | q₀, q₁, q₂, q₃ |
| **Divisible by 3** | Binary strings divisible by 3 | q₀, q₁, q₂ |

### Transition Function Example: Strings ending with 100

| State | 0 | 1 | Meaning |
|-------|---|---|---------|
| q₀ | q₀ | q₁ | Initial |
| q₁ | q₂ | q₁ | Ends with 1 |
| q₂ | q₃ | q₁ | Ends with 10 |
| q₃* | q₀ | q₁ | Ends with 100 (final) |

### NFA Definition

A non-deterministic finite automaton is a quintuple:

M = (Q, Σ, δ, q₀, F)

| Symbol | Meaning |
|--------|---------|
| **Q** | Finite set of states |
| **Σ** | Alphabet |
| **δ** | Transition function (Q × {Σ ∪ ε} → 2^Q) |
| **q₀** | Initial state |
| **F** | Set of final states |

### DFA vs NFA

| Feature | DFA | NFA |
|---------|-----|-----|
| **Transitions** | Exactly one per (state, symbol) | Zero, one, or more |
| **Choice** | Single choice | Multiple choices |
| **Backtracking** | Not needed | May be needed |
| **Determinism** | Deterministic | Non-deterministic |

### DFA vs NFA Examples

```
DFA (Deterministic):          NFA (Non-deterministic):
    A                               A
   ↙↘                             ↙ ↘
  B   C                           B   C
```

### NFA Types

| Type | Description |
|------|-------------|
| **Without ε-transitions** | No epsilon moves |
| **With ε-transitions** | Can transition without reading symbol |

### Key Terms

| Term | Definition |
|------|------------|
| **DFA** | Deterministic Finite Automaton |
| **NFA** | Non-Deterministic Finite Automaton |
| **Transition Function** | Maps (state, symbol) → next state(s) |
| **Initial State** | Starting state (q₀) |
| **Final State** | Accepting state |
| **Deterministic** | One transition per (state, symbol) |
| **Non-deterministic** | Multiple transitions possible |

---

## Lecture 3: NFA to DFA

### NFA to DFA Conversion

| Step | Description |
|------|-------------|
| 1 | Start with NFA's start state as DFA start |
| 2 | For each DFA state, consider possible NFA state sets |
| 3 | Use epsilon closure for transitions |
| 4 | Continue until no new DFA states can be created |

### ε-Closure

| Definition | Description |
|------------|-------------|
| **ε-Closure(q)** | Set of states reachable from q using only ε-transitions |
| **Purpose** | Handle NFA transitions without input symbols |

### Conversion Algorithm

```
For each DFA state (set of NFA states):
  For each input symbol:
    Compute ε-closure of all NFA transitions
    Create new DFA state if unique
```

### Subset Construction

| Concept | Description |
|---------|-------------|
| **DFA State** | Set of NFA states |
| **Power Set** | 2^Q (all possible subsets of Q) |
| **Construction** | Systematic enumeration of reachable subsets |

### Key Terms

| Term | Definition |
|------|------------|
| **ε-Closure** | States reachable via epsilon transitions |
| **Subset Construction** | NFA to DFA conversion method |
| **Power Set** | All subsets of a set (2^Q) |
| **Determinization** | Converting NFA to DFA |

---

## Lecture 4: Regular Expressions

### Regular Expression Definition

A regular expression is a sequence of characters that define a search pattern.

### RE Operators

| Operator | Description | Example |
|----------|-------------|---------|
| **Union (+ or ∪)** | Either X or Y | a + b |
| **Concatenation** | X followed by Y | ab |
| **Kleene Star (*)** | Zero or more repetitions | a* |
| **Kleene Plus (+)** | One or more repetitions | a+ |

### RE to NFA Conversion

| RE | NFA Structure |
|----|--------------|
| **a** | Single symbol NFA |
| **X + Y** | NFA with parallel paths |
| **XY** | NFA with sequential paths |
| **X*** | NFA with loop |

### NFA to RE Conversion (State Elimination)

| Rule | Description |
|------|-------------|
| 1 | Add new initial state with ε-transition |
| 2 | Add new final state with ε-transitions |
| 3 | Eliminate states one by one |
| 4 | Combine paths using RE operators |

### Pumping Lemma for Regular Languages

| Condition | Requirement |
|-----------|------------|
| **For any regular language L** | There exists pumping length n |
| **For any string w** | |w| ≥ n |
| **Can be written as** | w = xyz where:
  1. |xy| ≤ n
  2. |y| > 0
  3. xyⁱz ∈ L for all i ≥ 0 |

### Pumping Lemma Application

| Language | Pumped String | Result |
|----------|---------------|--------|
| **aⁿbⁿ** | a³b³ = aaabbb | x=aa, y=abb, z=b
  xy²z = a⁴b⁵ ∉ L | Not regular |

### Regular Language Properties

| Property | Description |
|----------|-------------|
| **Closed under** | Union, concatenation, Kleene star |
| **Accepted by** | DFA, NFA |
| **Described by** | Regular expression |
| **Pumping lemma** | Used to prove non-regular |

### Key Terms

| Term | Definition |
|------|------------|
| **Regular Expression** | Pattern description |
| **Kleene Star** | Zero or more repetitions |
| **Kleene Plus** | One or more repetitions |
| **Pumping Lemma** | Test for regularity |
| **Regular Language** | Accepted by DFA/NFA |

---

## Lecture 5: Applications of FA

### Applications of Finite Automata

| Application | Description |
|-------------|-------------|
| **String Matching** | Pattern matching algorithms |
| **Lexical Analysis** | Compiler tokenization |
| **Network Protocols** | Communication protocols |
| **Text Processing** | Search and replace |

### Pattern Matching

| Algorithm | Complexity | Description |
|-----------|------------|-------------|
| **Brute Force** | O(mn) | Shift pattern by 1 on mismatch |
| **KMP** | O(n) | Avoid backtracking on string |

### Knuth-Morris-Pratt (KMP) Algorithm

| Step | Description |
|------|-------------|
| 1 | Compare pattern with text |
| 2 | On mismatch, shift pattern optimally |
| 3 | Avoid previously compared positions |
| 4 | Achieve O(n) matching time |

### Lexical Analyzer

| Component | Description |
|-----------|-------------|
| **Input** | Source code |
| **Output** | Sequence of tokens |
| **Method** | DFA simulation |
| **Process** | RE → DFA → Program |

### Lexical Analysis Example

```
Input:  for i=1 to max do X[i]=0;
Tokens: for, i, =, 1, to, max, do, X, [, i, ], =, 0, ;
```

### Communication Protocol

| State | Description |
|-------|-------------|
| **Wait for RFNM** | Initial state |
| **Receiving RFNM** | Receiving request |
| **Sending ACK** | Sending acknowledgment |
| **Sending Message** | Transmitting data |
| **Waiting for ACK** | Awaiting confirmation |

### Key Terms

| Term | Definition |
|------|------------|
| **Pattern Matching** | Finding pattern in text |
| **KMP Algorithm** | Efficient string matching |
| **Lexical Analyzer** | Tokenizer for compilers |
| **Communication Protocol** | Network communication states |

---

## Lecture 6: CFG

### Context-Free Grammar (CFG)

| Component | Description |
|-----------|-------------|
| **V** | Set of variables (non-terminals) |
| **T** | Set of terminals (alphabet) |
| **P** | Set of production rules |
| **S** | Start symbol (S ∈ V) |

### CFG Production Rule Format

A → α

| Symbol | Meaning |
|--------|---------|
| **A** | Non-terminal (variable) |
| **α** | String of terminals and/or non-terminals |

### CFG Example

```
S → aSb | ab
```

| Derivation | Steps |
|------------|-------|
| **S ⇒ aSb** | Apply rule S → aSb |
| **⇒ aaSbb** | Apply rule S → aSb |
| **⇒ aabbb** | Apply rule S → ab |

### Language Generated by CFG

| Grammar | Language |
|---------|----------|
| **S → aSb | ab** | {aⁿbⁿ | n ≥ 1} |
| **S → aSb | λ** | {aⁿbⁿ | n ≥ 0} |

### Derivation Trees

| Component | Description |
|-----------|-------------|
| **Root** | Start symbol S |
| **Internal Nodes** | Non-terminals |
| **Leaves** | Terminals |
| **Children** | RHS of production rule |

### Leftmost Derivation

| Definition | Example |
|------------|---------|
| Always replace leftmost non-terminal | S ⇒ aSb ⇒ aaSbb ⇒ aabbb |

### Rightmost Derivation

| Definition | Example |
|------------|---------|
| Always replace rightmost non-terminal | S ⇒ aSb ⇒ aSabb ⇒ aababb |

### Ambiguity

| Grammar | Language | Property |
|---------|----------|----------|
| **S → aS | a | Sa** | Strings of a's | Unambiguous |
| **S → S + S | S * S | a** | Arithmetic expressions | Ambiguous |

### Key Terms

| Term | Definition |
|------|------------|
| **CFG** | Context-Free Grammar |
| **Non-terminal** | Variable in grammar |
| **Terminal** | Symbol in final string |
| **Production Rule** | A → α |
| **Start Symbol** | Initial non-terminal S |
| **Derivation** | Sequence of rule applications |
| **Ambiguous Grammar** | Multiple parse trees for string |

---

## Lecture 7: CNF

### Chomsky Normal Form (CNF)

| Rule Type | Format | Example |
|-----------|--------|---------|
| **Binary** | A → BC | A → BC |
| **Terminal** | A → a | A → a |

### CNF Properties

| Property | Requirement |
|----------|------------|
| **RHS** | Either one terminal or two non-terminals |
| **ε-productions** | Not allowed (except S → ε) |
| **Unit productions** | Not allowed (A → B) |
| **Long rules** | Not allowed (A → BCD) |

### CNF Conversion Algorithm

| Step | Operation | Purpose |
|------|-----------|---------|
| 1 | Add new start symbol S' → S | S in RHS |
| 2 | Remove null productions | Eliminate ε |
| 3 | Remove unit productions | Eliminate A → B |
| 4 | Break long rules | A → BCD → A → BC, C → CD |
| 5 | Separate terminals | A → aB → A → XB, X → a |

### CNF Conversion Example

**Original:**
```
S → ASA | aB
A → B | S
B → b | ε
```

**Step 1 (New start):**
```
S' → S
S → ASA | aB
A → B | S
B → b | ε
```

**Step 2 (Remove ε):**
```
S' → S
S → ASA | aB | a | AS | SA
A → B | S | ε
B → b
```

**Step 3 (Remove unit):**
```
S' → ASA | aB | a | AS | SA
S → ASA | aB | a | AS | SA
A → B | S | b
B → b
```

**Step 4 (Break long rules):**
```
S' → AX | aB | a | AS | SA
S → AX | aB | a | AS | SA
A → B | AX | aB | a | AS | SA
B → b
X → SA
```

**Step 5 (Separate terminals):**
```
S' → AX | YB | a | AS | SA
S → AX | YB | a | AS | SA
A → B | AX | YB | a | AS | SA
B → b
X → SA
Y → a
```

### Key Terms

| Term | Definition |
|------|------------|
| **CNF** | Chomsky Normal Form |
| **Binary Rule** | A → BC |
| **Terminal Rule** | A → a |
| **Null Production** | A → ε |
| **Unit Production** | A → B |
| **Long Rule** | A → BCD |

---

## Lecture 8: PDA

### Pushdown Automaton (PDA)

| Component | Description |
|-----------|-------------|
| **Q** | Finite set of states |
| **Σ** | Input alphabet |
| **Γ** | Stack alphabet |
| **δ** | Transition relation |
| **q₀** | Initial state |
| **F** | Final states |

### PDA Components

| Component | Description |
|-----------|-------------|
| **Input Tape** | Read input string |
| **Control Unit** | Finite state machine |
| **Stack** | Infinite LIFO storage |

### Stack Operations

| Operation | Description |
|-----------|-------------|
| **Push** | Add symbol to top |
| **Pop** | Remove top symbol |
| **Replace** | Replace top with symbols |

### PDA Transition

δ(q, a, X) = (p, γ)

| Symbol | Meaning |
|--------|---------|
| **q** | Current state |
| **a** | Input symbol (or ε) |
| **X** | Stack symbol to pop |
| **p** | Next state |
| **γ** | String to push |

### PDA Acceptance

| Type | Condition |
|------|-----------|
| **Final State** | End in final state |
| **Empty Stack** | Stack empty after reading all input |

### PDA Example: aⁿbⁿ

| Step | Input | Stack | Action |
|------|-------|-------|--------|
| 1 | a | Z₀ | Push a |
| 2 | a | aZ₀ | Push a |
| 3 | a | aaZ₀ | Push a |
| 4 | b | aaZ₀ | Pop a |
| 5 | b | aZ₀ | Pop a |
| 6 | b | Z₀ | Pop a (stack empty) |

### PDA vs DFA

| Feature | DFA | PDA |
|---------|-----|-----|
| **Memory** | Finite | Infinite (stack) |
| **Language** | Regular | Context-free |
| **Power** | Limited | More powerful |

### Key Terms

| Term | Definition |
|------|------------|
| **PDA** | Pushdown Automaton |
| **Stack** | LIFO storage |
| **Push** | Add to stack |
| **Pop** | Remove from stack |
| **Acceptance** | Final state or empty stack |

---

## Lecture 9: CYK Algorithm

### CYK Algorithm

| Aspect | Details |
|--------|--------|
| **Inventors** | Cocke, Younger, Kasami (1965-67) |
| **Purpose** | String membership for CFG |
| **Requirement** | Grammar must be in CNF |
| **Output** | Triangular table of possible non-terminals |

### CYK Algorithm Steps

| Step | Description |
|------|-------------|
| 1 | Consider substrings of length 1 |
| 2 | Consider substrings of length 2 |
| 3 | Continue to length n |
| 4 | Check if S is in X₁ₙ |

### Triangular Table Construction

```
      baaba       (Row 5: length 5)
     b a a b a      (Row 4: length 4)
    b a a b a       (Row 3: length 3)
   b a a b a        (Row 2: length 2)
  b a a b a         (Row 1: length 1)
```

### CYK Algorithm Example

**Grammar:**
```
S → AB | BC
A → BA | a
B → CC | b
C → AB | a
```

**String:** baaba

| Length | Substrings | Non-terminals |
|--------|-----------|---------------|
| 1 | b | {B} |
| 1 | a | {A, C} |
| 1 | a | {A, C} |
| 1 | b | {B} |
| 1 | a | {A, C} |
| 2 | ba | {A, S} |
| 2 | aa | {B} |
| 2 | ab | {S, C} |
| 2 | ba | {A, S} |
| 3 | baa | ∅ |
| 3 | aab | {A, S} |
| 3 | aba | ∅ |
| 4 | baab | ∅ |
| 5 | baaba | {S, A, C} |

### Result

Since S ∈ {S, A, C}, string "baaba" is in L(G).

### Key Terms

| Term | Definition |
|------|------------|
| **CYK Algorithm** | String membership testing |
| **CNF** | Chomsky Normal Form |
| **Triangular Table** | CYK computation structure |
| **String Membership** | Whether string is in language |

---

## Lecture 10: Turing Machines

### Turing Machine (TM)

| Component | Description |
|-----------|-------------|
| **Q** | Finite set of states |
| **Σ** | Input alphabet |
| **Γ** | Tape alphabet (includes blank symbol ⊔) |
| **δ** | Transition function |
| **q₀** | Initial state |
| **F** | Accepting states |

### TM Definition

M = (Q, Σ, Γ, δ, q₀, F)

| Symbol | Meaning |
|--------|---------|
| **δ(q, x) = (p, y, d)** | In state q, read x, write y, move d |
| **d ∈ {L, R, S}** | Move Left, Right, or Stay |

### TM Components

| Component | Description |
|-----------|-------------|
| **Tape** | Infinite tape with symbols |
| **Head** | Read/write head |
| **Control Unit** | Finite state machine |

### TM Operations

| Operation | Description |
|-----------|-------------|
| **Read** | Read symbol at head position |
| **Write** | Write symbol at head position |
| **Move** | Move head left or right |
| **Halt** | Stop computation |

### TM Acceptance

| Condition | Result |
|-----------|--------|
| **Halt in accept state** | Accept |
| **Halt in non-accept state** | Reject |
| **Infinite loop** | Reject |

### TM Example: aba*

| State | a | b | ⊔ | Action |
|-------|---|---|---|--------|
| q₀ | (q₁, a, R) | - | - | Read a, move right |
| q₁ | - | (q₂, b, R) | - | Read b, move right |
| q₂ | (q₂, a, R) | - | - | Read a, move right |
| q₂ | - | - | (qf, ⊔, S) | Halt and accept |

### TM vs Other Automata

| Automaton | Memory | Language Class |
|-----------|--------|----------------|
| **DFA/NFA** | None | Regular |
| **PDA** | Stack | Context-free |
| **TM** | Infinite tape | Recursively enumerable |

### Key Terms

| Term | Definition |
|------|------------|
| **TM** | Turing Machine |
| **Tape** | Infinite storage |
| **Head** | Read/write mechanism |
| **Transition Function** | δ(q, x) = (p, y, d) |
| **Halting** | Stop computation |
| **Acceptance** | Halt in accept state |

---

## Lecture 11: Hierarchy

### Chomsky Hierarchy

| Type | Grammar | Language | Machine | Production Form |
|------|---------|----------|---------|----------------|
| **3** | Regular | Regular | DFA/NFA | A → aB | A → a | A → λ |
| **2** | Context-free | Context-free | PDA | A → BC | A → a |
| **1** | Context-sensitive | Context-sensitive | LBA | αAβ → αγβ |
| **0** | Unrestricted | Recursively enumerable | TM | Any with non-terminal on LHS |

### Language Hierarchy

```
Unrestricted (Type 0)
        ↑
Context-sensitive (Type 1)
        ↑
Context-free (Type 2)
        ↑
Regular (Type 3)
```

### Type 3: Regular Grammars

| Property | Description |
|----------|-------------|
| **Production rules** | A → aB | A → a | A → λ |
| **Machine** | DFA/NFA |
| **Example** | L = {aⁿbⁿ | n ≥ 0} (not regular!) |

### Type 2: Context-Free Grammars

| Property | Description |
|----------|-------------|
| **Production rules** | A → α (single non-terminal on LHS) |
| **Machine** | PDA |
| **Example** | L = {aⁿbⁿ | n ≥ 0} |

### Type 1: Context-Sensitive Grammars

| Property | Description |
|----------|-------------|
| **Production rules** | αAβ → αγβ (|α| ≤ |αAβ| ≤ |αAβ|) |
| **Machine** | Linear-bounded automaton |
| **Example** | L = {aⁿbⁿcⁿ | n ≥ 0} |

### Type 0: Unrestricted Grammars

| Property | Description |
|----------|-------------|
| **Production rules** | Any with non-terminal on LHS |
| **Machine** | Turing machine |
| **Example** | Any computable language |

### Recursive vs Recursively Enumerable

| Type | Description |
|------|-------------|
| **Recursive** | TM always halts (accepts or rejects) |
| **Recursively Enumerable** | TM halts on accept, may loop on reject |

### Key Terms

| Term | Definition |
|------|------------|
| **Chomsky Hierarchy** | Grammar classification |
| **Regular Language** | Type 3 |
| **Context-Free Language** | Type 2 |
| **Context-Sensitive Language** | Type 1 |
| **Unrestricted Language** | Type 0 |
| **LBA** | Linear-bounded automaton |

---

## Lecture 12: TM Variations

### TM Variations

| Variation | Description | Power |
|-----------|-------------|-------|
| **Multi-Track TM** | Multiple tracks on tape | Same as TM |
| **Multi-Tape TM** | Multiple tapes and heads | Same as TM |
| **2-Stack TM** | Two stacks instead of tape | Same as TM |
| **Non-deterministic TM** | Multiple possible transitions | Same as TM |

### Multi-Track TM

| Feature | Description |
|---------|-------------|
| **Tape** | Single tape with multiple tracks |
| **Head** | Reads/writes all tracks simultaneously |
| **Transition** | δ(q, [a₁, a₂, ...]) = (p, [b₁, b₂, ...], d) |

### Multi-Tape TM

| Feature | Description |
|---------|-------------|
| **Tapes** | k tapes |
| **Heads** | k independent heads |
| **Transition** | δ(q, [a₁, a₂, ...]) = (p, [b₁, b₂, ...], d₁, d₂, ...) |
| **Advantage** | Can copy data, compare strings |

### 2-Stack TM

| Feature | Description |
|---------|-------------|
| **Stack 1** | Holds left side of head |
| **Stack 2** | Holds right side of head |
| **Equivalence** | TM with 2 stacks = TM with tape |

### Non-deterministic TM (NTM)

| Feature | Description |
|---------|-------------|
| **Transitions** | Multiple possible for one configuration |
| **Acceptance** | If any path accepts, string accepted |
| **Power** | Same as deterministic TM |

### NTM Transition

δ(q, x) = {(p₁, y₁, d₁), (p₂, y₂, d₂), ...}

### TM Equivalence

| Variation | Equivalent to | Reason |
|-----------|---------------|--------|
| **Multi-Track** | Standard TM | Can simulate with one track |
| **Multi-Tape** | Standard TM | Can interleave tracks |
| **2-Stack** | Standard TM | Stacks can simulate tape |
| **NTM** | DTM | Can simulate with breadth-first search |

### Key Terms

| Term | Definition |
|------|------------|
| **Multi-Track TM** | TM with multiple tracks |
| **Multi-Tape TM** | TM with multiple tapes |
| **2-Stack TM** | TM with two stacks |
| **NTM** | Non-deterministic Turing Machine |
| **Equivalence** | Same computational power |

---

## Lecture 13: Complexity

### Time Complexity Classes

| Class | Definition | Example Problems |
|-------|------------|------------------|
| **O(1)** | Constant | Array access |
| **O(log n)** | Logarithmic | Binary search |
| **O(n)** | Linear | Linear search |
| **O(n log n)** | Linearithmic | Merge sort |
| **O(n²)** | Quadratic | Bubble sort |
| **O(nᵣ)** | Polynomial | Some algorithms |
| **O(aⁿ)** | Exponential | Some algorithms |
| **O(n!)** | Factorial | Permutations |

### P Class

| Property | Description |
|----------|-------------|
| **Definition** | Problems solvable in polynomial time |
| **Notation** | P = ⋃ᵣ O(nᵣ) |
| **Examples** | Sorting, primality testing, GCD |
| **Characteristic** | Tractable |

### NP Class

| Property | Description |
|----------|-------------|
| **Definition** | Solutions checkable in polynomial time |
| **Notation** | Nondeterministic Polynomial |
| **Examples** | TSP, Hamiltonian circuit, satisfiability |
| **Characteristic** | Intractable (suspected) |

### NP-Complete

| Property | Description |
|----------|-------------|
| **Definition** | Can be reduced to any NP problem |
| **Characteristics** | - Solutions checkable in polynomial time
  - Cannot necessarily be found in polynomial time
  - Stand or fall together |
| **Examples** | Satisfiability, TSP, graph coloring |
| **Count** | > 1000 known problems |

### P vs NP

| Question | Answer |
|----------|--------|
| **P ⊆ NP?** | Yes (all P problems are NP) |
| **NP ⊆ P?** | Unknown (major open problem) |
| **P = NP?** | Unknown, most suspect not |

### NP Problems Solutions

| Method | Description | Trade-off |
|--------|-------------|----------|
| **Approximation** | Sub-optimal solution | Speed vs accuracy |
| **Heuristic** | Probabilistic solution | Not guaranteed optimal |
| **Randomized** | Random choices | Probably correct |
| **Genetic** | Modeled on genetics | Applied to hard problems |

### Complexity Hierarchy

```
P (Tractable)
    ↓
NP (Probably Intractable)
    ↓
NP-Complete (Hardest in NP)
```

### Key Terms

| Term | Definition |
|------|------------|
| **P** | Polynomial time solvable |
| **NP** | Nondeterministic polynomial time |
| **NP-Complete** | Hardest problems in NP |
| **Intractable** | Not solvable in polynomial time |
| **Approximation** | Sub-optimal but fast solution |

---
