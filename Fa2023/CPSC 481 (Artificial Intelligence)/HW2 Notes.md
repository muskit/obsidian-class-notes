## Question 5
![[Pasted image 20230909000011.png]]
Assume unnumbered path costs are **1**.
Heuristic cost of each node (relative to G) are as follows:

|h|h(n)|
|---|---|
|A|5.1|
|B|4.1|
|C|3.9|
|D|4|
|E|2.2|
|F|3.8|
|G|0|
|H|3.7|
|J|7|
|K|6|
|L|4|
|M|0.5|
|N|1.5|
|P|1.8|
|S|4.5|
```
S               | Frontier: A(6.1) B(5.1) C(5.9)
S B             | Frontier: A(6.1) C(5.9) D(6) E(4.2) F(4.8)
S B E           | Frontier: A(6.1) C(4.9) D(6) F(4.8) M(2.5)
S B E M         | Frontier: A(6.1) C(4.9) D(6) F(4.8) N (2.5)
S B E M N       | Frontier: A(6.1) C(4.9) D(6) F(4.8)
S B E M N F     | Frontier: A(6.1) C(4.9) D(6) P(3.8)
S B E M N F P   | Frontier: A(6.1) C(4.9) D(6) G(2.0)
S B E M N F P G | Frontier: A(6.1) C(4.9) D(6)
```
