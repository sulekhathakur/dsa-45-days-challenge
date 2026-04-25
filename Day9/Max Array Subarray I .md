```java
class Solution {
    public double findMaxAverage(int[] nums, int k) {
        int n = nums.length;

        // Step 1: First window sum
        int windowSum = 0;
        for (int i = 0; i < k; i++) {
            windowSum += nums[i];
        }

        int maxSum = windowSum;

        // Step 2: Slide window
        for (int i = k; i < n; i++) {
            windowSum += nums[i];      // add next
            windowSum -= nums[i - k];  // remove left

            maxSum = Math.max(maxSum, windowSum);
        }

        // Step 3: Return average
        return (double) maxSum / k;
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(1)

```