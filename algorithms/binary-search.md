C# implementation
```cs
public class Solution
 {
    public int Search(int[] nums, int target)
    {
        short k = 0;
        for (short i = (short) nums.Length / 2; i >=1; i /=2 )
        {
            while(k+i < nums.Length && nums[k+i] <= target)
            {
                k+=i;
            }
        }
        
        return nums[k] == target ? k : -1;
    }
}
```
