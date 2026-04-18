```java
class Solution {
    public void moveZeroes(int[] nums) {
        int j = 0; // position to place non-zero

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                // swap
                int temp = nums[i];
                nums[i] = nums[j];
                nums[j] = temp;
                j++;
            }
        }
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(1)

```