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


