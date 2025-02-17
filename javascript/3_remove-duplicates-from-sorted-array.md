# [Leetcode 26: Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## Two pointers 

This approach efficiently reduces duplicates in place with minimal space overhead, leveraging the fact that the input array is already sorted

**Code**:

```javascript

var removeDuplicates = function(nums) {
    let i = 0;

    for(let j =0; j < nums.length;j++) {
        if(nums[i] !== nums[j]){
            i++;
            nums[i] = nums[j]
        }
    }
    return i+1;
};

```
- **Time Complexity**: O(n), We loop over the nums Once.
- **Space Complexity**: O(1), using only one constant.