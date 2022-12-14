Question Name : Two Sum

Level : Easy

The question : 

    Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
    You may assume that each input would have exactly one solution, and you may not use the same element twice.
    You can return the answer in any order.

  Example:

    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
    
What Solution I Give:
1. Fix one number of two.
2. Get another number which the addition of them is equal to TARGET.
3. Find this another number in List. If the same value number exits in the list, Get its index.
4. Set two indices in new list answer.
5. If can not find, return null. Else return answer.

What I Learned From This Question:
1. return new int[] { i, j };

    There is no need to new a list anwser for setting the indices. Directly set the indices in the list when do return.
 
2. A hash table.
    
    A ash table is the best way to maintain a mapping of each element in the array to its index.
    ```
    Map<Integer, Integer> map = new HashMap<>();
    map.put(nums[i], i)
    map.containsKey(complement) && map.get(complement) != i)
    ```

New words:

    iterating
    collision
    degenerate 
    constant time
    amortized 
    
 Example Solution:
 
 ```
 class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer,Integer> map = new HashMap<>();
        for (int i=0;i<nums.length;i ++)
        {
            map.put(nums[i],i);
            int complement = target - nums[i];
            if (map.containsKey(complement) && map.get(complement)!= i)
            {
                return new int [] {map.get(complement) , i};
            }
        }
        return null;
    }
}
```
