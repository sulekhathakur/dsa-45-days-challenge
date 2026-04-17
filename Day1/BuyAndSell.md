```java
class Solution {
    public int maxProfit(int[] prices) {

        // Step 1: Assume the minimum price is very large initially
        // (so any real price will be smaller than this)
        int minPrice = Integer.MAX_VALUE;

        // Step 2: Initially, we have made no profit
        int maxProfit = 0;

        // Step 3: Traverse through each day's price
        for (int price : prices) {

            // Case 1: If current price is lower than the minimum price seen so far
            // → This is a better day to BUY the stock
            if (price < minPrice) {
                minPrice = price;  // update minimum price
            }

            // Case 2: Otherwise, try selling today
            else {
                // Profit = selling price - buying price (minPrice)
                int profit = price - minPrice;

                // Update max profit if this profit is better
                if (profit > maxProfit) {
                    maxProfit = profit;
                }
            }
        }

        // Step 4: Return the best profit we found
        // If no profit was possible, it will return 0
        return maxProfit;
    }
}
```
---

```
Time  Complexity: O(n)
Space Complexity:  O(1)

```