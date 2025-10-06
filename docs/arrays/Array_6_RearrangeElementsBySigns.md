### Rearrange Elements by Signs

```java
class Solution {
    public int[] rearrangeArray(int[] nums) {
        // Better Solution
        int pIdx = 0;
        int nIdx = 1;
        int ans[] = new int[nums.length];
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] >= 0) {
                ans[pIdx] = nums[i];
                pIdx = pIdx + 2;
            } else {
                ans[nIdx] = nums[i];
                nIdx = nIdx + 2;
            }
        }

        return ans;
    }
}

// Brute Force:
// create 2 list one for storing postive numbers and another for
// storing negative numbers
// iterate over them and take numbers and create final ans
```

#### Brute Force:
Time Complexity: O(N) + O(N) + O(N) = O(3N)
Space Complexity: O(N) - for storing positive and negative values + O(N) -- fir storing answer


#### Better Solution:
Time Complexity: O(N)
Space Complexity: O(N) -- for storing answer