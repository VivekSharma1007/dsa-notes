### Pascal Triangle: Print the given row

```java
class Solution {
    public int[] pascalTriangleII(int r) {
        int ans[] = new int[r];
        for(int i = 1; i <= r; i++) {
            int val = func(r - 1, i - 1);
            ans[i - 1] = val;
        }

        return ans;
    }

    public int func(int n, int r) {
        int res = 1;
        for(int i = 0; i < r; i++) {
            res = res * (n - i);
            res = res / (i + 1);
        }
        return res;
    }
}
```

Time Complexity: O(n^2)
Space Complexity: O(m) -- to return the answer