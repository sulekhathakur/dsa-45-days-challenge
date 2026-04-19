```java
class Solution {
    public int subarraySum(int[] nums, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();
        
        // Important: handles case when subarray starts from index 0
        map.put(0, 1);
        
        int sum = 0;
        int count = 0;
        
        for (int num : nums) {
            sum += num;
            
            // Check if there exists a prefix sum such that:
            // currentSum - previousSum = k
            if (map.containsKey(sum - k)) {
                count += map.get(sum - k);
            }
            
            // Store current prefix sum
            map.put(sum, map.getOrDefault(sum, 0) + 1);
        }
        
        return count;
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(n)

```