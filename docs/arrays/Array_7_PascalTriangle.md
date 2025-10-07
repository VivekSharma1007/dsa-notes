```java
class Solution {
    public int pascalTriangleI(int r, int c) {
        // to calculate the element at row and col
        // we do n = r-1, r = c - 1, nCr = n! / (r! * (n-r)!)
        return func(r - 1, c - 1);
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

Time Complexity: O(N)
Space Complexity: O(1)