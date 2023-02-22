---
title: "4 ways to return keys as list in pyhton"
description: "Different methods of fetching keys of a dictionary as list"
date: "2023-02-22T00:00:05+09:00"
draft: false
link: ""
author: "tribhuvan0"
image: ""

---

## Overview of dictionary in python 

Dictionary is python data type which is used to store key-value pair. It is ordered, mutable and does not allow duplicates.

A dictionary has a syntax as given below:

```
myDict = {key1 : value1, key2 : value2, key3 : value3}
```

The keys must be of same data type, but values can be of any data type.

## Methods to fetch keys from a Python dictionary as list

There are a lot of cases wherein we would be required to get keys as a list in python.

Therefore, lets dive deep into the different methods


## Using `for()` loop

Using for loop, we can access the keys of element and then store in a list.

The list method `append()` can be used to insert the keys of dictionary in the list.


```python
myDict = {1 : 'abc', 2 : 'pqr', 3 : 'xyz'}
myList = []
for x in myDict:
    myList.append(x)
    
print(myList)
```
Output:
```
[1, 2, 3]
```
Isn't this code somewhat lengthy, let's go for some less lines of codes and make it more cleaner

## Using list comprehension

The example shown below shows this in action

```python
myDict = {1 : 'abc', 2 : 'pqr', 3 : 'xyz'}
myList = [k for k in myDict]
print(myList)
```
Output:
```
[1,2,3]
```

By this method the code looks more cleaner

## Using list literal

For python version greater than or equal to 3.5 (python >=3.5) unpacking into list literal can be used.

“ * “ is the unpacking operator, and it works with any object that is iterable, and since on iteration 
dictionaries return their keys, they can pe inserted into a list on unpacking.

```python
myDict = {1 : 'abc', 2 : 'pqr', 3 : 'xyz'}
myList = [*myDict]
print(myList)
```
Output:
```
[1,2,3]
```

## Using `keys()` method of the dictionary object

The keys() method returns dictionary_keys data type, which can be converted to list using typecasting.
This is an inbuilt python functino which returns keys and we store in a list.

```python
myDict = {1 : 'abc', 2 : 'pqr', 3 : 'xyz'}
my_list = list(myDict.keys())
print(my_list)
```
Output:
```
[1, 2, 3]
```
It's pretty simple and easy. 

## Conclusion

In this article we discussed about the various methods by the help of which we can get a list of keys from a `python` dictionary.

We started off by discussing the novice method and then slowly looked how efficiently we can get the list of keys.
