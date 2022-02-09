---
title: Missionaries and Cannibals Puzzle
description: A proposed solution for
author: Yuki Hattori
keywords: marp,marp-cli,slide

image: https://marp.app/og-image.jpg

theme: uncover
class: invert
---

### **Missionaries and Cannibals** Puzzle
> Three Missionaries and Three Cannibals need to cross the river...
https://hgup.github.io/slides/09-02-2022-Missionary-and-Cannibal-Puzzle.html
---

# **Constraints**

- The boat can carry **at most two people**,
- **For both banks**, that the missionaries present on the bank cannot be outnumbered by cannibals **or** $n \geq m$
- The _boat cannot cross the river by itself_ with no people on board.

---
<!-- backgroundColor: white -->
# <!-- fit --> :innocent:
<!-- We will use this to represent Missionaries -->
---
<!-- backgroundColor: black -->

# <!-- fit --> :smiling_imp:
<!-- Their ulterior motives -->

---
<!-- backgroundColor: default -->
# :innocent::innocent::innocent:&emsp;|&emsp;|&emsp;&emsp;
# :smiling_imp::smiling_imp::smiling_imp:&emsp;|&emsp;|&emsp;&emsp;
#### :boat:&emsp;&emsp;&emsp;&emsp;&emsp;
---

| Bank 1                                                   |            Boat            |                                                                Bank 2 |
|:---------------------------------------------------------|:--------------------------:|----------------------------------------------------------------------:|
| :innocent::innocent::innocent::smiling_imp::smiling_imp: |        :smiling_imp:       |                                                                       |
| :innocent::innocent::smiling_imp::smiling_imp:           |   :arrow_right::innocent::smiling_imp:  |                                                                       |
| :innocent::innocent::smiling_imp::smiling_imp:           |        :smiling_imp::arrow_left:       |                                                            :innocent: |
| :innocent::innocent::smiling_imp:                        | :arrow_right::smiling_imp::smiling_imp: |                                                            :innocent: |
| :innocent::innocent::smiling_imp:                        |        :smiling_imp::arrow_left:       |                                               :innocent::smiling_imp: |
---
| Bank 1                                                   |            Boat            |                                                                Bank 2 |
|:---------------------------------------------------------|:--------------------------:|----------------------------------------------------------------------:|
| :innocent::smiling_imp:                                  | :arrow_right::innocent::smiling_imp:    |                                               :innocent::smiling_imp: |
| :innocent::smiling_imp:                                  |        :smiling_imp::arrow_left:       |                                     :innocent::innocent::smiling_imp: |
| :innocent:                                               | :arrow_right::smiling_imp::smiling_imp: |                                     :innocent::innocent::smiling_imp: |
| :innocent:                                               |        :smiling_imp::arrow_left:       |                        :innocent::innocent::smiling_imp::smiling_imp: |
|                                                          |   :arrow_right::innocent::smiling_imp:  |                        :innocent::innocent::smiling_imp::smiling_imp: |
|                                                          |                            | :innocent::innocent::innocent::smiling_imp::smiling_imp::smiling_imp: |
---
# How do I **represent** it in code?

---
> ...when you need to represent the missionary-cannibal river-crossing puzzle in code. Use **lists**...

###### &emsp;&emsp;&emsp;&emsp;&emsp;**- Sun Tzu** (Art of War)

