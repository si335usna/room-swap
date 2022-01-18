# SI 335 Project: Room Swap

## Overview

We have a list of Midshipmen along with their company numbers, listed
according to their current rooms in Bancroft Hall.

Unfortunately, the companies are currently spread out over all the
rooms. To fix that, your program needs to say which Mids should swap
rooms (in order) so that all the companies are together.

The swaps produced by your program **must** put all the Mids in the same
company together in the final resulting list. However, it doesn't matter
what order the companies are in, or what order the Mids are within each
company area.

The goal is to accomplish this goal with **the fewest number of swaps**.

## Cheating

Take a moment to review the
[relevant section from the course
policy](https://usna.edu/Users/cs/pfau/s22si335/resources/policy.php#collaboration).

**If you have any doubt of what is allowed, just ask!**

## Requirements

The input to your program will come in the standard input stream (piped
in). It will consist of *n* lines, and each line will have a company
number, a single space, and then a name.

(Note, the input comes from **standard input**; it is not a filename
given on the command line.)

You may assume that company numbers will always be between 1 and 100,
and names will always consist of letters (no spaces) and have length at
most 40. The number of names *n* will be at most 1 million.

Despite the bounds just given, you should think of your *target*/typical
input as having 30 companies and 4000 names. Other, larger, input sizes
will be tested but you should focus on good performance on this input size.

Your program must **run within 5 seconds on my computer**, which has the
same specs as the machines in the Linux labs of Hopper Hall. If it takes
longer than this, you might not get credit for that example.

Your program should write its output to the standard output stream.
Each line of the output should contain two names (with space in between),
indicating who should be swapped, in order.

**There will be many possible correct outputs** for the same input.
There is not just one right answer, but there are some answers that are
better than others!

## What to turn in

Submit to [submit.cs.usna.edu](https://submit.cs.usna.edu) under SI335
and assignment name `proj1`. Your submission should contain two files:

*   Your source code, all in one file called `rooms.cpp` or similar (see
    table below under Languages)

*   An extensive `README.txt` file that:

    +   Has your name
    +   Cites (specifically!) any references you used in accordance with
        the collaboration policy
    +   Explains clearly how your program works
    +   Briefly explains how you came up with your brilliant idea
    +   Gives an analysis in terms of *n* and *k* (number of companies)
        of the running time of your program. Use what we've learned in
        class like best-case, worst-case, big-Theta, etc, and try to be
        as precise as you can.
    +   Gives an analysis of the number of swaps produced by your
        program in terms of *n* and *k*. (Note, this can be less than
        your program's running time!)

## Check program

To help you out, I have included a program [`checker.cpp`](checker.cpp) that will check
the input and output for correctness and count how many swaps there
were.

To compile this program, just type

```bash
make checker
```

Then you give command-line arguments for the input and output files
(respectively) to check how you did. For example, included in this
repository is a small example input [`5x30.txt`](5x30.txt), and a sample
solution of swaps (like what your program should output) in
[`sol5x30.txt`](sol5x30.txt). So you can run

```bash
./checker 5x30.txt sol5x30.txt
```

to confirm that this output is correct and it uses 10 swaps.

Note, you can also leave the output file off and pipe output directly.
So for example, if your program is called `rooms`, you could test your
program's output on that input file by running

```bash
./rooms <5x30.txt | ./checker 5x30.txt
```

and cut out the middleman entirely! (In fact, this is how I will test
your submitted program.)

## Languages

Your program must be called `rooms`, and can be written in any
programming language as long as I can run it.
Here are the "standard" languages:

Language | Source code filename
-------- | --------------------
C        | `rooms.c`
C++      | `rooms.cpp`
Java     | `Rooms.java` (and your `main` must be in the `Rooms` class)
Python3  | `rooms.py`
Rust     | `rooms.rs`
Haskell  | `rooms.hs`

To use one of these languages, just put *all* of your source code into a
file with the given name and submit it.  **You must use the names above
and put all your source code in a single file**.

(Note, for Java, it *is* possible to put multiple `class`es in the same
`.java` file as long as only the `Rooms` class is `public`. Make sure
the `Rooms` class has your `main` method.)

If you want to use a different language than the ones listed, send me an
email.

## Example test files

A few files are included for your own testing. Of course, you can (and
should) make your own additional files for testing your own code!

*   [`5x30..txt`](5x30.txt) 30 names, 5 companies
*   [`sol5x30.txt`](sol5x30.txt) sample solution for `5x30.txt` (remember, there are
    many other correct swap orders as well!)
*   [`3x4000.txt`](3x4000.txt) 4000 names, 3 companies
*   [`30x4000.txt`](30x4000.txt) 4000 names, 30 companies ("target" case)
*   [`5x100close.txt`](5x100close.txt) 100 names, 5 companies, and
    "close" to a correct order - possible to solve with about 10 swaps.
*   [`30x4000close.txt`](30x4000close.txt) 4000 names, 30 companies, and
    "close" to a correct order - possible to solve with about 100 swaps.

## Downloading this repo

You can scroll up and download individual files, or you can just use
git to clone the entire repository. Many (most?) professional
programmers nowadays use git to collaborate, organize, and share code,
so it's worth your effort to learn to use it a little bit.

To download ("clone") this repository, run from a linux command-line:

```bash
git clone https://github.com/si335usna/room-swap.git
```

This will create a directory `room-swap` from wherever you ran that
command, with all of these files. You can `cd` into that directory and
get to work!

Later, if some updates get made to this starter code repository and you
want to copy them to your local copy, you can just run:

```bash
git commit -am "saving my code"
git pull -s recursive -X ours origin main
```

I *strongly encourage* you to save your work using GitHub (or BitBucket
or GitLab or any other git-hosting service). For example, if you create
a free github account with username `myself`, then create a repository
(click the big + sign) called `myrepo`, you can connect that to your
local version by running

```bash
git remote add mine https://github.com/myself/myrepo
git push -u mine main
```

**Note**: Make sure your repository is *private*; otherwise you are
sharing your solutions with the world and probably violating the course
policy.
