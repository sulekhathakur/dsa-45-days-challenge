```java
class Solution {
    public ListNode rotateRight(ListNode head, int k) {

        if (head == null || head.next == null || k == 0) {
            return head;
        }

        ListNode curr = head;
        int length = 1;

        while (curr.next != null) {
            curr = curr.next;
            length++;
        }

        curr.next = head; // make circular

        k = k % length;
        int steps = length - k;

        ListNode tail = curr;

        while (steps-- > 0) {
            tail = tail.next;
        }

        head = tail.next;
        tail.next = null;

        return head;
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(1)

```