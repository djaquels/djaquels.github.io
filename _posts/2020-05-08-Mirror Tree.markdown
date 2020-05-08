---
title: "IsMirror Tree Code - A Functional Aproach"
layout: post
date: 2020-06-04 22:48
image: /assets/images/posts/spongebob.jpg
headerImage: true
tag:
- functional programming
- algorithms
- clojute
category: blog
author: djacales
description: How I Solve The NULL Repository issue after bad wiring on Srping.
---

Hector Daniel Jacales Rojas <hjacales@gmail.com>
	

#### Algorithm 

    We need to find if a a binary tree is a Mirror, a tree is a mirror if the
    left branch is symetric to the right branch. This means that we can draw an imaginary line in the middle of the tree
    and the branches most be equal.

    The data structure of a binary tree is quite simple:
    Tree : {
        value : integer
        left :  Tree || Null
        right : Tree || Null
    }

#### EXAMPLE


Is Symetric.
```
    1
   / \
  2   2
 / \ / \
3  4 4  3

```

It's not symetric.
```
   1
   / \
  2   2
 / \ / \
3  4 5  3
```



## Solution

I wanted to use a functional aproach, beacause i consider that using functional programming languages is
very usesful whe working with trees. For the easy that is translate the algorithm into code.

We can either use iteration or recusion to read a tree, but recursion is a little bit more familiar to the
way brains work.

## Code


The way we can find if a tree is symetris is by reading node by node both in the left and right branch.
If we call L the Left Branch and R the Right branch.
We need to ensure  L.value is equal to R.value and after this we need to do the same for the L.left
L.right nodes  and R.right , R.left nodes.

We use a logic and so if there is two pairs of nodes when the validation fails we can know the tree is not symetric.


The implementation on the clojure language (A JVM pure functional language) looks like this.

```clojure
-- mi own solution

(defn mirror [ t1 t2 ]
    (cond 
        (and (nil? t1) (nil? t2)) true
        :else (and (= (:value t1) (:value t2)) (mirror (:left t1) (:right t2)) (mirror (:right t1) (:left t2))  )
    )
)
(defn isTreeSymmetric [t] 
    (mirror t t )
)

```
Just a few lines of code and we can solve the problem. This is what i like about functional programming.

## My Favorite Solution

This solution by [@simonsirak](https://app.codesignal.com/profile/simonsirak) i like a lot. The solution use the Haskell language
another good functional programming language.

```haskell

isTreeSymmetric Null = True
isTreeSymmetric (Tree v Null Null) = True
isTreeSymmetric (Tree v l Null) = False
isTreeSymmetric (Tree v Null r) = False
isTreeSymmetric (Tree v (Tree lv ll lr) (Tree rv rl rr)) =
    lv == rv && (isTreeSymmetric (Tree v ll rr)) && (isTreeSymmetric (Tree v lr rl))


```
It uses a similar aproach but implemented using matching patterns. A great tool Haskell offers.