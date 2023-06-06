---
title: Lab 12 - Grammars
type: docs
weight: 12
BookToC: true
---

# **Lab Session #12**

# **Agenda**

{{<button relref="#grammars">}} Generative Grammars {{</button>}} 
{{<button relref="#chomsky-hierarchy">}} Chomsky Hierarchy {{</button>}} 
{{<button relref="#context-free-grammars-type-2">}} Context-Free Grammars: Backus-Naur Form {{</button>}}



# **Models**
{{<columns>}}
### **Automata (operational models):**
- Models suitable to recognize/accept, translate, compute language: receive an input string and process it.
<--->
### **Grammar (generative models):**
- Models suitable to describe how to generate a language: set of rules to build phrases of a language. 
{{</columns>}}

---

# **Grammars**


### **A grammar is a set of rules to produce strings.**

*A grammar is a tuple*: {{<katex>}} \langle V_N, V_T, P, S \rangle {{</katex>}}, where: 
- {{<katex>}} V_N {{</katex>}} is  the  non-terminal  alphabet 

- {{<katex>}} V_T {{</katex>}} is  the  terminal  alphabet; 

- {{<katex>}} P {{</katex>}} is  the  terminal  alphabet; 

- {{<katex>}} S {{</katex>}} is  the  terminal  alphabet; 

- {{<katex>}} V = V_N \cup V_T  {{</katex>}}the  alphabet;

- {{<katex>}} P \subseteq \left(V^* \cdot V_N \cdot V^*\right) \times V^* {{</katex>}} is the (finite) set of rewriting rules of production;

- {{<katex>}} S \in V_N {{</katex>}} is  a particular element called axiom or initial symbol. 

-  A grammar {{<katex>}} \langle V_N, V_T, P, S\rangle{{</katex>}} generates a language on  V_T. 

<br>

**Terminal symbols are elementary symbols** - cannot be broken down into smaller units i.e. cannot be changed using the production rules of the grammar.

**Non-terminal symbols** -  can be replaced by groups of terminal and  non-terminal symbols according to the production rules.


## **Production Rule**

Let {{<katex>}} G = \langle V_N, V_T, P, S\rangle {{</katex>}} be  a grammar.  <br>

A production rule {{<katex>}} \alpha \rightarrow \beta{{</katex>}}  is an element of {{<katex>}}P{{</katex>}}, where: 

- {{<katex>}}\alpha \in V^* \cdot V_N \cdot V^*{{</katex>}}  is a sequence of symbols including at least one non-terminal   symbol.

- {{<katex>}}\beta \in V^*{{</katex>}}  is a (potentially empty) sequence of (terminal or non-terminal) symbols. 

---

#  **Chomsky Hierarchy**

|Chomsky hierarchy | Grammars| Languages| Miniamal automaton|
| :---: | :---: | :---: | :---: |
|type 0 | Unrestricted | Recursively enumerable | Turing machine|
|type 1 | Context-sensitive | Context-sensitive | LBA|
|type 2 | Context-free | Context-free | NDPDA|
|type 3 | Regular | Regular | FSA|


---


# **Strictly Regular grammars** *(type 3)*
Production rules are restricted to a single non-terminal on the left-hand side and a right-hand side consisting of a single terminal, possibly
- **followed by a single non-terminal - right grammar**
- **preceded by a single non-terminal - left grammar**

{{<hint info>}}
{{<columns display>}}
## Example:
**Generate language with the strings of alternating a's and b's:**
- {{<katex>}} V_N = \{S, A, B\}; \hspace{0.2cm} {{</katex>}}
- {{<katex>}} V_T = \Sigma_1 = \{a, b\} {{</katex>}}

<--->
## Set of  Production rules P:
- {{<katex>}} S \rightarrow A {{</katex>}}
- {{<katex>}} S \rightarrow B {{</katex>}}
- {{<katex>}} A \rightarrow  aB {{</katex>}}
- {{<katex>}} A \rightarrow \epsilon {{</katex>}}
- {{<katex>}} B \rightarrow  bA {{</katex>}}
- {{<katex>}} B \rightarrow \epsilon {{</katex>}}
{{</columns>}}
{{</hint>}}

---

