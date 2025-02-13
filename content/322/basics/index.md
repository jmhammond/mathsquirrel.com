---
author: John Hammond
title: Basics for the assignments
mathjax: true
ShowBreadCrumbs: true
showTableOfContents: true
tocopen: false
showDate: false
---

How are we doing what we're doing?
<!--more-->

So nearly everyone has opened files in C++ or other languages before. Hooray! We'll go ahead and take it one step further and read from `stdinput` that is, your program will take as a command line argument the name of a file.[^1] If no argument is given, assume the file is `test.txt`.

For further reading, search Google, specifically for results from
StackOverflow, and feel free to ask me if you need help. On the file IO portion, I'm fine if you use an LLM[^2]. However, the actual assigned content (e.g. finding the transitive closure of a relation using Warshall's algorithm **must** be your own work, implementing the algorithms we learned.)

[^2]: Automate the boring stuff. I want to see that **you** understand the **math** portion. 




## But wait, how do I read a filename from the command line?

### In C++:

Instead of using

```cpp
    int main(void) {
    ...
    }
```

You\'ll write your program using the following template:

```cpp
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
```


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

If you\'re using standard java, the main static method will be:

``` java
class Closures {
...
    public static void main(String[] args) { 
       // do something with the file; note: the filename is args[0]. 
       ...
    } 
...
}
```

## Writing to *stdout*

All of the programs will output to *stdout*. I use this output data to
compare against correctly computed values. You can do this via a number
of mechanisms in your chosen Language. Here is one way in each of the
above listed languages:

-   In C++, it's `std::cout << "text to output"`
-   In Python, you can use `print("text to output")`
-   In Java, it's `system.out.println("text to output")`

I will be trimming out whitespace from your output, so you don't need to worry about that.

[^1]: This allows me to run multiple tests by calling `./student.o test1.txt` and then using test2.txt, etc...