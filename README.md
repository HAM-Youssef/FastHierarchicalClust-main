[![Build Status](https://travis-ci.com/Janiikson/M2AlgoHAC.svg?branch=main)](https://travis-ci.com/Janiikson/M2AlgoHAC)


# M2AlgoHAC Vignette
### Janikson Garcia Brito
#### Evry Paris-Saclay University
### Avril 3, 2025

> [Quick Start](#qs)

> [The 4 algorithms at fixed data length](#com)

> [Microblenchmark](#micro)

> [Time complexity](#time)

<a id="qs"></a>

## Quick Start

The `M2algorithmique` R package is an **example package** developed for students building their own R/Rcpp package as part of the **algorithmic M2 courses in Data Science master's program at Evry Paris-Saclay University**. This package contains some algorithmic strategies (**HAC_naive** and **HAC_improved**) implemented in R and in Rcpp.


# Hierarchical Agglomerative Clustering (HAC)

## Introduction

**Hierarchical Agglomerative Clustering (HAC)** is a clustering technique that builds a hierarchy of clusters by iteratively merging the closest pairs based on a similarity metric, such as Euclidean distance. The result is a **dendrogram** illustrating the nested structure of clusters.

### Algorithmic Challenge

The primary algorithmic challenge lies in its computational complexity. A naïve implementation requires constructing an \( n \times n \) distance matrix (\( O(n^2) \)) and updating it over \( n-1 \) merging steps, each involving \( O(n^2) \) operations, yielding a total complexity of \( O(n^3) \).

This cubic scaling limits its applicability to large datasets, necessitating more efficient approaches.

## Problem Statement

HAC, as described above, performs a series of pairwise distance computations and iterative updates, leading to a prohibitive computational cost for large datasets. As the dataset size grows, the time complexity increases significantly, making it infeasible to handle very large datasets efficiently.

## Objectives

1. Implement a **naïve HAC** algorithm in **R** and **Rcpp**.
2. Compare the computational performance between the naïve and improved versions of HAC.
3. Investigate how **distance matrix updates** contribute to the high complexity and propose solutions using more efficient data structures, such as **k-d trees**.

## Next Steps

The next step will involve testing and profiling the algorithm's performance, followed by optimization techniques to reduce the complexity, including leveraging efficient data structures and improving the algorithmic steps involved in merging clusters.


### Package installation

You first need to install the `devtools` package, it can be done easily from Rstudio.
We install the package from Github (remove the # sign):

```{r}
#devtools::install_github("Janiikson/M2AlgoHAC")
library(M2AlgoHAC)
```

### A first simple test


We simulate simple data 