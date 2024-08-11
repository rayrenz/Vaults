## Simplification Rule 1. Drop the Constants
For example a function runs two loops from 0 to n, we'd expect it to be written as O(2n) but this rule means we can just write it as O(n)

## O(n^2)
ex. loop with a loop inside

## Simplification Rule 2. Drop Non-dominants
ex. loop with loop inside + another loop of n
It would normally be written as O(n^2 + n) but at very large values for n, the n is non-dominant which should be dropped and we simplify it as O(n^2)

## O(1)
called the most efficient or optimal
ex. a function that adds x + y
ex. a function that adds x + x + x , it still is O (1) since we're not increasing number of operations

## O(log n)
Very efficient but not as optimal as O(1)
Below is the output of a binary search algorithm with inputs from `1` to `n` and data 
`[1,2,3,...,n]` where `n=8` 
Since we're halving n for every step, we know from its runtime that 3 is the most we need to cut the list in half to find a number.
2$^3$ = 8
log$_2$ 8 = 3
How many times do you have to divide 8 by 2 to get to 1 item? Answer is 3
```
0: finding 1 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 1 at [1, 2, 3, 4]
mid is 3 at pos 2
2: finding 1 at [1, 2]
mid is 2 at pos 1
3: finding 1 at [1]
Found 1 at 0 with 3 steps
=================
0: finding 2 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 2 at [1, 2, 3, 4]
mid is 3 at pos 2
2: finding 2 at [1, 2]
Found 2 at 1 with 2 steps
=================
0: finding 3 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 3 at [1, 2, 3, 4]
Found 3 at 2 with 1 steps
=================
0: finding 4 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 4 at [1, 2, 3, 4]
mid is 3 at pos 2
2: finding 4 at [4]
Found 4 at 0 with 2 steps
=================
0: finding 5 at [1, 2, 3, 4, 5, 6, 7, 8]
Found 5 at 4 with 0 steps
=================
0: finding 6 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 6 at [6, 7, 8]
mid is 7 at pos 1
2: finding 6 at [6]
Found 6 at 0 with 2 steps
=================
0: finding 7 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 7 at [6, 7, 8]
Found 7 at 1 with 1 steps
=================
0: finding 8 at [1, 2, 3, 4, 5, 6, 7, 8]
mid is 5 at pos 4
1: finding 8 at [6, 7, 8]
mid is 7 at pos 1
2: finding 8 at [8]
Found 8 at 0 with 2 steps
=================
runtimes: [3, 2, 1, 2, 0, 2, 1, 2]
```

## Multiple parameters
For example, a function has two params, a and b, and it loops through a then loops through b.
We could write this as O(a) + O(b) or simplify as O(a+b)