# Daily Challenges Posted Here

#### Most Recent Update: Friday, April 12 -- 12:00 PM EST

##  Sunday, April 14, 2019
*Posted by [Stephan](https://github.com/osterburg) on Friday, April 12 at 5:30 PM*

*Credit to [Stephan](https://github.com/osterburg) for posting to Slack*

Given a singly linked list of integers `l` and an integer `k`, remove all elements from list `l` that have a value equal to `k`.

Example:
For `l = [3, 1, 2, 3, 4, 5]` and `k = 3`, the output should be `removeKFromList(l, k) = [1, 2, 4, 5]`;

```python
# Definition for singly-linked list:
class ListNode(object):
 	def __init__(self, x):
		self.value = x
 		self.next = None
```

The following [blog](https://medium.com/@kojinoshiba/data-structures-in-python-series-1-linked-lists-d9f848537b4d) helps explaining what a linked list is.

---

## Saturday, April 13, 2019
*Posted by [Andrew Wester](https://github.com/steeznation16) on Friday, April 12, at 11:30 AM*

*Credit to [Rafael Carrasco](https://github.com/erdosn) for posting in Slack*

Some interesting data science interview questions that I’ve faced are:
1) How would I design a function that takes in a string (mathematical) and solves the expression
2) Given a list of words write a loop to find anagrams in the list. Ex: `anagram_finder(['bat', 'tab', 'cat', 'this', that']) -> ['bat', 'tab']`
3) What is a p-value?
4) What is the difference between random forest and gradient boosting?

---

## Friday, April 12, 2019 -- 11:30 AM
*Posted by [Andrew Wester](https://github.com/steeznation16) on Friday, April 12 at 11:30 AM*

*Credit to [Stephan](https://github.com/osterburg) for posting to Slack*

**Question (note: This problem was asked by [Uber](uber.com))**

Given an array of integers, return a new array such that each element at index i of the new array is the product of all the numbers in the original array except the one at i.

For example, if our input was [1, 2, 3, 4, 5], the expected output would be [120, 60, 40, 30, 24]. If our input was [3, 2, 1], the expected output would be [2, 3, 6].

---

## Friday, April 12, 2019 -- 9:00 AM
*Posted by [Andrew Wester](https://github.com/steeznation16) on Friday, April 12 at 9:00 AM*

*Credit to the [Daily Coding Problem](https://www.dailycodingproblem.com/) on their website on Friday morning*

**Question (note: this question was asked by [Amazon.com](amazon.com)):** 

There's a staircase with N steps, and you can climb 1 or 2 steps at a time. Given N, write a function that returns the number of unique ways you can climb the staircase. The order of the steps matters.

For example, if N is 4, then there are 5 unique ways:

- 1, 1, 1, 1
- 2, 1, 1
- 1, 2, 1
- 1, 1, 2
- 2, 2

What if, instead of being able to climb 1 or 2 steps at a time, you could climb any number from a set of positive integers X? For example, if X = {1, 3, 5}, you could climb 1, 3, or 5 steps at a time. Generalize your function to take in X.

---

## Friday, April 12, 2019 -- 8:30 AM
*Posted by [Andrew Wester](https://github.com/steeznation16) on Friday, April 12 at 8:30 AM*

Today's question was posted on Slack yesterday by [Stephan](https://github.com/osterburg)

**Question:**

Write a function `solution(A, K)` where, given a list of numbers and a number K, return whether any two numbers from the list add up to K.

For Example: Given the array A = [10, 15, 3, 7], and K = 17, `solution(A, K)` should return `TRUE`, since 10 + 7 = 17

**BONUS:** Can you do this in one pass?

---

## Thursday, April 11, 2019
*Posted by [Andrew Wester](https://github.com/steeznation16)) on Friday, April 12 at 8:15 AM*

This question is from a coding challenge that [Andrew](https://github.com/steeznation16) had the other day as part of applying for a job.  The question was hosted through [Codility](https://app.codility.com/programmers/) which has many interesting challenges available.

**Question:**

You are given a bag of coins, and asked to flip each coin and record the results in an array, where 0 is Heads, and 1 is Tails.  The array has a length of N, and values will only be 0 or 1.  

Write a function `solution(A)` where, given the array (A), you calculate the least number of coins that need to be flipped over in order to make all coins in the array the same.

For Example: Given the array A = [1, 0, 1, 1, 1, 0, 0, 1, 1, 0], `solution(A)` should return `4`, since there were 4 Heads recorded and 6 Tails.  Thus, the 4 Heads would need to be flipped to Tails in order for all 10 coins to show Tails.