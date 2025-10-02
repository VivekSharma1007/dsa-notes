### Move Zeroes to end

```java
class Solution {
    public void moveZeroes(int[] nums) {
        int zIdx = 0;
        while(zIdx < nums.length && nums[zIdx] != 0) {
            zIdx++;
        }
        int nzIdx = zIdx;
        while(nzIdx < nums.length && nums[nzIdx] == 0) {
            nzIdx++;
        }

        while(nzIdx < nums.length) {
            if(nums[nzIdx] != 0) {
                nums[zIdx] = nums[nzIdx];
                zIdx++;
                nzIdx++;
            } else {
                nzIdx++;
            }
        }
        while(zIdx < nums.length) {
            nums[zIdx] = 0;
            zIdx++;
        }
    }

    public void bruteForce(int nums[]) {
        // brute force 
        // store all non zero elements in one array and then 
        // copy them to the given array and make other elements as zero
        int noOfNonZero = 0;
        // O(N)
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] != 0) {
                noOfNonZero++;
            }
        }

        int arr[] = new int[noOfNonZero];
        noOfNonZero = 0;
        // O(N)
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] != 0) {
                arr[noOfNonZero] = nums[i];
                noOfNonZero++;
            }
        }

        // copy back to the given array
        // O(M)
        for(int i = 0; i < arr.length; i++) {
            nums[i] = arr[i];
        }
        // O(M)
        for(int i = arr.length; i < nums.length; i++) {
            nums[i] = 0;
        }
    }
}
```


#### Brute force
Time Complexity: O(N) + O(N) + O(M) + O(M) = O(3N)
Space Complexity: O(1)

#### Optimal Approach:
Time Complexity: O(N)
Space Complexity: O(1)