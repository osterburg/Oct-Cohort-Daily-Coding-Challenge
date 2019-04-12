# SOLUTIONS:
### Here are the solutions as recorded online when available
---

## Table of Contents  
- [Monday, April 15, 2019](#monday-april-15)
- [Sunday, April 14, 2019](#sunday-april-14)
- [Satuday, April 13, 2019](#saturday-april-13)
- [Friday, April 12, 2019 11:30am](#friday-april-12-3)
- [Friday, April 12, 2019 9:00am](#friday-april-12-2)
- [Friday, April 12, 2019 8:30am](#friday-april-12-1)
- [Thursday, April 11, 2019](#thursday-april-11)

---
---

## Monday, April 15, 2019 <a class="anchor" id="monday-april-15"></a>
### Solution Posted:
#### Solution Posted & Formatted By:

---
---

## Sunday, April 14, 2019 <a class="anchor" id="sunday-april-14"></a>
### Solution Posted:
#### Solution Posted & Formatted By:

---
---

## Saturday, April 13, 2019 <a class="anchor" id="saturday-april-13"></a>
### Solution Posted:
#### Solution Posted & Formatted By:

---
---

## Friday, April 12, 2019 -- 11:30 AM <a class="anchor" id="friday-april-12-3"></a>
### Solution Posted: Friday, April 12, 2019 -- 10:30AM PST
#### Solution Posted & Formatted By: [Stephan](https://github.com/osterburg)

The solution was posted by [Danyal](https://github.com/DanyalAndriano) in the group slack channel on Friday, April 12. 


```python
import numpy as np

def list_prod(l):
    return [np.prod([a for a in l if a != i]) for i in l]

l = [1, 2, 3, 4, 5]
print(list_prod(l))
```

---

## Friday, April 12, 2019 -- 9:00 AM <a class="anchor" id="friday-april-12-2"></a>
### Solution Posted Friday, April 12, 2019 -- 9:45 AM
#### Solution Posted & Formatted By: [Andrew Wester](https://github.com/steeznation16)

It's always good to start off with some test cases. Let's start with small cases and see if we can find some sort of pattern.

* N = 1: [1]
* N = 2: [1, 1], [2]
* N = 3: [1, 2], [1, 1, 1], [2, 1]
* N = 4: [1, 1, 2], [2, 2], [1, 2, 1], [1, 1, 1, 1], [2, 1, 1]

What's the relationship?

The only ways to get to N = 3, is to first get to N = 1, and then go up by 2 steps, or get to N = 2 and go up by 1 step. So f(3) = f(2) + f(1).

Does this hold for N = 4? Yes, it does. Since we can only get to the 4th step by getting to the 3rd step and going up by one, or by getting to the 2nd step and going up by two. So f(4) = f(3) + f(2).

To generalize, f(n) = f(n - 1) + f(n - 2). That's just the Fibonacci sequence!

<center><img src='Solutions_IMG/Solution 1 - Pic 1.png'>

Of course, this is really slow (O(2<sup>N</sup>)) — we are doing a lot of repeated computations! We can do it a lot faster by just computing iteratively:

<center><img src='Solutions_IMG/Solution 1 - Pic 2.png'>

Now, let's try to generalize what we've learned so that it works if you can take a number of steps from the set X. Similar reasoning tells us that if X = {1, 3, 5}, then our algorithm should be f(n) = f(n - 1) + f(n - 3) + f(n - 5). If n < 0, then we should return 0 since we can't start from a negative number of steps.

<center><img src='Solutions_IMG/Solution 1 - Pic 3.png'>

This is again, very slow (O(|X| <sup> N </sup>)) since we are repeating computations again. We can use dynamic programming to speed it up.

Each entry cache[i] will contain the number of ways we can get to step i with the set X. Then, we'll build up the array from zero using the same recurrence as before:

<center><img src='Solutions_IMG/Solution 1 - Pic 4.png'>

This now takes O( N * |X| ) time and O( N ) space.

---

## Friday, April 12, 2019 -- 8:30 AM <a class="anchor" id="friday-april-12-1"></a>
### Solution Posted Friday, April 12, 2019 -- 12:00 PM
#### Solution Posted & Formatted By: [Andrew Wester](https://github.com/steeznation16)
#### Solution Credit to [Stephan](https://github.com/osterburg) for posting in Slack

The official solution was posted by [Stephan](https://github.com/osterburg) in the group slack channel on Friday, April 12.  

```python
def solution(A, K):
    seen = set()
    for num in A:
        if K - num in seen:
            return True
        seen.add(num)
    return False
```

Other solutions solved by students from the [Flatiron School's Online Immersive Data Science Bootcamp](https://flatironschool.com/career-courses/data-science-bootcamp/online/) October Cohort are as follows:

From [Danyal](https://github.com/DanyalAndriano) on Thursday, April 11 in the afternoon on slack, she came up with:

```python
import itertools
def solution(A):
    return any(sum(combination) == 17 for combination in itertools.combinations(A, 2))
    ```

## Thursday, April 11, 2019 <a class="anchor" id="thursday-april-11"></a>
### Solution Posted Friday, April 12, 2019 -- 12:00 PM
#### Solution Posted & Formatted By: [Andrew Wester](https://github.com/steeznation16)
#### Solution Credit to [Andrew](https://github.com/steeznation16)

I have not found any other solutions for this, but this is the exact solution I used for my coding challenge that I was given.  Please feel free to add your own options for solutions!

```python
def solution(A):
    count = 0
    heads = 0
    tails = 0
    for i in A:
        if i == 0:
            heads += 1
        else:
            tails += 1
    print("Total Heads: {}".format(heads))
    print("Total Tails: {}".format(tails))
    if heads > tails:
        return tails
    elif heads < tails:
        return heads
    else:
        return (heads + tails // 2)
    ```