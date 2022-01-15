---
layout: post
title: "What World Are We Building?"
date: "2016-01-27 15:51:52 +1100"
category: link
tags: [analytics, bias, machinelearning]
external-link: https://points.datasociety.net/what-world-are-we-building-9978495dd9ad#.kkf3y4ieb
---

danah boyd asks "What World are we Building" in [this excellent post][db1]. It's a thoughtful piece, which reflects on the recent history of social media, and extrapolates some of the underlying trends into our next generation of technologies. In particular, there's something of a call-to-arms around data analytics, and the need to be thoughtful about the subjectivity of the data and results.

<blockquote> 
One of the perennial problems with the statistical and machine learning techniques that underpin “big data” analytics is that they rely on data entered as input. When the data you input is biased, what you get out is just as biased. These systems learn the biases in our society, and they spit them back out at us.
</blockquote> 

It's so tempting, when working with aggregate data sets, to assume that the outputs are objective, that they somehow get at a fundamental truth. Here, we are reminded that both the data and the insights we derive from them are fundamentally subjective. Worse, the real-world effects of forgetting this are significant, and affect people in real ways. 

<blockquote>
We are moving into a world of prediction. A world where more people are going to be able to make judgments about others based on data. Data analysis that can mark the value of people as worthy workers, parents, borrowers, learners, and citizens. Data analysis that has been underway for decades but is increasingly salient in decision-making across numerous sectors. Data analysis that most people don’t understand.
</blockquote> 

There's two important lessons from this as security people. 

First, security teams are increasingly building data collection and analysis tools. They go by many names -- security incident and event management systems, forensics, hunting, investigation support -- but they largely support the data analysis and prediction workflows that danah references. In building these systems, we should be thoughtful both about the data that's collected and the insights we derive from them; we need to respect the subjectivity of the data and the analysis in how we respond to what they tell us. 

Second, security teams are often very well placed to spot these data prediction systems being build by other parts of our organisations. Bringing these issues to the attention of system owners early in the process can help our organisations make better decisions, and hopefully design out some of the dangers. 

<blockquote>
We must learn how to ask hard questions of technology and of those making decisions based data-driven tech. And opening the black box isn’t enough. Transparency of data, algorithms, and technology isn’t enough. We need to build assessment into any system that we roll-out.
</blockquote>

[db1]: https://points.datasociety.net/what-world-are-we-building-9978495dd9ad#.kkf3y4ieb