# **Strictly Regular grammars**

{{<tabs "strictly">}}
{{<tab "Strictly Right regular grammar">}}
## **Strictly Right regular grammar**
A right regular grammar is a formal grammar, such that all the production rules in P are of one of the following forms:
- {{<katex>}} A \rightarrow b {{</katex>}}  where {{<katex>}} A \in V_N {{</katex>}}  and {{<katex>}} b \in V_T{{</katex>}}
- {{<katex>}} A \rightarrow bB {{</katex>}}  where {{<katex>}} A, B \in V_N {{</katex>}} and {{<katex>}} b \in V_T{{</katex>}}
- {{<katex>}} A \rightarrow \epsilon {{</katex>}} where A {{<katex>}} \in V_N {{</katex>}} and {{<katex>}}  \epsilon {{</katex>}}  denotes  the  empty string. 
{{</tab>}}

{{<tab "Strictly Left regular grammar">}}
## **Strictly Left regular grammar**
A left regular grammar is a formal grammar, such that all the production rules in P are of one of the following forms:
- {{<katex>}} A \rightarrow b{{</katex>}}  where {{<katex>}} A \in V_N {{</katex>}} and {{<katex>}} b \in V_T {{</katex>}}
- {{<katex>}}A \rightarrow Bb{{</katex>}} where {{<katex>}}A, B \in V_N{{</katex>}} and {{<katex>}}b \in V_T{{</katex>}}
- {{<katex>}}A \rightarrow \epsilon{{</katex>}} where {{<katex>}}A \in V_N{{</katex>}} and {{<katex>}}\epsilon{{</katex>}} denotes the empty string.
{{</tab>}}
{{</tabs>}}



# **Extended regular grammars**


{{<tabs "extended">}}
{{<tab "Extended Right regular grammar">}}

## **Extended Right regular grammar**
A right regular grammar is a formal grammar, such that all the production rules in P are of one of the following forms:
- {{<katex>}}A \rightarrow b{{</katex>}} where {{<katex>}}A \in V_N{{</katex>}} and {{<katex>}}b \in V_T{{</katex>}}
- {{<katex>}}A \rightarrow wB{{</katex>}} where {{<katex>}}A, B \in V_N{{</katex>}} and {{<katex>}}w \in V_T^*{{</katex>}}
- {{<katex>}}A \rightarrow \epsilon{{</katex>}} where {{<katex>}}A \in V_N{{</katex>}} and {{<katex>}}\epsilon{{</katex>}} denotes the empty string.
{{</tab>}}

{{<tab "Extended Left regular grammar">}}
## **Extended Left regular grammar**
A left regular grammar is a formal grammar, such that all the production rules in P are of one of the following forms:
- {{<katex>}}A \rightarrow b{{</katex>}} where {{<katex>}}A \in V_N{{</katex>}} and {{<katex>}}b \in V_T{{</katex>}}
- {{<katex>}}A \rightarrow Bw{{</katex>}} where {{<katex>}}A, B \in V_N{{</katex>}} and {{<katex>}}w \in V_T^*{{</katex>}}
- {{<katex>}}A \rightarrow \epsilon{{</katex>}} where {{<katex>}}A \in V_N{{</katex>}} and {{<katex>}}\epsilon{{</katex>}} denotes the empty string.
{{</tab>}}
{{</tabs>}}


---


## **Exercises**
**Define Strictly Regular grammars that produce the following languages over the alphabet:**
- {{<katex>}}\Sigma_1  =  \{a, b\} ,  \Sigma_2  = \{0, 1\}{{</katex>}} 
- {{<katex>}}L_1 = \{0,1\}^*{{</katex>}}
- {{<katex>}}L_2 = \{(aab \hspace{0.2cm} | \hspace{0.2cm} bba)^*\}{{</katex>}} 

## *Solutions*
{{<details "Solutions">}}
{{<tabs "1">}}

{{<tab "Solutions L1">}} 
{{<katex display>}} L_1 = \{0,1\}^* {{</katex>}}
{{<katex display>}}V_N = {S} \hspace{0.2cm} {{</katex>}}
{{<katex display>}} V_T = \Sigma_2 = \{0,1\}{{</katex>}} 
Set of  Production rules P: 
- {{<katex>}}S \rightarrow \epsilon{{</katex>}}
- {{<katex>}}S \rightarrow 0S{{</katex>}}
- {{<katex>}}S \rightarrow 1S{{</katex>}}
{{</tab>}}

