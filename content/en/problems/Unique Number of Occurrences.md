---
title: "Check if occurence of every number is unique in array"
description: "Given an array of integers arr, return true if the number of occurrences of each value in the array is unique, or false otherwise."
lead: ""
date: 2023-02-22T14:40:56+01:00
lastmod: 2023-02-22T14:40:56+01:00
draft: false
images: []
type: docs
weight: 2
---

There are two ways to check if two strings are anagrams or not in Python without using sorting. 

1. Using element Counting
2. Using `Counter()`

## Approach 1: Brute force approach or element counting

The problem can be found out at https://leetcode.com/problems/unique-number-of-occurrences/ this link. 

We will discuss two approaches to solve this problem. Initially we will start with brute force approach. 

The basic approach one can try is to:-
1. create another empty list and 
2. then by using two for loops count the occurrenceof each and every element in the given array
3. store that count in our new list. 
4. Then convert the count list in set

after converting to list we will only be getting unique values and we will compare the length of count(which contains the count of each element) and 
set formed by elements of count. If there is a difference we will return false else true. You will get more insight of this point in second appraoch

```python

    class Solution: 
    def uniqueOccurrences(self, arr: List[int]) -> bool: 
        d={} 
        count =[] 
        for i in arr: 
            if i in d: 
                d[i]=d.get(i)+1 
            else: 
                d[i]=1 
        for k,v in d.items(): 
            count.append(v) 
        return len(count)==len(set(count))

```


### Complexity

**Time Complexity is `O(n^2)`**

Where `n` is the length of the array.

**Space Complexity is `O(n)`**


## Approach 2: Using `Counter()`.

Instead of two `for` loops we can use Python built in function `Counter()` which is part of `collections`.

In this approach we will use counter container. Countainer is a container in collections module. 
Counter is an unordered collection where elements are stored as dict keys and their count as dict value. 
The logic here is we will store each element in counter and counter stores data as key value pair with data as key and its frequency as value. 

Eg: arr = [1,2,2,1,1,3] 

Now if we pass this array to counter 

```
newArr = Collections.Counter(arr) 
print(newArr) 
```

It will print  

```
Counter({1: 3, 2: 2, 3: 1}) 
```

We can see the digits and their counts are stored in this. 

Now length of counter is 3, we will also prepare a set of of values in counter which will be
`dict_values([3, 2, 1])`, it’s length is also three as all three numbers are distinct so we will get true. 

Let’s look at a case where it will be false 

Let arr = [2,2,3,3,4,4,6,6] 

Now let’s pass it to counter 

```
newArr = collections.Counter(arr) 
print(newArr) 
```

It will print  
```
counter({2: 2, 3: 2, 4: 2, 6: 2}) 
```

Here length of counter is 4 as there are 4 keys, but if we look clearly we will find that there are all the values 2
hence if we prepare a set of all the values of this counter we will get dict_values([2, 2, 2, 2]) and when we convert
it to set(which stores all values uniquely) we will get only `{2}` and the length of this set will be 1 as we have only 
one unique element 2. Hence it will return false. 

Let’s code this approach 


```python

    def uniqueOccurrences(self, arr: List[int]) -> bool: 
        c = collections.Counter(arr) 
        return len(c) == len(set(c.values())) 
```

### Complexity

**Time Complexity is `O(n)`**

Where `n` is the length of the array.

**Space Complexity is `O(n)`**

## Summary

In this Python tutorial, we learnt different ways to **to check unique occurence of values in an array.**

Prefer using dictionary based method(counter mehtod) as here time complexity is better.
