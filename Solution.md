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
 
   ### nums = [2,7,11,15]
        
    class Solution {
    public int[] twoSum(int[] nums, int target) {
  
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
_________________________________________________________________________________________________________________________________________________________________________________


## 2. Add Two Numbers

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

 

Example 1:


### Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.


/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */

    
    class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode result= null, head=null;
        int count=0,val1,val2,top,carry=0;
        ListNode prev = null;
        ListNode next = null;
        
        while(l1 != null || l2 != null) {
          int sum = 0;
          if(l1 != null) {
            sum += l1.val;
            l1 = l1.next;
          }
          if(l2 != null) {
            sum += l2.val;
            l2 = l2.next;
          }
          sum += carry;
          int value  = sum%10;
          carry = sum/10;
          ListNode node = new ListNode(value);
          if(result != null) {
            result.next = node;
            result = result.next;
          } else {
            result = head = node;
          }
        }if(carry > 0) {
          result.next = new ListNode(carry);
        }
        
        //Si on veut inverser le node.
        while(head!=null){
            next=head.next;
            head.next=prev;
            prev=head;
            head=next;
        }
        head=prev;
        return head;
  }
        
}

_________________________________________________________________________________________________________________________________________________________________________________