{{<tab "Solutions L2">}} 
{{<katex display>}}L_2 = \{(aab \hspace{0.2cm} |\hspace{0.2cm} bba)^*\}{{</katex>}}
{{<katex display>}}V_N = \{S, A, B, F, E\} \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma_1 = \{a, b\} {{</katex>}}

Set of  Production rules P:
- {{<katex>}} S \rightarrow \epsilon{{</katex>}}
- {{<katex>}}S \rightarrow aA{{</katex>}}
- {{<katex>}}S \rightarrow bB{{</katex>}}
- {{<katex>}}A \rightarrow aF{{</katex>}}
- {{<katex>}}F \rightarrow bS{{</katex>}}
- {{<katex>}}B \rightarrow bE{{</katex>}}
- {{<katex>}}E \rightarrow aS{{</katex>}}
{{</tab>}}
{{</tabs>}}
{{</details>}}


---

## **Homework:**
- {{<katex>}}L_3 = \{(aa \hspace{0.2cm} | \hspace{0.2cm} bb)^*aa \}{{</katex>}}
- {{<katex>}}L_4 = \{(00^* 11^*)\}{{</katex>}}

---

# **Context-Free grammars** *(type 2)*
Defined by rules of the form {{<katex>}}A \rightarrow \gamma{{</katex>}} where {{<katex>}}A{{</katex>}} is a non-terminal and {{<katex>}}\gamma{{</katex>}} is a string of terminals and non-terminals. <br>

{{<hint info>}}
{{<columns>}}
## Example
**Generate language:**
- {{<katex>}}a^nb^n,  {{</katex>}}where{{<katex>}}  n>0{{</katex>}}
- {{<katex>}}V_N = \{S\}; \hspace{0.2cm} {{</katex>}}
- {{<katex>}} V_T = \Sigma_1 = \{a, b\}{{</katex>}} 
<--->
## Set of  Production rules P:
- {{<katex>}}\{ S \rightarrow  aSb  |  ab\}{{</katex>}}
{{</columns>}}
{{</hint>}}

{{<hint>}}
## **Exercises**
**Define context-free grammars that produce the following languages over the alphabet:**
- {{<katex>}}\Sigma = \{a, b\}{{</katex>}}
- {{<katex>}}L_1 = \{w ∈ \{a, b\}^∗| w = w^R\}{{</katex>}}
- {{<katex>}}L_2= \{a^ib^jc^k  |  i, j, k \geq 0  and  i=j or  i=k \} {{</katex>}}
**Homework:**
- {{<katex>}} L_3 = Generate  language  with  alternating  a's  and  b's {{</katex>}}
- {{<katex>}}L_4 = \{a^nb^nc^m \mid n,m>0\} \cup \{a^nb^mc^m \mid n,m>0\}{{</katex>}}
{{</hint>}}

## *Solutions*
{{<details "Solutions">}}
{{<tabs "2">}}

{{<tab "Solution L1">}}
{{<katex display>}}L_1 = \{w ∈ \{a, b\}^∗ | w = w^R\}{{</katex>}}
{{<katex display>}}V_N = \{S, O, E\} \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a, b\}{{</katex>}}
Set of  Production rules P: <br>
- {{<katex>}}S \rightarrow O \hspace{0.2cm} | \hspace{0.2cm} E{{</katex>}}
- {{<katex>}}E \rightarrow  \epsilon \hspace{0.2cm} |\hspace{0.2cm}  aEa \hspace{0.2cm} \hspace{0.2cm} | \hspace{0.2cm} bEb{{</katex>}}
- {{<katex>}}O \rightarrow a \hspace{0.2cm}|\hspace{0.2cm} b \hspace{0.2cm} | \hspace{0.2cm} aOa\hspace{0.2cm} |\hspace{0.2cm} bOb{{</katex>}}
or:
- {{<katex>}}S \rightarrow aSa \hspace{0.2cm} |\hspace{0.2cm} bSb \hspace{0.2cm}|\hspace{0.2cm} a \hspace{0.2cm}|\hspace{0.2cm} b\hspace{0.2cm} |\hspace{0.2cm} e {{</katex>}}
{{</tab>}}


