https://cses.fi/problemset/task/2183/

All number are positive.
Smallest answer could be 1.

First sort the array

We start with `ans = 1`
And according to condition add `nums[i]` to `ans`, so prefix sum in formed.
Why we add `nums[i]`? Because 

There are two possibilities:
1. if `ans >= nums[i]` 
2. if `nums[i] > ans` then smallest value is ans, because there is gap between `ans` and `nums[i]`. Smallest value is `ans` and not `ans + 1` because we had started from 1.