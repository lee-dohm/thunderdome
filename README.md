# Thunderdome

A test harness for comparing two algorithms against each other.

## What Is It For?

Thunderdome is for comparing two (or more) algorithms that are intended to do the same thing against each other. For example, let's say that you have two different algorithms for determining the type of a file. One examines the file extension. The other examines the contents of the file. How do you determine which is best? Thunderdome can help!

## How Does It Work?

Thunderdome works by taking the functions you give it, calling them and reporting the results. The functions you supply to Thunderdome are:

* `getAlgorithms` &mdash; Returns the list of functions under test
* `getScorer` &mdash; Returns the function to use to grade the output of the functions under test
* `nextTest` &mdash; Returns the test data to be used when calling the functions under test

Thunderdome then performs the following steps:

1. Call `getAlgorithms` to get the list of functions under test
1. Call `getScorer` to get the function to use to score the results
1. While `nextTest` does not return `undefined`
    1. Call each algorithm in turn with the test data
    1. Use the scorer function to score the output of the algorithm and record it
1. Report the results

## Copyright

Copyright &copy; 2015 by [Lee Dohm](http://www.lee-dohm.com). See [LICENSE](https://github.com/lee-dohm/thunderdome/blob/master/LICENSE.md) for details.