{{<tab "Solution L2">}}
{{<katex display>}}L_2= \{a^ib^jc^k |  i, j, k \geq 0  and  i=j  or  i=k\}{{</katex>}}
{{<katex display>}}V_N = \{S, X, Y, W, Z \} \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a, b\} {{</katex>}}
Set of  Production rules P:<br>
- {{<katex>}}S \rightarrow XY \hspace{0.2cm} | \hspace{0.2cm} W{{</katex>}}
- {{<katex>}}X \rightarrow aXb \hspace{0.2cm} | \hspace{0.2cm} \epsilon{{</katex>}}
- {{<katex>}}Y \rightarrow cY \hspace{0.2cm} | \hspace{0.2cm} \epsilon{{</katex>}}
- {{<katex>}}W \rightarrow aWc \hspace{0.2cm} | \hspace{0.2cm} Z{{</katex>}}      
- {{<katex>}}Z \rightarrow bZ \hspace{0.2cm} | \hspace{0.2cm} \epsilon{{</katex>}}
{{</tab>}}

{{<tab "Solutions L3">}}
{{<katex display>}}L_3,  Generate  language  with  alternating  a's  and  b's {{</katex>}}
{{<katex display>}}V_N = \{ S,A,B\} \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma_1 = \{a, b\} {{</katex>}}
- {{<katex>}}S \rightarrow bB\hspace{0.2cm}|\hspace{0.2cm}aA\hspace{0.2cm}|\hspace{0.2cm}\epsilon{{</katex>}}
- {{<katex>}}A \rightarrow bB\hspace{0.2cm}|\hspace{0.2cm} \epsilon{{</katex>}}
- {{<katex>}}B \rightarrow aA\hspace{0.2cm}|\hspace{0.2cm} \epsilon{{</katex>}} 
{{</tab>}}


{{<tab "Solutions L4">}}
{{<katex display>}}
L_4 = \{a^nb^nc^m \mid n,m>0\} \cup \{a^nb^mc^m \mid n,m>0\}
{{</katex>}}
{{<katex display>}}V_N = \{S,M,N,A,C\} {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a,b,c\} {{</katex>}}
- {{<katex>}}S \rightarrow aNbC\hspace{0.2cm}|AbMc{{</katex>}}
- {{<katex>}}N \rightarrow aNb\hspace{0.2cm}| \hspace{0.2cm}\epsilon{{</katex>}}
- {{<katex>}}M \rightarrow bMc\hspace{0.2cm}| \hspace{0.2cm}\epsilon{{</katex>}}
- {{<katex>}}C \rightarrow cC\hspace{0.2cm}|\hspace{0.2cm}\epsilon{{</katex>}}
- {{<katex>}}A \rightarrow aA\hspace{0.2cm}|\hspace{0.2cm} \epsilon{{</katex>}}
{{</tab>}}
{{</tabs>}}
{{</details>}}



---

# **Context-Sensitive grammars** *(type 1)*
The rules of the form {{<katex>}}\alpha A \beta \rightarrow \alpha \gamma \beta{{</katex>}}, where {{<katex>}}A{{</katex>}} is a non-terminal and {{<katex>}}\alpha{{</katex>}}, {{<katex>}}\beta{{</katex>}} and {{<katex>}}\gamma{{</katex>}} are strings of terminals and non-terminals.
- {{<katex>}}\gamma{{</katex>}} must be non-empty
- The rule {{<katex>}} S\rightarrow\epsilon{{</katex>}} is allowed if S does not appear on the right side of any rule



