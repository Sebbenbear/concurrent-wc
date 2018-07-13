# concurrent-wc

This project is for comparing async and concurrency tools in different
languages by implementing a simple `wc -l`-style utility.

## spec

The `wc` utility should do the following:

1. Display the number of lines for each regular file in the directory.
2. Display the cumulative number of lines of all files in the directory.
3. Optionally take a single command-line argument specifying a different
   directory.
4. Sort the files in terms of number of lines, in descending order.

e.g.

```
$ ./go/wc tmp
        11 tmp/big.txt
         1 tmp/small.txt
        12 [TOTAL]
```

## implementing

The suggested implementation involves "fanning out" asynchronous tasks to read
through each file in the directory and count the lines concurrently.  The tasks
will need to be synchronized at the end in order to compile the results and sort
them for display.

As of commit [c89a50e](https://github.com/dan-f/concurrent-wc/commit/c89a50e20954d0ba32973a39ad660cf31c1b2bba), the go implementation is the reference implementation.

## contributors

Thanks to the following folks!

* Daniel Friedman <dfriedman58s@gmail.com>
* Nicolas Hahn <nicolas@stonespring.org>
* Max Bittman <maxb.personal@gmail.com>
