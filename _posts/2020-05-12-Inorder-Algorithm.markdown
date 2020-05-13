---
title: "Read a Tree efficienlty"
layout: post
date: 2020-05-12 22:48
image: /assets/images/posts/spongebob.jpg
headerImage: true
tag:
- functional programming
- algorithms
- groovy
category: blog
author: djacales
description: How to read a binary tree inorder way with morris algorithm, groovy implementation.
---

Hector Daniel Jacales Rojas <hjacales@gmail.com>

This is an algorithm to read a tree inorder way time and space efficently because we don't need to use a stack or recursion to read the tree.

## Tree Structure

```groovy
class Node {
    int value;
    Node left;
    Node right;
}
```



## Inorder Search Algorithm

The steps are the next. First we start at root. We start our iterable variable, lets call it currentNode pointing to root.

Then we need to check for current until is null, that means we finish. So this is our loop condition.

There may be two cases, either current.left exist or it doesn't.

If it does exist we can make current equals to the right child of the rightmost node in current's left subtree. After this we can go to the left of the tree.

If it doesn't exist then we can operate with the node. (print node value for example). And then when need to go to the right of the tree.

## Implementation

```groovy
void MorrisTransversal(root){
    Node current = root
    Node pre = null
    // groovy while check for null authomaticly
    while(current){
        if (!current.left){
            println(current)
            current = current.right
        }else{
            pre = current.left
            while(pre.right && pre.right != current ){
                pre = pre.right
            }
            if(!pre.right){
                pre.right = current
                current = current.left
            }else{
                pre.right = null
                println(current.value)
                current = current.right
            }
        }
    }
}
```

