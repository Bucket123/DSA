# DSA
<h4>Find missing number and repeated number in an 2D Matrix</h4>

class Solution {
    public int[] findMissingAndRepeatedValues(int[][] grid) {
        int n = grid.length;
        int num = n*n;
        int[] ans = new int[2];
        int totalSum = (num * (num+1)) / 2;
        int actualSum = 0;  
        HashMap<Integer, Integer> map = new HashMap<>();
        for(int i=0; i<n; i++)
        {
            for(int j=0; j<n; j++)
            {
                actualSum += grid[i][j];
                map.put(grid[i][j], map.getOrDefault(grid[i][j],0)+1);

                if(map.get(grid[i][j])==2)
                {
                    ans[0] = grid[i][j];
                }
            }
        }

        ans[1] = totalSum - (actualSum - ans[0]);
        return ans;
    }
}
