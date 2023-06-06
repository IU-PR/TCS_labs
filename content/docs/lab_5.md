---
title: Lab 5 - DPDA
type: docs
weight: 5
BookToC: true
---
# **Lab Session #4**

# **Agenda**

- Deterministic Pushdown Automaton (DPDA): Notion, formal definition, configuration, transition, and acceptance.
- Exercises on DPDAs

---

## **Pushdown Automata**

A Pushdown Automaton (PDA) is a way to implement a Context Free Grammar in a similar way we design Finite Automaton for Regular Grammar.

- It is more powerful than FSA
- FSA has a very limited memory but PDA has more memory
- PDA = FSA + a Stack

A stack is a way we arrange elements one on top of another; it does two basic operations:

- **PUSH:** A new element is added at the Top of the stack
- **POP:** The Top element of the stack is read and removed

## **PDA-components**
A Pushdown Automaton has 3 components:
- An input tape
- A Finite Control Unit
- A Stack of infinite size

**Acceptance criteria:** A string {{<katex >}}x{{< /katex >}} is accepted by a PDA if there is a path coherent with {{<katex >}}x{{< /katex >}} on the PDA that goes from the initial state to the final state.
The input string has to be read completely.


When a PDA reads an input symbol, it will be able to save it
(or save other symbols) in its memory.

- For deciding if an input string is in the language  {{< katex >}} A_nB_n {{< /katex >}}, the
PDA needs to remember the numbers of {{< katex >}}a{{< /katex >}}’s.
- Whenever the PDA reads the input symbol {{< katex >}}b{{< /katex >}}, two things
should happen:
1. it should change states: from now on the only legal input
symbols are {{< katex >}}b{{< /katex >}}’s.
2. it should delete one *a* from its memory for every {{< katex >}}b{{< /katex >}} it reads.

A single move of a PDA will depend on:
- the current state
- the next input (it could be no symbol: ε symbol), and
- the symbol currently on top of the stack.
PDA will be assumed to begin operation with an initial start
symbol {{< katex >}} Z_0 {{< /katex >}} on its stack
- {{< katex >}} Z_0 {{< /katex >}} is not essential, but useful to simplify definitions
- {{< katex >}} Z_0 {{< /katex >}} is on top means that the stack is effectively empty.

---

## **Formal Definition**

A Pushdown Automaton is a tuple {{< katex >}} \langle {{< /katex >}} {{< katex >}}Q{{< /katex >}}, {{<katex >}}I{{< /katex >}}, {{< katex >}}\Gamma{{< /katex >}}, {{< katex >}}\delta{{< /katex >}}, {{< katex >}}q_0{{< /katex >}}, {{< katex >}}Z_0{{</katex>}}, {{< katex >}}F{{< /katex >}} {{< katex >}}\rangle{{< /katex >}}, where:

- {{< katex >}}Q{{< /katex >}} is a finite set of states. 
- {{< katex >}}I{{< /katex >}} and {{< katex >}}\Gamma{{< /katex >}} are finite sets, the input and stack alphabets.
- {{< katex >}}\delta{{< /katex >}} is the transition function.
- {{< katex >}}q_0 \in Q{{< /katex >}}, the initial state.
- {{< katex >}}Z_0 \in \Gamma{{< /katex >}}, the initial stack symbol.
- {{< katex >}}F \subseteq Q{{< /katex >}}, the set of accepting states.

**Configuration** 
A configuration is a generalization of the notion of state. It shows:
- the current state,
- the portion of the input string that has not yet been read, and
- the stack.
It is a snapshot of the PDA.

---

## **Example** 

Construct a PDA that accepts {{< katex >}} L = \{0^n1^n | n \geq 0\} {{< /katex >}}

{{< expand Solution >}}

![placeholdertext](/images/lab5/1.svg)

{{< /expand >}}

---

## **Exercises**

### **Part I**

Build DPDAs that recognise the following languages:
1. {{<katex>}} \{a^nb^{2n} \mid n \ge 1 \} {{</katex>}}
{{< expand Solution >}}
![Solution 1](/images/lab5/2.svg)
{{< /expand >}}
2. {{<katex>}} P = \{xycy^Rx^R \mid x \in \{a, b\}^* \wedge y \in \{d, e\}^* \wedge \left\vert{x}\right\vert > 0 \}{{</katex>}} (where {{<katex>}}x^R {{</katex>}}, {{<katex>}}y^R {{</katex>}}are the reversed strings {{<katex>}}x{{</katex>}}, {{<katex>}}y{{</katex>}}), the alphabet is {{<katex>}}I=\{a, b, c, d, e\}{{</katex>}}
{{< expand Solution >}}
![Solution 2](/images/lab5/3.svg)
{{< /expand >}}
3. {{<katex>}}  {{</katex>}} The language of nested and balanced brackets and parentheses. E.g. a string in the language: {{<katex>}}(([])())(){{</katex>}}, a string that does not belong to the language: {{<katex>}}([(]))()(){{</katex>}} -- the alphabet is {{<katex>}}I = \{(, ), [, ]\}{{</katex>}}
{{< expand Solution >}}
![Solution 3](/images/lab5/4.svg)
{{< /expand >}}

### **Part II**

Build DPDAs that recognise the following languages:

1. {{<katex>}}L_1 = \{w \in \{a, b\}^* \mid \phi(w, a) = \phi(w, b)\}{{</katex>}} where {{<katex>}}\phi(s, c){{</katex>}} is the number of occurrences of the character {{<katex>}}c{{</katex>}} in the string {{<katex>}}s{{</katex>}}
{{< expand Solution >}}
![Solution 1](/images/lab5/5.svg)
{{< /expand >}}
2. {{<katex>}}L_2 = \{a^nb^ma^mb^n \mid n > 0 \wedge m > 0\}{{</katex>}}
{{< expand Solution >}}
![Solution 1](/images/lab5/6.svg)
{{< /expand >}}
3. {{<katex>}}L_3 = L^*_2{{</katex>}}
{{< expand Solution >}}
![Solution 1](/images/lab5/7.svg)
{{< /expand >}}
4. {{<katex>}}L_4 = \{a^{n_1}b^{n_1}a^{n_2}b^{n_2}a^{n_3}b^{n_3} \ldots a^{n_k}b^{n_k} \mid k \ge 1 \wedge n_i \ge 1 \wedge 1 \le i \le k \}{{</katex>}}
{{< expand Solution >}}
![Solution 1](/images/lab5/8.svg)
{{< /expand >}}

---

## **Homework**

1. Define a DPDA that recognises this language:
    {{<katex>}}L = \{a^nb^n \cup a^nb^{2n} \mid n \ge 0\}{{</katex>}}
2. Construct a DPDA that recognises the language of well-formed parentheses of the arithmetic expressions (binary operations). 
      
For simplicity, consider the alphabet  {{<katex>}}I = \{a, (, ), +\} {{</katex>}} - a single symbol  {{<katex>}}a {{</katex>}} that represents terms  {{<katex>}}a, b, c, \ldots {{</katex>}} and a single operator {{<katex>}}+{{</katex>}}.

Examples of strings belonging to the language are:

- {{<katex>}}(a + a){{</katex>}}
- {{<katex>}}((a) + (a + a)){{</katex>}}
- {{<katex>}}((a + a)){{</katex>}}

