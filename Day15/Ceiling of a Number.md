```java
class Solution {
    public int ceiling(int[] nums, int target) {
        int left = 0, right = nums.length - 1;

        if (target > nums[right]) return -1; // no ceiling

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] == target) return nums[mid];
            else if (nums[mid] < target) left = mid + 1;
            else right = mid - 1;
        }
        return nums[left]; // ceiling
    }
}
```
---

```
Time  Complexity: O(log n)
Space Complexity:  O(1)

```