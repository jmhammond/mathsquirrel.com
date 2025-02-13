![](./WSULogo.png){alt="Wichita State Logo" title="Wichita State Logo!"
align="right" width="200px"}

# Programming in a Math class???

I know. It\'s awesome.

In Math 321, Discrete Mathematics 1, we built together the core
data-structures of mathematics: logical statements, sets, functions,
matrices, ... We explored what we could do with them. We explored
conjecturing about what could be accomplished, and *proved* whether
those conjectures were true or not.

In this class, we take all of those structures and employ them in
interesting algorithms to solve problems. Want to see if you can get
from point A to point B? What if you wanted to visit every local brewery
in Wichita without your designated driver driving over the same street
twice? Want to search a large set of text for some word(s)?

This class will give you the very basics.

# Grading and expectations

## How it\'s going to be graded:

-   I will be piping the output of your program to my own grading
    program.
-   It will read your output and compare it to the calibrated correct
    output. I will be trimming whitespace, however it must be correctly
    comma and bracket delimited.
-   If your output matches the expected output, you get full credit
    (yay!)
-   If your output doesn't match the expected output, it's considered
    wrong and I send it back to you with the test file. It is up to you
    to fix the program and resubmit it for one less point.
-   Each time I send a program back, or each day it is late, you lose
    one point. (For example, if it's late two days and I send it back
    once before it's corrected, that's 7/10)
-   You are required to meet the expected input / output standards
    above. If your program doesn't (*EVEN IF IT CORRECTLY RUNS YOUR TEST
    DATA*), it is still considered incorrect and must be resubmitted.
-   I run Linux. I accept:
    -   gcc, g++
    -   Python2 and python3
    -   Java, Kotlin (or some modern language on the JVM)

## I will run your program giving it the filename as a command line argument:

For example, if Sammy sent me a sammyChapter11.cpp that I compile to
sammyChapter11, I\'ll call:

``` {.bash org-language="sh"}
./sammyChapter11  testInput.txt
```

In reality, all of this is happening via a python script that wraps your
executable I/O to compare against correctly computed values, however
this is the specification I am requiring of you.

## But wait, how do I read a filename from the command line?

### In C++:

Instead of using

    int main(void) {
    ...
    }

You\'ll write your program using the following template:

    #include <string>
    #include <fstream>
    #include <iostream>
    using namespace std;
    int main(int argc, char* argv[]) {
        if (argc > 1) {     
            ifstream fin;
            fin.open(argv[1]);
        // ... do stuff with the file... 
            string aLineWeRead;
            getline(fin, aLineWeRead); 
        ...
      }
    }

For further reading, search Google, specifically for results from
StackOverflow, and feel free to ask me if you need help.

### In Python

Here\'s a basic template you can use:

``` python
import sys

with open(sys.argv[1]) as f: 
   # do something with the file
   aLineWeRead = f.readline()
   ...
...
```

### In Java

If you\'re using standard java, the main state member will be:

``` java
class Chapter9 {
...
    public static void main(String[] args) { 
       // do something with the file; note: the filename is args[0]. 
       ...
    } 
...
}
```

### Other languages

You\'re on your own.

