### Leaders in an array

```java
class Solution {
    public List<Integer> leaders(int[] nums) {
        // Better way
        List<Integer> ans = new ArrayList<>();
        ans.add(nums[nums.length - 1]);

        for(int i = nums.length - 2; i >= 0; i--) {
            if(nums[i] > nums[i + 1]) {
                ans.add(nums[i]);
            } else {
                nums[i] = nums[i + 1];
            }
        }
        ans.sort(Collections.reverseOrder());
        return ans;
    }
}

// brute force
// start from the very first element and iterate over from the
// next element and see if any other item in array is greater than 
// the current element, if yes its not leader, if no it is a leader

```

#### Brute Force: 
Time Complexity: O(N*2)
Space Complexity: O(M) -- space required for storing answer

#### Optimal Approach:
Time Complexity: O(N) 
Space Complexity: O(M) -- space required for storing answer