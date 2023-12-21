#queue
#monotonicQueue
#twoPointers

For each subarray of size k, find its maximum element.
Monotonic decreasing queue can be used to do this in $O(n)$ time.
When inserting new element we compare it with last element to form decreasing order $nums[dq.peekLast()] < nums[r]$.

So largest element is always at first position.

To remove element which is no longer in window we check $dq.peekLast() < l$.

A monotonic decreasing queue can be used because when a new element is introduced then if will not affect answer if it is smaller then largest element, so it can be queued from end. But if new element is larger then it can affect current or upcoming windows.

While maintaining monotonicity we can remove elements because element greater then them has come so they will not have effect on window maximum now.  

```java
public int[] maximumSlidingWindow(int[] nums, int k) {
	int n = nums.length;
	int[] ans = new int[n - k + 1];
	Dequeue<Integer> dq = new LinkedList<>();
	int l = 0;

	for (int r = 0; r <= n; r++) {
		// maintaing monotonic queue
		while (!dq.isEmpty() && nums[dq.peekLast()] < nums[r]) {
			dq.pollLast();
		}

		// remove element no longer in window
		if (!dq.isEmpty() && dq.peekFirst() < l) {
			dq.pollFirst();
		}

		dq.offer(r);

		if (r >= k - 1) {
			ans[l++] = nums[dp.peekFirst()];
		}
	}

	return ans;
}
```