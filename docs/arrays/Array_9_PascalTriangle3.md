### Pascal Triangle 3

```java
class Solution {
    public List<List<Integer>> pascalTriangleIII(int n) {
        List<List<Integer>> ans = new ArrayList<>();
        for(int i = 1; i <= n; i++) {
            List<Integer> list = func(i);
            ans.add(new ArrayList<>(list));
        }
        return ans;        
    }

    public List<Integer> func(int row) {
        List<Integer> list = new ArrayList<>();
        list.add(1);
        long res = 1;
        for(int col = 1; col < row; col++) {
            res = res * (row - col);
            res = res / col;
            list.add((int)res);
        }
        return list;
    }
}
```

Time Complexity: O(n^2)
Space Complexity: Storing the answer only