---
# <!-- fit --> Use **Lists**!
---
##### `B1 = [M, C, Boat]` on **Bank 1**
- **M** represent number of Missionaries
- **C** represent number of Cannibals
- **Boat** tells us whether the boat is on **B1** or not.
---
##### `B2 = [M, C]` on **Bank 2**
- **M** represent number of Missionaries
- **C** represent number of Cannibals
---
##### `B = [M, C]` is the **Boat**
- **M** represent number of Missionaries
- **C** represent number of Cannibals
---
```python
# B1: Bank 1, B2: Bank 2 and B: Boat
B1 = [3, 3, True]
B2 = [0, 0]
B = [0, 0]
```
---
```python
# step: represents the step number in process
step = 1
print(the current state)

#terminate when no one is left on the first bank
while Bank B1 is not empty:

  # PROGRESS

  # MAINTAINENCE
  step += 1
  print(the current state)
```
---
```python
# step: represents the step number in process
step = 1
print(the current state)

#terminate when no one is left on the first bank
while Bank B1 is not empty:

  # PROGRESS
  if Boat is on bank 1:
    # TODO on Bank 1

  else: # Boat is on bank 2
    # TODO on Bank 2

  # MAINTAINENCE
  step += 1
  print(the current state)
```
---
# `B[0]` and `B[1]`
---
```python

# init: Put a single cannibal on the boat
B1[1] -= 1
B[1] += 1

```
---
### **COM**: _Cannibals Outnumbered Missionaries_
---
```python
#terminate when no one is left on the first bank
while Bank B1 is not empty:

  # PROGRESS
  if Boat is on bank 1:
    # TODO on Bank 1 👈🏻

  else: # Boat is on bank 2
    # TODO on Bank 2

  # MAINTAINENCE
  step += 1
  print(the current state)
```
---
```python
# TODO on Bank 1
if remove one missionary -> COM:
  # put a cannibal on the boat

else: # no COM if missionary is removed
  # put a missionary
```  
---
```python
# TODO on Bank 1
if B1[0] - 1 < B1[1]: # COM when 1 Missionary is put on boat
  B1[1] -= 1
  B[1] += 1

else: # no COM when 1 Missionary is put on boat
  B1[0] -= 1
  B[0] += 1
```  
---
```python
#terminate when no one is left on the first bank
while Bank B1 is not empty:

  # PROGRESS
  if Boat is on bank 1:
    if B1[0] - 1 < B1[1]: # COM when 1 Missionary is put on boat
      B1[1] -= 1
      B[1] += 1

    else: # no COM when 1 Missionary is put on boat
      B1[0] -= 1
      B[0] += 1

  else: # Boat is on bank 2
    # TODO on Bank 2 👈

  # MAINTAINENCE
  step += 1
  print(the current state)
```
---
```python
# TODO on Bank 2
if there is a missionary on the boat:
  # Drop the Missionary on Bank 2

else: # there are two cannibals on the boat
  # Drop a Cannibal on bank 2


```  
---
```python
# TODO on Bank 2
if B[0] == 1: #a Missionary on the boat
  B[0] -= 1
  B2[0] += 1

else: # there are 2 Cannibals on the boat
  B[1] -= 1
  B2[1] += 1

```  
---
```python
while Bank B1 is not empty:
  # progress
  if B1[2]: # Boat is on bank 1
    if B1[0] - 1 < B1[1]: # COM when 1 Missionary is put on boat
      B1[1] -= 1
      B[1] += 1
    else: # no COM when 1 Missionary is put on boat
      B1[0] -= 1
      B[0] += 1
  else: # Boat is on bank 2
    if B[0] == 1: # if there is a Missionary on the boat
      B[0] -= 1
      B2[0] += 1
    else: # if there are 2 Cannibals on the boat
      B[1] -= 1
      B2[1] += 1

  # maintainence

  step += 1
```
---
```python
B1 = [3, 3, True]
```
---
```python
while not(B1[0] == 0 and B1[1] == 0):
  # progress
  if B1[2]: # Boat is on bank 1
    if B1[0] - 1 < B1[1]: # COM when 1 Missionary is put on boat
      B1[1] -= 1
      B[1] += 1
    else: # no COM when 1 Missionary is put on boat
      B1[0] -= 1
      B[0] += 1
  else: # Boat is on bank 2
    if B[0] == 1: # if there is a Missionary on the boat
      B[0] -= 1
      B2[0] += 1
    else: # if there are 2 Cannibals on the boat
      B[1] -= 1
      B2[1] += 1
  # maintainence
  B1[2] = not B1[2]
  step += 1
  print(f"Step {step}\t:", B1, B, B2,sep='\t'
```

---
```python
print(f"Step {step}\t:", B1, B, B2,sep='\t')
```

`Step 2	:	[2, 2, False]	[1, 1]	[0, 0]`

<!-- remember to comment the line before running the code -->
---
# <!-- fit --> :innocent::+1:
---
# <!-- fit --> :imp::-1:
---
# <!-- fit --> DONE!