{{<hint info>}}
{{<columns>}}
## Example
**Generate language:**
- {{<katex>}}\{A^nB^nC^n | n > 0\}{{</katex>}}  
<--->
## Set of production rules:        
- {{<katex>}}S \rightarrow aBC{{</katex>}}
- {{<katex>}}S \rightarrow  aSBC{{</katex>}}
- {{<katex>}}CB \rightarrow CZ{{</katex>}}
- {{<katex>}}CZ \rightarrow BZ{{</katex>}}
- {{<katex>}}BZ \rightarrow BC{{</katex>}}
- {{<katex>}}aB \rightarrow ab {{</katex>}}
- {{<katex>}}bB \rightarrow bb {{</katex>}}
- {{<katex>}}bC \rightarrow bc {{</katex>}}
- {{<katex>}}cC \rightarrow cc {{</katex>}}
{{</hint>}}
{{</columns>}}

{{<hint>}}
## **Exercises** 
**Define context-sensitive grammars that produce the following languages:** 
- {{<katex>}}L_1 = \{a^ib^jc^id^j \hspace{0.2cm}|\hspace{0.2cm} i,j \geq 1\} {{</katex>}}      
- {{<katex>}}L_2 = \{WW \hspace{0.2cm}|\hspace{0.2cm} W ∈ \{a, b\}^∗\}{{</katex>}} 
**Homework:**
- {{<katex>}}L_3 =  \{W ∈ \{a, b, c\}^∗| \#(a) = \#(b) = \#(c)   and  \#(a) ≥1  \} {{</katex>}}
{{</hint>}}
        
## *Solutions*
{{<details "Solutions">}}
{{<tabs "3">}}

{{<tab "Solutions L1">}}
{{<katex display>}}L_1 = \{a^ib^jc^id^j \hspace{0.2cm}|\hspace{0.2cm} i,j \geq 1\}{{</katex>}}

{{<katex display>}}V_N = \{S,X,B,C, Y,Z\}; \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a,b\} {{</katex>}}
Set of  Production rules P:
- {{<katex>}}S \rightarrow XY{{</katex>}}
- {{<katex>}}X \rightarrow aXC\hspace{0.2cm} |\hspace{0.2cm} aC{{</katex>}}
- {{<katex>}}Y \rightarrow BYd\hspace{0.2cm} | \hspace{0.2cm}Bd{{</katex>}}
- {{<katex>}}CB \rightarrow CZ{{</katex>}}
- {{<katex>}}CZ \rightarrow BZ{{</katex>}}
- {{<katex>}}BZ \rightarrow BC{{</katex>}}
- {{<katex>}}aB \rightarrow ab{{</katex>}}
- {{<katex>}}Cd\rightarrow cd{{</katex>}}
 {{</tab>}}



{{<tab "Solutions L2.1">}}

{{<katex display>}}L_2= \{WW \hspace{0.2cm}|\hspace{0.2cm} W ∈ \{a, b\}^∗\} {{</katex>}}
{{<katex display>}}V_N = \{S, A, B, C, D, E\} \hspace{0.2cm} {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a, b\}{{</katex>}}


Set of  Production rules P: 

- {{<katex>}}S    \rightarrow   \epsilon \hspace{0.2cm}| \hspace{0.2cm}CD\hspace{0.2cm}|\hspace{0.2cm} EF{{</katex>}}
- {{<katex>}}C    \rightarrow   aCA \hspace{0.2cm}|\hspace{0.2cm} bCB \hspace{0.2cm}|\hspace{0.2cm} a{{</katex>}}
- {{<katex>}}D    \rightarrow   aEA \hspace{0.2cm}|\hspace{0.2cm} bEB \hspace{0.2cm}| \hspace{0.2cm}b{{</katex>}}
- {{<katex>}}AD   \rightarrow   XD{{</katex>}}
- {{<katex>}}BD   \rightarrow   YD{{</katex>}}
- {{<katex>}}AF   \rightarrow   XF{{</katex>}}
- {{<katex>}}BF   \rightarrow   YF{{</katex>}}
- {{<katex>}}AX   \rightarrow   VX {{</katex>}}
- {{<katex>}}VX   \rightarrow   VW {{</katex>}}
- {{<katex>}}VW   \rightarrow   VA{{</katex>}}
- {{<katex>}}VA   \rightarrow   XA {{</katex>}}
- {{<katex>}}BX   \rightarrow   WX{{</katex>}}
- {{<katex>}}WX   \rightarrow   WV   {{</katex>}}

Continue..on next slide
{{</tab>}}