These three are the ones used by past students for these projects. I
know all of you know C++, so that\'s within your reach. If you want to
use another language, go for it. [Kotlin](https://kotlinlang.org) is a
pretty sweet language that runs on the JVM.

## Writing to *stdout*

All of the programs will output to *stdout*. I use this output data to
compare against correctly computed values. You can do this via a number
of mechanisms in your chosen Language. Here is one way in each of the
above listed languages:

-   In C++, it\'s *std::cout \<\< \"text\"*
-   In Python, you can use *print(\"text\")*
-   In Java, it\'s *system.out.println(\"text\")*

# Assignment 1 - Relations

Given the matrix representation of a relation, find the reflexive,
symmetric, and transitive closure of the relation.

This finds the smallest possible equivalence relation for the given set
and operation.

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
here](http://www.math.wichita.edu/~hammond/math322/Chap9TestData.txt).

## Output

-   To *stdout*: an $n\times n$ 0-1 matrix in the format described
    above.

``` text
{{1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {1, 1, 1, 1, 0}, {0, 0, 0, 0, 1}} 
```

There should be **nothing** else printed to stdout[^1].

# Assignment 2 - Graphs

## Implement Dijkstra\'s Algorithm

In this assigment you will implement Dijkstra\'s algorithm to determine
the shortest path from one point to another.

### Input

-   Plaintext file with a lot of lines.
-   The first line lists the vertices in the graph
-   The second line lists the start vertex and end vertex
-   The third through last lines of the file list the edges and
    associated weights

``` text
a,b,c,d
a,c
a,b,2
c,b,4
a,c,7
d,a,3
c,d,8
c,c,1
```

which corresponds to the graph:

![](chapter10graph.png)

Here is a [sample test file](./Chap10DijkA.txt)

### Output

Output two lines to stdout. The first line will be the weight, and the
second line will be the path from the start to the end vertex. In the
example above, this will be:

``` text
6
a, b, c
```

# [TODO]{.todo .TODO} Assignment 3 - Trees {#assignment-3---trees}

Implement questions #8 and #9 in the following way:

You will write a calculator that can compute prefix and postfix notation
depending on input. If the input begins with an operator, it's prefix.
If the line begins with a number, it's postfix.

Note: You shouldn't store values using ints. If we divide, ints lose
decimal values. Do you computations with floats or doubles. Further, the
numbers will not be single characters. You should parse the string by
splitting at spaces, not *char* by *char*

## Input

One or more lines of computations, properly formatted in pre- or
post-fix, with everything separated by spaces

``` text
+ 4 - 1 * 3 5
3 2 + 1 - 8 /
8 7 / 14 * 
```

Here is a [sample test file](./Chapter11TestData.txt)

## Output

To *stdout*, the answer to each question, one line per answer

For the above example:

``` text
-10
0.5
16
```

### Note: Not all number have good floating point representations.

For example, type this into the python interpreter:

``` text
>>> 0.1 + 0.2
```

You'll see

``` text
0.30000000000000004
```

So that we don't have to worry about representation in this assignment
(that's not the point), if you print to stdout the number
0.30000000000000004, my checker will be smart enough to know that your
calculation should be 0.3. I will compute *abs(your answer - mine) \<
0.001*.

# [TODO]{.todo .TODO} Assignment 4 - Boolean Algebra {#assignment-4---boolean-algebra}

Given a table of values of a Boolean Function, express the function only
in terms of $*$ and $-$. Boolean product and complement, no Boolean
sums!

## Input

A table of values, each line a row and each column separated by commas:

``` text
x, y, f
1, 1, 1
1, 0, 0
0, 1, 1
0, 0, 1
```

Here is a [sample test file](./Chapter12TestData.txt)

## Output

There are multiple possible answers, of course. I\'m requesting that the
output format use parentheses, -, and \* as below. A solution to the
above problem is:

``` text
-(-(x*y)*x)
```

which is to mean the in-class representation
$\overline{(\overline{(x\cdot y)}\cdot x)}$. It\'s a little ugly, but it
works.

There are other equivalent formulations. If your\'s is equivalent, you
will receive full credit. I am not asking that you minimize the function
(though you\'ll do this in Circuits).

# [TODO]{.todo .TODO} Assignment 5 - Automata {#assignment-5---automata}

Number 8 from this chapter: Given the test of ordered tuples of a
*nondeterministic*) finite state automaton and a string, determine
whether the string is recognized by the machine

## Input

### My ideas behind my input choices:

-   I\'m choosing to label the states *s0, s1, s2, ... s10, s11, ...*
-   Rather than using a state table, I\'ll write everything as ordered
    tuples, as we do with Turing Machines
-   The format of the tuple is (initial state, next state, input)
-   Note that the input parameters will define the possible alphabet. It
    coule be letters or numbers
-   

### The input:

-   The first line is a string that may or may not be recognized by the
    machine

-   The second line is a list of final states (one or more, comma
    separated)

-   We assume the starting state is s0

-   The next $n$ lines (until the end of file) will be ordered tuples
    which completely determine the FSA

    Here is a [sample test file](./Chapter13TestData.txt)

### Sample FSA

1.  Input file:

    ``` text
    ababbabab
        s2
        (s0, s1, a)
        (s0, s2, a)
        (s0, s2, b)
        (s1, s2, b)
        (s2, s0, a)
        (s2, s2, b) 
    ```

2.  Associated graph:

    Note: you don\'t have to draw a graph! I\'m presenting this here so
    you can compare the FSA with the list of tuples in order to make
    sense of the input.

    ``` {.dot file="chapter12.png" cmdline="yes"}
      digraph {
      rankdir=LR;
      rank="same";
        size = "6,4";
        node [shape = doublecircle]; s2;
        node [shape = circle];
        s0 -> s1 [label = "a" ];
        s0 -> s2 [label = "a, b" ];
        s1 -> s2 [label = "b" ];
        s2 -> s0 [label = "a" ];
        s2 -> s2 [label = "b" ];
    }
    ```

3.  Output:

    > yes

## Output {#output-5}

-   yes or no, (one word, lowercase) depending on whether the string is
    recognized.
-   The answer to the above input is yes.

# Footnotes

[^1]: This may seem arbitrary, but it\'s the specifications to interface
    with my grading utility. Meeting arbitrary specifications for
    interface compatibility is an important part of being a programmer.
    Welcome to your career.
