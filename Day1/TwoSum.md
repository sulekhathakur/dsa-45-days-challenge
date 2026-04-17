```java
import java.util.HashMap;

class Solution {
    public int[] twoSum(int[] nums, int target) {

        // Step 1: Create a map to store number → index
        HashMap<Integer, Integer> map = new HashMap<>();

        // Step 2: Traverse array
        for (int i = 0; i < nums.length; i++) {

            // Step 3: Find the required number to reach target
            int complement = target - nums[i];

            // Step 4: Check if complement already exists
            if (map.containsKey(complement)) {

                // If yes → we found the pair
                return new int[]{map.get(complement), i};
            }

            // Step 5: Store current number with its index
            map.put(nums[i], i);
        }

        return new int[]{};
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(n)
```