{{<tab "Solutions L2.2">}}
{{<katex display>}} L_1 = \{WW \hspace{0.2cm}|\hspace{0.2cm} W ∈ \{a, b\}^∗\} {{</katex>}} 

{{<katex display>}} V_N  =  \{S, A, B, C, D, E\} \hspace{0.2cm} {{</katex>}} 
{{<katex display>}} V_T = \Sigma = \{a, b\} {{</katex>}}

Set of  Production rules P: <br>

- {{<katex>}}WV   \rightarrow   WB  {{</katex>}}
- {{<katex>}}WB   \rightarrow   XB  {{</katex>}}
- {{<katex>}}AY   \rightarrow   UY   {{</katex>}}
- {{<katex>}}UY   \rightarrow   UZ  {{</katex>}}
- {{<katex>}}UZ   \rightarrow   UA  {{</katex>}}
- {{<katex>}}UA   \rightarrow   YA  {{</katex>}}
- {{<katex>}}BY   \rightarrow   ZY  {{</katex>}}
- {{<katex>}}ZY   \rightarrow   ZU  {{</katex>}}
- {{<katex>}}ZU   \rightarrow   ZB  {{</katex>}}
- {{<katex>}}ZB   \rightarrow   YB  {{</katex>}}
- {{<katex>}}aD   \rightarrow   aa   {{</katex>}}
- {{<katex>}}bD   \rightarrow   ba   {{</katex>}}
- {{<katex>}}aF   \rightarrow   ab   {{</katex>}}
- {{<katex>}}bF   \rightarrow   bb   {{</katex>}}
- {{<katex>}}aX   \rightarrow   aa   {{</katex>}}
- {{<katex>}}bX   \rightarrow   ba   {{</katex>}}
- {{<katex>}}aY   \rightarrow   ab   {{</katex>}}
- {{<katex>}}bY   \rightarrow   bb   {{</katex>}}
{{</tab>}}

{{<tab "Solution L3">}}


