#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I


```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```
O(n) because `n*n + n*n` ... n times, equals `n*n*n`, which is our while condition stop


```
b)  sum = 0
    for i in range(n):
      j = 1
      while j < n:
        j *= 2
        sum += 1
```
O(nlog(n)), because 1) we're looping through n times, and within that loop, we're looping through log_2(n) times, as we're multiplying j by 2 each time, which reaches our while condition stop in log time.

```
c)  def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```
O(n) I believe, because we're just building a chain of calls to the function bunnyEars, not a tree of them, as it only executes once per execution instead of twice per execution as in fibonacci. 

## Exercise II

```Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.```

This is essentially a binary search problem, as we are trying to find a value that lies within a min and max, same as binary search. So it would resolve in O(log(n)) time, as we're halving the remaining search area at each iteration. The algorithm would be roughly:

1. define our lower and upper boundaries, 1 and n, respectively
2. find the midway point between them, (1+n)//2 (rounding down since we can't have a decimal floor)
3. test if egg breaks on the midway point floor. 
    if it does, we we set our upper boundary to be our midway point
    if it doesn't, we set our lower boundary to be our midway point, plus 1.
keep repeating this process by doing steps 2-3 until we converge on floor f. 
ie, if the egg breaks and it was our lower boundary with only one other floor to check within our boundary, it means that that floor is `f`, or if the egg doesn't break and it was our lower boundary with only one other floor to check within our boundary, that floor above us is `f`.