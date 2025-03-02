# DSA
<h4>Find missing number and repeated number in an 2D Matrix</h4>
-----------------------------------------------
<br>
class Solution {<br>
    public int[] findMissingAndRepeatedValues(int[][] grid) {<br>
        int n = grid.length;<br>
        int num = n*n;<br>
        int[] ans = new int[2];<br>
        int totalSum = (num * (num+1)) / 2;<br>
        int actualSum = 0;  <br>
        HashMap<Integer, Integer> map = new HashMap<>();<br>
        for(int i=0; i<n; i++)<br>
        {
            for(int j=0; j<n; j++)<br>
            {
                actualSum += grid[i][j];<br>
                map.put(grid[i][j], map.getOrDefault(grid[i][j],0)+1);<br>

                if(map.get(grid[i][j])==2)<br>
                {
                    ans[0] = grid[i][j];<br>
                }
            }
        }

        ans[1] = totalSum - (actualSum - ans[0]);<br>
        return ans;<br>
    }<br>
}<br>
---------------------------------<br>----------
