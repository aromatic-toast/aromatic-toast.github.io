---
layout: post
title:  "Introduction to Basic Datatypes in R"
summary: "Numerics, Characters, Integers, Logicals Oh My!"
author: lesleymiller
date: '2020-12-30 1:11:23 +0530'
category: tutorials
thumbnail: /assets/img/posts/workstation.png
keywords: R, data types
permalink: /blog/introduction-to-data-types-in-R/
usemathjax: true
---

# To Future Fellow R Enthusiasts

If you are new to the R programming language, then this introductory post on the most common data types in R is for you. 
We will cover the basic data types of numeric, character, integer and logical. If all these terms are new to you, don't worry; by the end, you will be an R data type pro!

A good conceptual understanding of data types is important to prevent much sorrow in your future programming life. 
I can't count how many hours I've lost debugging my programs because I didn't realize I was working with the wrong data type. 
Data types in R serve a purpose in computer language that is similar to different parts of speech in a human language. 
The parts of speech in English, like nouns (i.e. a Sally, Vancouver or chair), verbs (ie jump, run, drive) and adjectives (ie green, large, salty) are all words, but they each have a distinct job to do when constructing a sentence that is meaningful. 
The parts of speech or collection of words can be thought of as bits of data in a sentence and they all have a different "type". If I made a sentence with all nouns for example, *Sally pig book chair.*, you would have no idea what I was trying to tell you. 
I must combine the words or bits of data in just the right way to make a meaningful message, *The pig sat on the chair.* This sentence is still a bit silly, but at least you know what I'm trying to communicate.

Similarly in R, we need different data types to express ourselves to a computer. The basic data types in R include the following:
- numeric
- integer
- character 
- logical

These types are like our nouns, verbs and adjectives in English. Just like in English, they have rules about where and how they can be used. 
Let's look closer at the type, *numeric*. 

This is *numeric* data in R:
```r
1
1.0
-3
2345.4939
```
All of these numbers are numeric and probably look pretty familiar to you. If you assign a number to a variable like this,

```r
x <- 1
```
R will automatically store it as a *numeric* as opposed to an *integer*. If you want an *integer* instead, then you can do the following:

```r
# adding the L after 4 specifies that 4 is an integer
x <- 4L
typeof(x)
[1] "integer"

# this uses a function to turn 4 explicitly into an integer
x <- as.integer(4)
typeof(x)
[1] "integer"

```

*Numerics* and *integers* just represent any number you you need for calculation and pretty much work the way you would expect. 
They differ in how the computer stores them in memory but you probably won't care much about this distinction in your day to day work. 

Next, let's look at the type *character*. 

```r
# this is a string with a single letter
"A"

# this is a sequence of letters
"Hello, my name is Lesley."

# this is a character that contains a sequence of numbers
"123"
```
All of the above examples are of the type *character*. They are used to represent any sort of text and the letters must be encased in quotation marks to be valid.
 *Characters* are also called *strings* in other languages like Python. 

The last data type we will look at is of type *logical*. These are referred to as *Booleans* in other programming languages. 

```r
TRUE
FALSE
```
This type only has two values and can be useful when you need to ask questions in your programs that have only yes and no answers. 
As a fun side note, R stores `TRUE` as a 1 and `FALSE` as a zero. As you will soon see, this is very useful when performing certain kinds of tasks. 

Here is an example of how to form some R expressions using the types we have learned about: 
```r

# create some numeric objects
my_numeric1 <- 4
my_numeric2 <- 7

# create a character object
my_character <- "Hello, my name is Lesley!"

# ask a yes no question, print out the sequence of text if question evaluates to `TRUE`.
if(my_numeric1 < my_numeric2){
    print(my_character)
    }
[1] "Hello, my name is Lesley!"
```
The above code block, demonstrates the R data types in action. 
I created some numeric and textual data and stored them in some variable objects `my_numeric1`, `my_numeric2` and `my_character`. 
I asked a yes/no question which evaluates to`TRUE` since 4 is less than 7, and as a consequence, my character text will get printed out. 
It's important to keep in mind that some functions in R can only operate on certain data types. 
If your program is throwing an error, sometimes you have passed data into a function that you think is of a certain type and underneath it is different than what you intended. 
For this reason, it is a good idea to double check the `class` of your objects now and then and be sure they are what you think they are. 

```r

# make a character object
x <- "Hello, my name is Lesley!"

# this will throw an error because the mean function 
# can not calculate the mean of a character
# mean will only accept numeric data
mean(x)

[1] NA
Warning message:
In mean.default(x) : argument is not numeric or logical: returning NA


# calling class function on an object will return the underlying data type for that object 
class(x)
[1] "character"
```
That's about it. I hope you enjoyed this short introduction to data types in R. Happy R programming! 








Attribution:
 The explanation of numerics and integers was inspired by this discussion on [Stack Overflow](https://stackoverflow.com/questions/23660094/whats-the-difference-between-integer-class-and-numeric-class-in-r).