{{<katex display>}} L_{3}=\left\{w \mid w \in\{a, b, c\}^{*} \wedge \#(a)=\#(b)=\#(c) \geq 1\right\} {{</katex>}}

{{<katex display>}} V_N = \{S,A,B,C,P,Q,R,X,Y,Z\} {{</katex>}}
{{<katex display>}} V_T = \Sigma = \{a, b, c\} {{</katex>}}

Set of  Production rules P: <br>
- {{<katex>}}S \rightarrow SABC\hspace{0.2cm}|\hspace{0.2cm}ABC{{</katex>}}
- {{<katex>}}A\rightarrow a{{</katex>}}
- {{<katex>}}AB\rightarrow AQ {{</katex>}}
- {{<katex>}}AQ \rightarrow BQ{{</katex>}}
- {{<katex>}}BQ \rightarrow BA{{</katex>}}
- {{<katex>}}AC \rightarrow AR{{</katex>}}
- {{<katex>}}AR \rightarrow CR{{</katex>}}
- {{<katex>}}CR \rightarrow CA{{</katex>}}
- {{<katex>}}B \rightarrow b{{</katex>}}
- {{<katex>}}BA \rightarrow BP{{</katex>}}
- {{<katex>}}BP \rightarrow AP{{</katex>}}
- {{<katex>}}AP \rightarrow AB{{</katex>}}

- {{<katex>}}BC \rightarrow CZ{{</katex>}}
- {{<katex>}}BZ \rightarrow CZ{{</katex>}}
- {{<katex>}}CZ \rightarrow CB{{</katex>}}


- {{<katex>}}C \rightarrow c{{</katex>}}
- {{<katex>}}CA \rightarrow CX{{</katex>}}
- {{<katex>}}CX \rightarrow AX{{</katex>}}
- {{<katex>}}AX \rightarrow AC{{</katex>}}
- {{<katex>}}CB \rightarrow CY{{</katex>}}
- {{<katex>}}CY \rightarrow BY{{</katex>}}
- {{<katex>}}BY \rightarrow BC{{</katex>}}
{{</tab>}}

{{</tabs>}}
{{</details>}}


---

# **Unrestricted grammars** *(type 0)*

The rules of the form {{<katex>}}\alpha \rightarrow \beta{{</katex>}}, where {{<katex>}}\alpha{{</katex>}} and {{<katex>}}\beta{{</katex>}} are strings of non-terminals and terminals.<br>
 	  
The grammars without any limitation on production rules.<br>
{{<katex>}}\alpha{{</katex>}}  at least have one non-terminal <br>
{{<katex>}}\alpha{{</katex>}} cannot be an empty string <br>
 	


{{<hint info>}}
{{<columns>}}
## Example:
**Generate language:** 
- {{<katex>}}\{A^nB^nC^n | n > 0\}{{</katex>}}		        
<--->
## Set of productions rules:
- {{<katex>}}S \rightarrow  aBC{{</katex>}}
- {{<katex>}}S \rightarrow  aSBC{{</katex>}}
- {{<katex>}}CB \rightarrow BC{{</katex>}}
- {{<katex>}}aB \rightarrow ab{{</katex>}}
- {{<katex>}}bB \rightarrow bb{{</katex>}}
- {{<katex>}}bC \rightarrow bc{{</katex>}}
- {{<katex>}}cC \rightarrow cc{{</katex>}}

{{</columns>}}
{{</hint>}}


## **Exercises**
**Generate Unrestricted grammars for below languages:** <br>
- {{<katex>}}L_1 = \{W  |    W = a^i{{</katex>}}  and {{<katex>}} i = 2^ k {{</katex>}} and {{<katex>}}  k > 0\} {{</katex>}}
- {{<katex>}}L_2 = \{a^nb^mc^nd^m \hspace{0.2cm}|\hspace{0.2cm} n>0, m>0\}{{</katex>}}

## *Solutions*
{{<details "Solutions">}}
{{<tabs "4">}}
{{<tab "Solution L1">}}

{{<katex display>}} L_1 = \{W :   W = a^i  and  i = 2^ k  and  k > 0\} {{</katex>}}


{{<katex display>}}V_N = \{S, L, X, Y\}; {{</katex>}} 
{{<katex display>}}V_T = \Sigma = \{a, b, c\} {{</katex>}}

Set of  Production rules P: <br>

- {{<katex>}}S \rightarrow LaaYR{{</katex>}}
- {{<katex>}}aX \rightarrow Xaa{{</katex>}}
- {{<katex>}}LX \rightarrow LY \hspace{0.2cm}|\hspace{0.2cm} \epsilon{{</katex>}}
- {{<katex>}}L \rightarrow \epsilon{{</katex>}}
- {{<katex>}}Ya \rightarrow aaY{{</katex>}}
- {{<katex>}}YR \rightarrow XR \hspace{0.2cm}|\hspace{0.2cm} \epsilon{{</katex>}}
- {{<katex>}}R \rightarrow \epsilon{{</katex>}}
{{</tab>}}

{{<tab "Solution L2">}}

{{<katex display>}}L_2=\{a^nb^mc^nd^m \hspace{0.2cm}|\hspace{0.2cm} n>0, m>0\} {{</katex>}}


{{<katex display>}}V_N = \{S, A, B, C, X, Y\}; {{</katex>}}
{{<katex display>}}V_T = \Sigma = \{a, b, c\}{{</katex>}}
Set of  Production rules P: <br>

- {{<katex>}}S\rightarrow XY{{</katex>}}
- {{<katex>}}X\rightarrow aXC\hspace{0.2cm}|\hspace{0.2cm}aC{{</katex>}}
- {{<katex>}}Y\rightarrow BYd \hspace{0.2cm}| \hspace{0.2cm} Bd{{</katex>}}
- {{<katex>}}CB\rightarrow BC{{</katex>}}
- {{<katex>}}aB\rightarrow ab{{</katex>}}
- {{<katex>}}bB\rightarrow bb{{</katex>}}
- {{<katex>}}Cd\rightarrow cd{{</katex>}}
- {{<katex>}}Cc\rightarrow cc{{</katex>}}
{{</tab>}}

{{</tabs>}}
{{</details>}}

---

## **Homework:**
- {{<katex>}}L_3 = \{ a^n b^{2n}c^{3n} \hspace{0.2cm}| \hspace{0.2cm} n ≥ 1\} {{</katex>}}



