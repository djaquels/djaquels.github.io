---
title: "R Language Fundamentals"
layout: post
date: 2020-05-12 22:48
image: /assets/images/posts/spongebob.jpg
headerImage: true
tag:
- R 
- statistics
- Data Science
category: blog
author: djacales
description: R languages notes
---

Hector Daniel Jacales Rojas <hjacales@gmail.com>

## R LANGUAGE FUNDAMENTALS

R language is a statistical language used  a lot in data science and as a statistic tool. This is a resume of some notes i take in a course I'm taking about R.

```R
#variables declarations
age <- 2 # by default numbers are set to double
ageInt <- 2L # by appendind L we splicit declare a number is an integer
grades <- c(8,7,6,8) # create a custome vector using the auxial c function
myseq <- seq(1,15,3) # create a sequence in a vector from 1 to 15 with steps of 3

#while loop
while(condition){
    // comands
}
# for is for iterations
for(i in 1:5)
{
    print(i) # iterates over a sequence
}
if(condition){
    //true statments
}else{
    // false statments
}
# work with vectors
names <- c("Messi","Ronaldo","Griezmann")
names[0] # character(0)
names[-1] # ("Ronaldo", "Grienzmann")
names[1:3] # ("Messi","Ronaldo","Griezmann")
names[1:5] # "Messi"     "Ronaldo"   "Griezmann" NA          NA  
names[c(1,2)] # "Messi"   "Ronaldo"
names[seq(3,1,-1)] #"Griezmann" "Ronaldo"   "Messi"


```
