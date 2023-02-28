---
title: "Palindrome number"
description: "Return true is the number is palindrome else return false"
lead: ""
date: 2023-02-22T14:40:56+01:00
lastmod: 2022-02-22T14:40:56+01:00
draft: false
images: []
type: docs
weight: 2
---

A palindrome number is a number whose value doesn’t changes if we reverse its digits. 

Now let’s discuss different methods to detect if a number is palindrome or not. 

## Approach 1: By converting to string

We can convert the integer to string and then reverse the string. 
If the reverse of string is same as the orignal string then return true else return false. 

```python

     def isPalindrome(self, x: int) -> bool: 	 
        if x < 0: 		 
          return False 	 	 

        return s(x) == s(x)[::-1] 

```

### Complexity

**Time Complexity is `O(n)`**

Where `n` is the length of the string.

**Space Complexity is `O(n)`**


## Approach 2: Creating a new reversed integer from orignal integer and then checking if they are same

This is a simple program we will just extract digits one by one from the end of orignal number and then create a new integer by all those 
extracted digits.
// is used for floor division in python


```python
    def isPalindrome(self, x: int) -> bool: 
	  if x<0: 
		    return False 
 
	  tempNum = x 
	    newNum = 0 
	  while x>0: 
		    newNum = newNum * 10 + x%10 
		      x = x//10 
	return newNum == tempNum 
```
### Complexity

**Time Complexity is `O(n)`**

Where `n` is the length of integer.

## Approach 3: By reversing the half number.

This is a cool approach and will blow your mind. Her instead of reversing the whole number, 
we will just reverse half of it and then check if the original half and new half are same or not. 
eg 

If we have a number 13231 

Now as we have num = 13231 and take a rev variable with initial value = 0. Now 

Let’s reverse num by a loop and see what happens at each succesive iteration 

Num = 1323, rev = 1 

Num = 132, rev = 13 

Num = 13, rev = 132 

Here we can see when rev > num (which happens after 3 iterations) as we have crossed the half length of integer as it is odd length. 
If it would have been of even length (suppose 6 digits) we would have got 3 digits on both the sides.  

Now if digit is of even length the loop will exactly stop in the middle then compare the both rev and num, if both are equal then return true, 
in case if the digit is of odd length, then compare num and rev//10, if both are equal then return true else false. 
// is used to perform floor division so is we divide rev//10 it will return 132//10 = 13, which is equal to num. 


```python

    def isPalindrome(self, x: int) -> bool: 
	     if x < 0 or (x > 0 and x%10 == 0):   """ if x is negative, return False. if x is positive and last 
              return False                         digit is 0, that also cannot form a palindrome, return False."""
		     
	 
	      result = 0 
	      while x > result: 
		      result = result * 10 + x % 10 
		      x = x // 10 
		 
	    return True if (x == result or x == result // 10) else False 
```
### Complexity

**Time Complexity is `O(n)`**

Where `n` is the length of integer.

In last case the runtime of this approach will be better as compared to other as in case if the integer is very large, in that case this approach
will run only for half of the length of integer. In both of the above approaches full integer is iterated.

## Summary

In this Python tutorial, we learnt different ways to **check if a number is palindrome or not**

Prefer using reversing the half number method as here we need not to iterate for whole number this is optimised approach. Although it is modified approach of 
the second approach but is more efficient
