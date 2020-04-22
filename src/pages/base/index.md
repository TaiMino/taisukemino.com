---
title: Decimal, Binary and Hexadecimal Basics for Programmers
description: >-
  decimal, binary and hexadecimal basics for programmers.
date: '2020-04-22T08:35:22.632Z'
keywords: []
slug: /@taisukemino/base
language: "en"
---

### Introduction
> “There are 10 kinds of people in the world — those who understand binary and those who don't.”
> Anonymous

You will know what this quote means by the end of this post. Read along :)


### Base 10
Normally, we count in a base 10, which means we represent every number using ten symbols(0 ~ 9). In this counting system, once we get over the symbol 9, we combine the symbols to create new numbers:
```
0 1 2 3 4 5 6 7 8 9
10 11 12 13 14 15 16 17 18 19
...
```

The “base” of a counting system is the number of symbols used to represent all the numbers in the world. We, humans, primarily use the base 10 probably because we have ten fingers. 


## Base 2
A computer uses a base 2 system. 

When counting in the base 2, we use only two symbols(0 and 1). Once we get over the symbol 1, we combine the symbols to create new numbers:
```
0 1
10 11
...
```

Why does a computer use the base 2 system at all? Here is the short answer. Every number in a computer is an electrical signal. It is reliable when you distinguish only between the “on” state and the “off” state as opposed to setting a specific voltage for each symbol with the base 10.

The base 2 system is the simplest number system possible. If you want something simpler than the base 2, you'll have to get rid of the 1. But we can't do much of anything with a 0. 


## Base 16
A base 16 system is another widely used counting system. It uses the same symbols as the base 10 (0,1,2,3,4,5,6,7,8,9) up to 9. But they also have six more symbols: A,B,C,D,E, and F. Once we get over the symbol
F, we combine the symbols to create new numbers:
```
0 1 2 3 4 5 6 7 8 9 A B C D E F
10 11 12 13 14 15 16 17 18 19 1A 1B 1C 1D 1E 1F
...
```

Since the base 16 system uses 16 symbols, a single-digit can show 16 different values. This means 15 in the base 10 is F in the base 16. We can count up to 15 without having to add a second digit in the base 16. It’s more compact. 

The primary purpose of the base 16 system is to provide a shorthand for the base 10 or 2 system. 

Below, you can see that the equivalent value of 4 digits in the base 2 uses only a single digit in the base 16: 
[image:B9397B07-5453-4B1A-9FB6-5265F8BF7190-98339-0001CCB520ACC322/image_1.png]

If you want to express large numbers, the base 16 can do that more shortly than the other two systems. The most common use of the base 16 today comes in the form of describing color online.
```
000000 => black ⚫️
FF0000 => red 🔴
FFFFFF => white ⚪️
```


## Summary
By changing the number of symbols available to you, you can make any base system for counting. Since the base 10, 2 and 16 systems are common, we have another name for each:

```
base 10: decimal
base 2: binary
base 16: hexadecimal
```

Now you perhaps know what the quote means?
> “There are 10 kinds of people in the world — those who understand binary and those who don't.”


It was using binary. Since 10 in binary is 2 in decimals, we can say that:
> “There are 2 kinds of people in the world — those who understand binary and those who don't.”


#writing
