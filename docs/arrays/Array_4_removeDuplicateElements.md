### Remove Duplicate elements and return the non duplicate elements number

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        // brute force
        // store elements in hashset(linked or tree set)
        // copy all the elements in Array
        // and return the size of set 

        // better approach
        int i = 0;
        int j = 0;
        if(nums.length == 1) {
            return 1;
        }

        while(j < nums.length) {
            if(nums[j] == nums[i]) {
                j++;
            } else {
                i++;
                nums[i] = nums[j];
                j++;
            }
        }
        return i+1;
    }
}
```

#### Brute Force: 
Time-Complexity: O(N)
Space-Complexity: O(N) -- in worst case

#### Optimal Solution:
Time-Complexity: O(N)
Space-Complexity: O(1)