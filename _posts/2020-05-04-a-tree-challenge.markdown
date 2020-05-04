---
title: "A tree challenge"
layout: post
date: 2020-05-04 22:48
image: /assets/images/markdown.jpg
headerImage: true
tag:
- markdown
- components
- extra
category: blog
author: djacales
description: Algoritmic challenge
---

## Summary:

On codesignal.com we can find interesting code challenges we can use to practice for an
interview or just to past the time in a fun way.

There i found this challge, where we have a binary tree.

## My Solution 

```java
//
// Binary trees are already defined with this interface:
// class Tree<T> {
//   Tree(T x) {
//     value = x;
//   }
//   T value;
//   Tree<T> left;
//   Tree<T> right;
// }}
boolean flag = false;
int getSum(Tree<Integer> root,int s,int c){
    if (root == null){
        return 0;
    }
    if (root.left == null && root.right == null){
        //is leaf
        if((c + root.value) == s){
            flag = true;
        }
        return root.value;
    }
    if (root.left == null){
        return root.value + getSum(root.right,s,c + root.value);
    }
    if (root.right == null){
        return root.value + getSum(root.left,s,c + root.value);
    }
    return root.value + getSum(root.left,s,c + root.value) + getSum(root.right,s,c + root.value);
}
boolean hasPathWithGivenSum(Tree<Integer> t, int s) {
    int sum = getSum(t,s,0);
    System.out.println(flag);
    return flag;
}

```
## A Simpler Solution
This is other aproach by the user [@jakzo](https://app.codesignal.com/profile/jakzo) that i found interesting.
```javascript
function hasPathWithGivenSum(t, s) {
    if (!t) return s === 0;
    s -= t.value;
    return hasPathWithGivenSum(t.left, s) ||
           hasPathWithGivenSum(t.right, s);
}
```