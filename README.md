# leetcode 283 Move Zeroes

## Approach: Count the 0's and add back at the end
```C#
public static void MoveZeroes(int[] nums)
{
    int zeroCounter = 0;
    int arrPos = 0;
    for (int i = 0; i < nums.Length; i++)
    {
        if (nums[i] == 0)
        {
            while (i < nums.Length && nums[i] == 0)
            {
                zeroCounter++;
                i++;
            }
        }
        if (i < nums.Length)
        {
            nums[arrPos] = nums[i];
            arrPos++;
        }
    }
    while (arrPos < nums.Length)
    {
        nums[arrPos++] = 0;
    }
```
#### Complexity Analysis
* Time Complexity: O(n)
* Space Complexity: O(1)

## Approach: Similar approach and simple
```C#
public static void MoveZeroes(int[] nums)
{
    int pos = 0;
    for (int i = 0; i < nums.Length; i++)
    {
        if (nums[i] != 0)
            nums[pos++] = nums[i];
    }
    for (int i = pos; i < nums.Length; i++)
    {
        nums[i] = 0;
    }
}
```
#### Complexity Analysis
* Time Complexity: O(n)
* Space Complexity: O(1)
