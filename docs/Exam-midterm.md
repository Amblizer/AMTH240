# Midterm

## Paper 2017


### Quiz-1

> Two "words" are considered equivalent if one is a rearrangement of the other. (Cat, act and cta 
    are considered same for example). How many three-letter words that are not equivalent can you 
    make?

We can choose 3 items from 26 letters and two spaces, so it's $26+2\choose 3$, or $28\choose 3$.

### Quiz-2

> Provide a 2 column proof: if $A \subseteq B$, then $\complement_U{A} \cup B = U$

To show $\complement_U{A} \cup B = U$, we need to prove $\complement_U{A} \cup B \subseteq U$ and $U \subseteq \complement_U{A}\cup B$

1. $\complement_U{A} \cup B \subseteq U$ is obvious by the definition of $U$.
1. To show $U \subseteq \complement_U{A}\cup B$:

\begin{align}
& \text{Let } x\in U \Rightarrow x\in A \text{ or } x\in \complement_U{A}.      &&\text{Definition of }U\\
& \text{If } x\in A  \Rightarrow x\in B \Rightarrow x\in \complement_U{A}\cup B &&A \subseteq B\\
& \text{If } x\in \complement_U{A} \Rightarrow x\in \complement_U{A}\cup B      &&\text{Definition of operator }\cup\\
\end{align}


### Quiz-3

> Use a 2-column and rules of inference with quantifiers to verify the validity of the following:<br>
1. All wizards at school must know how to make potions.<br>
2. All wizards who do magic outside of school must know how to cast spells.<br>
3. Harry is a wizard at school, but he doesn't know how to cast spells.<br>
4. Hermione knows How to cast spells but doesn't know hot ot make potions.<br>
Therefore Harry does not do magic out side of school and Hermione isn't a wizard at school.

$p(x)$: $x$ is a wizard at school.          <br>
$q(x)$: $x$ knows how to make potions.      <br>
$r(x)$: $x$ do magic outside of school.     <br>
$s(x)$: $x$ knows how to cast spells.       <br>

\begin{align}
(1) \text{ }& \forall{x}[p(x) \rightarrow q(x)]                 && \text{given}    \\
(2) \text{ }& \forall{x}[(p(x)\land{r(x)}) \rightarrow s(x)]    && \text{given}    \\
(3) \text{ }& p(Harry)                                          && \text{given}    \\
(4) \text{ }& \lnot{s(Harry)}                                   && \text{given}    \\
(5) \text{ }& (p(Harry)\land{r(Harry)}) \rightarrow s(Harry)    && \text{(2) Universal Spec}    \\
(6) \text{ }& \lnot (p(Harry)\land{r(Harry)})                   && \text{(4)(5) M. Tollen's}    \\
(7) \text{ }& \lnot p(Harry) \lor \lnot{r(Harry)}               && \text{(6) DMorgan}    \\
(8) \text{ }& \lnot{r(Harry)}                                   && \text{(3)(7) Disjunctive Syllogism}    \\
(9) \text{ }& \lnot q(Hermione)                                 && \text{given}    \\
(10)\text{ }& p(Hermione) \rightarrow q(Hermione)               && \text{(1) Universal Spec}    \\
(11)\text{ }& \lnot p(Hermione)                                 && \text{(9)(10) M. Tollen's}    \\
(12)\text{ }& \lnot{r(Harry)} \land \lnot p(Hermione)           && \text{(8)(11) Conjunction}    \\
\end{align}


### Quiz-4

> How many ways are there to place 10 books on 5 bookshelves, if the order of books relevant and 
    (a) shelf can be empty or (b) shelves can be left empty.

Because the order of books relevant, we arrange books first, which is $P(10, 5) = 5$.

If shelves can be empty, then we are assigning these $4$ bars in $5$ categories to 
$10+5-1$ places, which is $14\choose 4$, so number of ways are: 
$$
P(10, 5) \times {14\choose 4} = \dfrac{10!14!}{5!10!4!} = = \dfrac{14!}{5!4!}
$$

If shelves cannot be empty, then we are assigning these $4$ bars in $5$ categories to 
$10-1$ places, which is $9\choose 4$, so number of ways are: 
$$
P(10, 5) \times {9\choose 4} = \dfrac{10!9!}{5!5!4!}
$$

### Quiz-5

> How may permutations of the 26 different letters of the alphabet contain the pattern "DOG", 
    the pattern "CAT", or the "MICE" pattern?

Individual permutations:

- "DOG": $D = P(24, 24) = 24!$
- "CAT": $C = P(24, 24) = 24!$
- "MICE":$M = P(23, 23) = 23!$. 

The overall permutations is $C\cup D\cup M$, mind that elements included "DOG" and "CAT", "DOG" and "MICE" 
are partially overlapping. So in order to eliminate duplications, I use the Venn diagram helping me 
understand.
    
![Credit to MyDraw](AandBandC.png)

Venn diagram obviously shows that: 
$$
C\cup D\cup M = C + D + M - C\cap D - C\cap M - D\cap M + C\cap D\cap M
$$

Since:

\begin{align}
    C\cap D         &= P(26-6+2, 26-6+2) = P(22, 22) = 22!\\
    C\cap M         &= 0\\
    D\cap M         &= P(26-7+2, 26-7+2) = P(21, 21) = 21!\\
    C\cap D\cap M   &= 0
\end{align}

So:

\begin{align}
    C\cup D\cup M &= C + D + M - C\cap D - C\cap M - D\cap M + C\cap D\cap M\\
                  &= 24! + 24! + 22! - 22!
\end{align}
    
### Quiz-6

> Prove $S(n): \sum_{i=1}^n f_i^2 = f_nf_{n+1}$ for all $n$, where 
    $f_0 = 0, f_1 = f_2 = 1, f_{n+2} = f_n + f_{n+1}$.


### Quiz-7

> Let $a, b, c, d$ be positive integers. Prove $[(a|b)\land(c|d)\Rightarrow ac|bd]$.

\begin{align}
& (1) && a|b \Rightarrow b = an, n\in \mathbb{Z}    && \text{ Definition}\\
& (2) && c|d \Rightarrow d = cm, m\in \mathbb{Z}    && \text{ Definition}\\
& (3) && bd = (an)(cm) = (ac)(mn), mn\in \mathbb{Z} && \text{ (1)(2)}\\
& (4) && ac|bd                                      && \text{ (3) definition}\\
\end{align}

### Quiz-8

> Negate and simplify: $\forall x\exists y[(p(x, y)\land q(x, y))\rightarrow r(x, y)]$, 
    use 2 column proof format.

\begin{align}
\lnot[\forall x\exists y[(    p(x, y) \land q(x, y)) \rightarrow r(x, y)]&]  &&\text{ Negate}\\
\exists x\lnot[\exists y[(    p(x, y) \land q(x, y)) \rightarrow r(x, y)]&]  &&\text{ Negation of }\forall\\
\exists x\forall y\lnot[(     p(x, y) \land q(x, y)) \rightarrow r(x, y)]&   &&\text{ Negation of }\exists\\
\exists x\forall y\lnot[\lnot(p(x, y) \land q(x, y)) \lor        r(x, y)]&   &&\text{ Logically equivalent}\\
\exists x\forall y[\lnot\lnot(p(x, y) \land q(x, y)) \land \lnot r(x, y)]&   &&\text{ d'Morgan}\\
\exists x\forall y[(          p(x, y) \land q(x, y)) \land \lnot r(x, y)]&   &&\text{ Double negation}\\
\end{align}

### Quiz-9

> n/a