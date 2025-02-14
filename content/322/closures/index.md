---
author: John Hammond
title: "Assignment 1: Closures"
mathjax: true
ShowBreadCrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

Implement the transitive, reflexive, and symmetric closure algorithms.
<!--more-->

Familiarize yourself with the [basics of the assignments](../basics/) and ask questions if you have them!

## The assignment:

Given the matrix representation of a relation, find the reflexive,
symmetric, and transitive closure of the relation. 

This finds the smallest possible equivalence relation for the given set
and initial relation.

## Input:

-   A plaintext file of exactly two lines
    -   The first line completely describes a finite set.
    -   The second line contains a 0-1 matrix in the format { {row}, {row},
        ... , {row} }
-   You can assume that if you have n elements on the first row, that
    the matrix will be a well-defined n x n matrix.

Example:

``` text
a, b, c, d, e
{{0, 0, 1, 0, 0}, {1, 0, 0, 1, 0}, {1, 0, 0, 0, 0}, {0, 1, 0, 0, 0}, {0,0,0,0,1}}
```

You can find an example [input file
here](./relationsTestData.txt). Once again, your program will be run as `./student.o test.txt`, or `python3 student.py text.txt`, etc.

## Output

-   To *stdout*: an $n\times n$ 0-1 matrix in the format described
    above that is the transitive, reflexive, and symmetric closure of the initial relation.

``` text
{{1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {0, 0, 0, 0, 1}} 
```

There should be **nothing** else printed to stdout.

I will be trimming out whitespace, so don't worry about that.

## Submitting

Post your source file to the assignment in Blackboard. If there's necessary (nonstandard) headers or supplemental files, be sure to include them. Please also tell me how you compiled your assignment (maven, g++, javac) if relevant.