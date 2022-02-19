---
title: Stats Presentation
description:
author: Sibacharan Das and *not* Myla Eshwar
keywords: stats
theme: uncover
class: invert
---

# **Bayes' Theorem** Problems
---

## **Bayes'** *Theorem*

`PREREQUISITES`

Let $E1, E2,…, En$ be a set of events associated with a sample space $S$, where all the events $E1, E2,…, En$ have *nonzero probability* of occurrence and they form a **partition of S**. Let $A$ be any event associated with $S$, then according to Bayes theorem.

---
$$
P(A_i|B) = \frac{P(B|A_i)P(A_i)}{P(B)} = \frac{P(B|A_i)P(A_i)}{\sum_{j=1}^{n}P(B|A_j)P(A_j)}
$$

---

## Something...

>Bayes' Theorem does: it helps us update a hypothesis based on new evidence.

>Try not to get overwhelmed or lost in the question. Always begin by writing down what you want to discover.

>Under Bayes theorem no theory is perfect. Rather ,it is a work in progress ,always subject to further refinement and testing

---

# <!-- fit --> :book: **QUESTIONS**

---
# Question **1**
 > Let’s work on a simple **NLP problem** with Bayes Theorem. By using NLP, I can detect **spam e-mails** in my inbox.

---

 - Assume that the word `offer` occurs in $80\%$ of the *spam* messages in my account.
 - Also, let’s assume `offer` occurs in $10\%$ of my *desired* e-mails.
 - If $30\%$ of the *received* e-mails are considered as a **scam**, and I will receive a new message which contains `offer`, _what is the probability that it is a spam?_

 ---

## Defining the **events**
- A : Spam
- B : Contains the word `offer`

#### :clipboard:Given Probabilities

$$
P(B|A) = 0.8\\
P(A) = 0.3
$$

---
Now we will find the probability of e-mail with the word `offer`. We can compute that by adding the number of emails with the word `offer` in *spam* and *desired* e-mails.

---
### Such that,
$$
\begin{align*}
P(B) &= (0.3)(0.8) + (0.7)(0.1)\\
&= 0.31
\end{align*}
$$

<!-- footer: "*B **:** contains the word `offer`" -->

---
#### So, the Required **Probability** is...
$$
\begin{align*}
P(A|B) &= \frac{P(B|A) P(A)}{P(B)}\\
P(E) &= \frac{0.8 * 0.3}{0.31} = \fbox{77.42\%}\\
\end{align*}
$$

<!-- footer: "*A **:** spam\n *B **:** contains the word `offer`" -->
---
<!-- footer: "" -->
# Question **2**
 > Let’s now predict the weather on Marie's wedding tomorrow.
---

- Marie is getting married tomorrow, at an outdoor ceremony in the desert.
- In recent years, it has rained only $5$ days each year. Unfortunately, the weatherman has predicted rain for tomorrow.
- When it actually rains, the weatherman **correctly forecasts** rain $90\%$ of the time.
- When it doesn't rain, he **incorrectly forecasts** rain $10\%$ of the time. _What is the probability that **it will rain** on the day of Marie's wedding?_
---
## **Answer**
---
- Assuming that there are $365$ days in the year (non-leap year)

- We know that it rains $5$ times a year. Weatherman predicts with $90\%$ accuracy on these $5$ days.
So `the numerator` of our answer is the *favourable outcome* $= (0.9)(5) = 4.5$

- `the Denominator` is favourable outcome $(4.5)$ and the Weatherman's prediction
going wrong $(360\times0.1)$
#### Total $= (4.5) + (360\times0.1) = 40.5$

---
#### **Probability** of it actually raining
$$
P(\text{rain})= \dfrac{4.5}{40.5} = \dfrac{1}{9} = \fbox{11.11\%}
$$
---
<!-- footer: "" -->
# Question **3**
 > Making strategic decisions using customer demographics...
---

- You are selling a product in an area where $30\%$ of the people live in the **city** and _the rest_ live in the **suburbs**.

- Currently $20\%$ of the `city dwellers` user your product and $10\%$ of the `suburbanites` use your product.
---

#### You are presented with **two new sales strategies**...

- the first will increase your market share in the **suburbs** to $15\%$.
- The second will increase your market share in the **city** to $25\%$.
---

_Which strategy should you adopt?_ What **percentage** of the people who own your product are city dwellers **before your new sales drive**?

---
## **Answer**
---

City population = $0.3$ & Suburb population = $0.7$.
$$$$
As $20\%$ of the city dwellers used the product
`City dwellers` using the product $= 0.2 \times 0.3 = 0.06$
$$$$
As $10\%$ of the suburb population
`Suburbanites` using the product $= 0.1 \times 0.7 = 0.07$

---

### First **Strategy** :
From `Suburbs`, $10\% \rightarrow 15\%$

New users $= 0.05 \times 0.7 = \fbox{0.035}$

---
### Second **Strategy** :
From `City`, $20\% \rightarrow 25\%$

New users $= 0.05 \times 0.3 = \fbox{0.015}$

---
$$
\fbox{0.035 > 0.015}
$$
> We can clearly see that
the **first strategy should be adopted**.

---
##### **Also**, $P(\text{City dwellers}|\text{Own our Product})$
$$
=\tfrac{0.06}{0.06 + 0.07}
=\fbox{0.46}
$$
---
# <!-- fit -->ॐ **SAI**RAM
