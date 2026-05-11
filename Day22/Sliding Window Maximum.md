```java
class Solution {
    public int[] maxSlidingWindow(int[] nums, int k) {

        Deque<Integer> deque = new LinkedList<>();
        int[] result = new int[nums.length - k + 1];

        int index = 0;

        for (int i = 0; i < nums.length; i++) {

            // remove out of window
            while (!deque.isEmpty() && deque.peekFirst() <= i - k) {
                deque.pollFirst();
            }

            // remove smaller elements
            while (!deque.isEmpty() && nums[deque.peekLast()] < nums[i]) {
                deque.pollLast();
            }

            deque.offerLast(i);

            // store answer
            if (i >= k - 1) {
                result[index++] = nums[deque.peekFirst()];
            }
        }

        return result;
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(k)

```