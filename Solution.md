# LeetCode
Solution

## 1. Two Sum
 
Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 
 
 
 Solution :
 // nums = [2,7,11,15]
 
 class Solution {
    public int[] twoSum(int[] nums, int target) {
        
        
        ArrayList<Integer> s;

        for(int i=0; i<nums.length; i++){
            for(int k=0; k<nums.length; k++){
                if(i!=k ){
                    if(nums[i] + nums[k] == target){
                        return new int[] { i, k };
                    }
                }
                 
            }
        }
        
        return new int[] {};
        
    }
}
