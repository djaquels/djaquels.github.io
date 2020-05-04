---
title: "A tree challenge"
layout: post
date: 2020-05-04 22:48
image: /assets/images/posts/spongebob.jpg
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

There i found this challge, where we have a binary tree, we can call them T , and a integer number named S.
Our goal is to find if its a path from root to any leaf, where the sum of each node is eqaul to the target number S.

I share two solutions, the first is my own solution i code. And the second is a different aproach i like it when 
i read the code.

(In the website once you solve the problem , you can watch others developers code).

## My Solution 

My aproach was as follow, i can read the Tree by using a recursive algorithm. Also i have a record
where i store the sum from the root to te leaf. Once i found a leaf (When T.left and T,right are Null), i check if the sum is equal to S and update a flag, that tells if the path exists.

After reading all nodes, i return the flag value.


#### The Code:

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

There are one proble with this code, the first is that even if i find the path, i still have to read the rest of the nodes.

So i also share this other solution.

## A Simpler Solution
This is other aproach by the user [@jakzo](https://app.codesignal.com/profile/jakzo) that i found interesting.

In the next code the aproach is that i start from S and every node i rest the node valuo (T) to S.
When i found a leaf i check if the s value is equal to 0 . That indicates the path exists.

The code still has the issue that we have to read all the tree. But i think with this aprach we can have
a cleaner code. (Not using global variables as i did).



#### The Code:


```javascript
function hasPathWithGivenSum(t, s) {
    if (!t) return s === 0;
    s -= t.value;
    return hasPathWithGivenSum(t.left, s) ||
           hasPathWithGivenSum(t.right, s);
}
```

## Conclusion 

I like this kind of challenges because its force you to think and keeps you warm on topics
as algorithms, data structures, etc...

And the fact that you can compare yourself with others developers, its great so you can measure your skills.
With people from all the world. And adopt good practices you see from others coders.

