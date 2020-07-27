---
layout: page
title: Extending INSeq analysis
description: adding posthoc testing to ZINB modelling
img: /assets/img/12.jpg
importance: 3
---

INSeq experiments: a type of TnSeq using a Mariner transposon that inserts at TA sites

[Transit](https://github.com/mad-lab/transit) is a fantastic software package that uses a variety of methods to analyse INSeq data.

Historically, the most favoured method involves a Hidden Markov Model (HMM) that analyses each gene within a dataset to classify it into the following classes based on comparing read counts at each site to the average read counts in the area of the genome.
The classes include ES (essential), no or nearly no reads recovered; GD (growth defective), reduced reads recovered; NE (neutral), the average number of reads recovered; and GA (growth advantaged), increased reads recovered.
Comparing the classes a gene is classified as in different datasets enables us to score the relative importance of the gene in different conditions (e.g. carbon source, Fe availability).

This system works well, except when it doesn't.
The model is highly reliant on the quality of the data and can be skewed by high levels of reads at the outer edges of the genes, those that are unlikely to completely knock-out function.

A better method that is offered by Transit is the zero-inflated negative-binomial (ZINB) modelling approach.
The ZINB model 

[My solution](https://github.com/AroneyS/transit)


Recently, an update to Transit added log-fold changes information to the output of the ZINB method.1
