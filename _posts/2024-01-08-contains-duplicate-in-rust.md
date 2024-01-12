---
title: Solution to Contains Duplicate in Rust
author: derrick
date: 2024-01-08 14:10:00 +0800
categories: [Leetcode_Solutions, Blind_75]
tags: [problems]
render_with_liquid: false
math: true
comments: false
---

## Introduction

This is one part of a 75-part series where I post my solutions to the Blind 75 in Rust. The solutions are sourced from my previous work in Python and the notes I wrote accompanying them.

My solutions will contain three parts for each question.

1. **Code.** This includes the solution of the given question in Rust.
2. **Big idea.** This is an explaination to the "trick" contained in the problem.
3. **Runtime analysis.** This is an explaination of the time-complexity for my solution algorithm.

## Contains Duplicate (Easy)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

### Code

```rust
use std::collections::HashSet;
impl Solution {
    pub fn contains_duplicate(nums: Vec<i32>) -> bool {
        let mut number_set = HashSet::<i32>::new();
        for number in nums {
            if number_set.contains(&number) {
                return true
            }
            number_set.insert(number);
        }
        false
    }
}
```

### Big idea

HashSets provides us with a memory and time efficient way to keep track of the given numbers. We simply check if an element exists in our HashSet and return true if it does. If we iterate through all of the given numbers without a duplicate, we simply return false.

### Runtime analysis

This algorithm runs in $$O(n)$$

Lookup on a HashSet is $$O(1)$$, and we are doing this for an array nums of given length n.


