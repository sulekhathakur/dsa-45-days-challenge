```java
class Solution {
    public int maxSubarraySumCircular(int[] nums) {
        int totalSum = 0;
        
        int maxSum = nums[0];   // for normal Kadane (max subarray)
        int curMax = 0;
        
        int minSum = nums[0];   // for min subarray
        int curMin = 0;
        
        for (int num : nums) {
            // Kadane for max subarray
            curMax = Math.max(curMax + num, num);
            maxSum = Math.max(maxSum, curMax);
            
            // Kadane for min subarray
            curMin = Math.min(curMin + num, num);
            minSum = Math.min(minSum, curMin);
            
            totalSum += num;
        }
        
        // Edge case: all elements are negative
        if (maxSum < 0) {
            return maxSum;
        }
        
        // Return max of normal and circular case
        return Math.max(maxSum, totalSum - minSum);
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(1)

```