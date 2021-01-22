---
layout: post
title:  "What is the Central Limit Theorem?"
#summary: 
author: lesleymiller
date: '2021-01-21'
category: tutorials
thumbnail: /assets/img/posts/height_density_plot.png
keywords: statistics
permalink: /blog/what-is-the-clt
usemathjax: true
---

If you have taken any introductory stats course, one of the first things you will learn about is the `Central Limit Theorem`. Even though its a core statistical concept, I'll admit that it took awhile to wrap my head around it the first time and understand what it really meant and why it was important. This blog post will attempt to demistify the concept of CLT by using practical illustrations. I'll address the following questions: 

1) Why is CLT so central to statistics? 
2) Is the concept useful? 
3) How should I use it as a data scientist? 

Okay here we go...

## What is CLT: Jargon Version 
The CLT is a theoretical result that says the sampling distribution of a statistic resembles a normal distribution even if the underlying population is not normal. However, this result is based on a couple of underlying assumptions. 

1) The sample size is "large enough" (usually greater than 30)
2) The underlying population isn't too skewed away from normal

## What is CLT: Intuitive Version 
Okay huh? What did any of the above mean? Though the above explanation is correct let's step through a thought experiment together to get an intuitive feel for what is going on underneath. 

Let's say you wanted to know the typical height of an human. Of course you can't go out and measure the height of every single human out there (all 1.7 billion of them) because that would get really boring after probably person 100,000. So the next best thing is to measure the heights of a much smaller portion of people and compute the average of them. So let's say you go out and measure the heights of 100 people and you get 1.7 meters. You want to be sure of your estimate so you go out and measure another 100 people and get an average of 1.8 meters.

But let's say you kept doing this over and over, what CLT says is that regardless of what the underlying distribution of human heights are, if you were to take lots and lots of samples of 100 you would over time collect a distribution of those averages that you computed. As you drew more and more samples from the same population, the distribution of these averages would resemble a bell-shaped curve or a Gaussian distribution. The hump of the curve would center around the true population average height. The standard deviation of this curve would shrink the more samples you took.

Okay so CLT is referring to the distribution of your sample means if you took repeated samples. That makes a bit more sense. But how do we know that this theoretical result is actually true? Well, we can use some Python code to simulate this thought experiment and prove to ourselves that this is true. Let's check it out! 

## CLT Illustrated 

<script src="https://gist.github.com/aromatic-toast/ae54baf83816bc6afe725ea5d2cb81ab.js"></script>



