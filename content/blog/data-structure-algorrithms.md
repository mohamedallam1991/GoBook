---
draft: true
title:  Data structure and Algorithms
date: 2022-09-03
# url: algorithms
# showTaxonomies: ["Go"]
tags: ["Go"]
categories: ["Beginner"]
---

An algorithm is a plan, a set of step-by-step instructions to resolve a problem. And there is two ways to represent that.

<!--more-->

## Intro

As a programmer, everything you are doing, is representing and manipulating data, in a form a shape or another.
However smoe terminology and jargon may scare you, this brief intro, explains you the need for data structure.

## Why Data structure
Say you are using your email, Gmail for instance, you have inbox, draft, sent emails and so on, when you navigate you reach out to one of them right?
Sometimes you even filter or sort them.
This is you doing data structure in action.

## What is data structure

A collection of some data, is data structure. there is data values, and some sort of relationship between them.
You might perform operations on them, maybe remove a value, or add a value.
So a data strucutre, is a collection of data values, the relationships among them, and function or operations that can be applied to them.



## Complexity analysis

To measure the effectivenss of your solution, we use a complexity measurement, of course sometimes the best solution is the one you can implement in a faste manner, however if we speak of computational resources there is 2 things, time complexity and space complexicty, reffered to as, Space Time complexity.

<!-- prettier-ignore-start -->
{{< chart >}}
type: 'line',
data: {
  labels: ['1', '3', '3', '4', '5', '6', '7'],
  datasets: [{
    label: 'Complexity analysis',
    data: [0, 59, 80, 81, 56, 55, 40],
    tension: 0.2
  },
  {
    label: 'Complexity analysis',
    data: [0, 80, 59, 56, 55, 40],
    tension: 0.2
  }]
}
{{< /chart >}}
<!-- prettier-ignore-end -->

## Bits and bytes

Anything with two separate states can store 1 bit,  electric charge in a chip = 0/1, spots of North/South magnetism = 0/1 for hard drives, but that alone is useless.
Lets group 8 bits together, now you have 1 byte. a collection of 8 bits, now we can store a charachter, say "A" or "b" or "$", exanple wouold be `01011000`
## How many patterns?

| Number of bits | Patterns |
| --- | ----------- |
| 1 | 0 1 |
| 2 | 00 01 10 11 |
| 3 | 000 001 010 011 100 101 110 111 |


Now how many patterns?
Memory has slots, each slot is a byte, a byte is 8 bits, a bit is either a 0 or 1.
So if we say a byte it might be `01011000` or `01011011` or any sequence of 8, combination of 0 and 1.

[source](https://web.stanford.edu/class/cs101/bits-bytes.html)
