# SOLUTIONS:
### Here are the solutions as recorded online when available
---

## Table of Contents  
- [Monday, April 15, 2019](#monday-april-15)
- [Sunday, April 14, 2019](#sunday-april-14)
- [Satuday, April 13, 2019](#saturday-april-13)
- [Friday, April 12, 2019](#friday-april-12)

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

## Friday, April 12, 2019 -- 9:00 AM <a class="anchor" id="friday-april-12"></a>
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