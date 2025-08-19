# Pharmacy Vending Machine 
<img width="494" height="373" alt="ven" src="https://github.com/user-attachments/assets/72ff39c1-e1d0-47fb-bd01-fbc3c82384b5" />


## Scope 
In this project, a vending machine was designed using Finite State Machines. It is intended to be placed in markets, restaurants,
universities, and other public areas. The vending machine will sell medical products such as wound plasters, cotton,headache pills, and other items 
for users who may be injured, unwell, or unable to access a pharmacy or hospital. It will also offer products related to skin care and oral care.
This project involves the construction of a finite automaton that includes three main categories: medicines, skin care, and oral care. The vending machine simulator processes product
sale transactions by taking the user's product selection as input and displaying the amount to be paid as output. The vending machine supports various payment methods to make the process convenient.
However, if the user chooses to pay with cash, only denominations of 5 SR, 10 SR, and 15 SR are accepted. Any other denominations will be rejected.



## Vending Machine States Table
![state table 1](https://github.com/user-attachments/assets/043235b1-5ce8-499a-be13-cbb5a05b763a)

![state table 2](https://github.com/user-attachments/assets/55065df5-3599-487f-8c16-c092710b6169)





## Vending Machine Strings Table

![string table](https://github.com/user-attachments/assets/3bf56341-c48a-43e0-85f5-4442ed0bf9de)





## Finite Automata

![fininte automanta](https://github.com/user-attachments/assets/ec2ff14a-9655-4e73-82a5-59c964a59420)


## Scenario
Starting from the initial state (Q0) The user has 3 sector options to choose from: 
1. (Q1) Makeup Section
2. (Q2) Pharmacy Section
3. (Q3) Oral care Section
Each section has exactly 3 products with different prices, if the user selects (Q1) it will take them to the makeup section (Q1) which 
has 3 products to choose from: 
(Q4) nail polish, (Q5) makeup remover, (Q6) SPF. So, when the user selects (Q6) for example, the machine will check first the 
availability of the product in state (Q15). The availability has two cases: 
• If the product is available, the user will move to state (Q25). Then the user will have two payment methods either by credit 
card (Q30) or cash (Q31). The process of the two methods is the same for the two states. So, if user selects pay by credit card 
(Q30) the process is either successful (Q39) which is the final state, or not successful which is state (Q40) that is also a final 
state. 
• If the product is not available, the state of the product will go back to the initial state and start the machine process.
The scenario applies the same for each product in the automata.




## NFA


![nfa](https://github.com/user-attachments/assets/5eee17f1-d0e7-4f32-9874-1bbbce3569a8)


## NFA State Transition Table
![nfa table](https://github.com/user-attachments/assets/7e4669fd-ec45-4bff-abd0-47d42950f5f5)





## DFA State Transition Table
![DFA table](https://github.com/user-attachments/assets/a066fc7d-aee9-4bbe-b951-af2b97935fe5)
![DFA table 2](https://github.com/user-attachments/assets/205be5f4-fc12-4d13-99f6-6a382e2b5397)





## Build DFA

![build dfa](https://github.com/user-attachments/assets/3c13f673-f190-4d84-9d50-b5482e4b7bcc)



## Production Rules for NFA
q0 → Op1 q1 | Op2 q2

q1 → SelNP q4 | SelMR q5 | SelSPF q6

q2 → SelPn q7 | SelPl q8 | SelC q9

q4 → CheckAv q13

q5 → CheckAv q14

q6 → CheckAv q15

q7 → CheckAv q17

q8 → CheckAv q18

q9 → CheckAv q19

q13 → Av q23 | NotAv q32

q14 → Av q24 | NotAv q32

q15 → Av q25 | NotAv q32

q16 → Nots q54 | Succ q3

q17 → Av q42 | NotAv q45

q18 → Av q43 | NotAv q45

q19 → Av q44 | NotAv q45

q23 → 10 q26,q27

q24 → 15 q28,q29

q25 → 55 q30,q31

q26 → Nots q34 | Succ q3

q27→ Nots q34 | Succ q3

q28→ Nots q37 | Succ q3

q29 → Nots q37 | Succ q3

q30→ Nots q40 | Succ q3

q31→ Nots q40 | Succ q3

q32 → Pnot q0

q42 → 5 q46, q47

q43 → 15 q16,q52

q44 → 10 q56, 57

q45 → Pnot q0

q46 → Nots q50 | Succ q3

q47 → Nots q50 | Succ q3

q52 → Nots q54 | Succ q3

q56 → Nots q59 | Succ q3

q57 → Nots q59 | Succ q3






## Production Rules for DFA

Q0 → Op1 Q1 | Op2 Q2 | SelNp D | Sel MR D | SelSpF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAv D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q1 → Op1 D | Op2 D | SelNp q4 | SelMR q5 | Selg SPF q5 | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q2 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm q7 | SelP1 q8 | SelC q9 |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q4 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q13 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q5 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q14 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q6 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q15 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q7 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q17 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q8 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q18 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q9 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv q19 | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q13 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av q23 | NotAV q32 | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q14 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av 24 | NotAV 32 | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q15 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av 25 | NotAV 32 | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q16 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q54 | Succ q3


Q17 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q18 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q19 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av q24 | NotAV q45 | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q23 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 q26,q27 | 15 D | 55 D | 5 D | NotS D | Succ D


Q24 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 q28,q29 | 55 D | 5 D | NotS D | Succ D


Q25 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS D | Succ D


Q26 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q34 | Succ q3


Q27 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q34 | Succ q3


Q28 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q37 | Succ q3


Q29 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q37 | Succ q3


Q30 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q40 | Succ q3


Q31 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS q40 | Succ q3


Q32 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 D | NotS D | Succ D


Q42 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D | 55 D | 5 q46,q47 | NotS D | Succ D


Q43 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 q16,q25 | 55 D | 5 D | NotS D | Succ D


Q44 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 q56,q57 | 15 D| 55 D | 5 D | NotS D | Succ D


Q45 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS D | Succ D


Q46 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS 50 | Succ 3


Q47 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS 5 | Succ 3


Q52 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS 54 | Succ 3


Q56 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS 59 | Succ 3


Q57 → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS 59 | Succ 3
D → Op1 D | Op2 D | SelNp D | SelMR D | Selg SPF D | SelPm D | SelP1 D | SelC D |
CheckAv D | Av D | NotAV D | Pmot D | 10 D | 15 D| 55 D | 5 D | NotS D | Succ D






## Table for op1 new status name

![cfg](https://github.com/user-attachments/assets/23408ea2-ee88-4579-9dce-117bfcd61f7b)





## OP1 CFG:

Start symbol: S
S → op1A | resetW | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D | notsD | succD

A → selnpB | selmrC | selspfE | op1D | checkD | yD | nD | pnotD | 10D | 15D | 5D | notsD | succD

W → ɛ

B → checkF | op1D | selnpD | selmrD | selspfD | yD | nD | pnotD | 10D | 15D | 5D | notsD | succD

C → checkG | op1D | selnpD | selmrD | selspfD | yD | nD | pnotD | 10D | 15D | 5D | notsD | succD

E → checkH | op1D | selnpD | selmrD | selspfD | yD | nD | pnotD | 10D | 15D | 5D | notsD | succD

F → yI | nJ | op1D | selnpD | selmrD | selspfD | checkD | pnotD | 10D | 15D | 5D | notsD | succD

G → yK | nJ | op1D | selnpD | selmrD | selspfD | checkD | pnotD | 10D | 15D | 5D | notsD | succD

H → yL | nJ | op1D | selnpD | selmrD | selspfD | checkD | pnotD | 10D | 15D | 5D | notsD | succD

I → 10M | 10N | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 15D | 5D | notsD | succD

J → pnotS | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | 10D | 15D | 5D | notsD | succD

K → 15O | 15P | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 5D | notsD | succD

L → 5R | 5Q | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | notsD | succD

M → succT | notsX | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

N → succT | notsX | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

O → succT | notsU | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

P → succT | notsU | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

R → succT | notsV | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

Q → succT | notsV | op1D | selnpD | selmrD | selspfD | checkD | yD | nD | pnotD | 10D | 15D | 5D

T → ɛ

X → ɛ

U → ɛ

V → ɛ


## Op1 strings: 

### Accepted Strings in OP1 examples :

Op1selspfchecky5succ

Op1selnpcheckmpnotreset

Op1selmrchecky15succ

Op1selnpchecky10succ





### Rejected Strings in OP1 examples :

Op1selnp

100

Op1selmr500

Op2



![1](https://github.com/user-attachments/assets/976293c9-1f14-4933-a130-d57ee07959d4)




![2](https://github.com/user-attachments/assets/889281b2-e27d-446f-88ad-12ad08f22a8d)




![3](https://github.com/user-attachments/assets/f1ae1d9a-c019-48a9-8dc3-f5876923fa1f)





![4](https://github.com/user-attachments/assets/f009a910-d136-4fd0-8a10-25c52ccf149f)






![5](https://github.com/user-attachments/assets/820d3558-6e87-472e-a174-8dc7ca8a7127)







