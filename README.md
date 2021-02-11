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
policy](https://usna.edu/Users/cs/roche/335/resources/policy.php#collaboration).

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
input as having 30 companies and 4000 names. If your program does great
on such inputs, that will be best.

Your program must **run within 5 seconds on my computer**, which has the
same specs as the machines in the Linux labs of Hopper Hall. If it takes
longer than this, you might not get credit for that example.

Your program should write its output to the standard output stream.
Each line of the output should contain two names (with space in between),
indicating who should be swapped, in order.

**There will be many possible correct outputs** for the same input.
There is not just one right answer, but there are some answers that are
better than others!

## Check program

To help you out, I have included a program `checker.cpp` that will check
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
