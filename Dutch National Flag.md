#threePointer
Related to quicksort.
Made by Edgar Dijsktra.
Partitioning three elements red, white, blue.

- Start building red from top to bottom
- Leave white in between
- Build blue from bottom to top

```kotlin
fun dnf(nums: IntArray): IntArray {
	var red = 0
	var white = 0
	var blue = nums.lastIndex

	while (white <= blue) {
		if (nums[white] == 0) {
				// found red
				// send red in front by swapping
			val temp = nums[white]
			nums[white] = nums[red]
			nums[red] = temp
			white++
			red++
		}
		else if (nums[white] == 1) {
			// found white
			white++
		}
		else {
			// found blue
			// send blue back by swapping
			val temp = nums[blue]
			nums[blue] = nums[white]
			nums[white] = temp
			// not increamented white because swapped element could be red
			blue--	
		}
	}
}
```