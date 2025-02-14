# [Leetcode 283: Move Zeroes](https://leetcode.com/problems/move-zeroes/)

## Approaches
1. [Brute Force Approach](#brute-force-approach)
2. [Optimal In-place Approach](#optimal-in-place-approach)

### Brute Force Approach

Create a new array and add all non-zero elements from the original array. Then, calculate the difference in length between the original and new arrays to determine the number of zeros. Finally, use a loop to add the required number of zeros at the end.

**Code**:
```javascript
    var moveZeroes = function (nums) {
        let result = [];
    
        for (let i = 0; i < nums.length; i++) {
            if (nums[i] !== 0) {
                result.push(nums[i])
            }
        }
        var noOfZeros = nums.length - result.length;
    
        for (let i = 0; i < zeroCount; i++) {
            result.push(0);
        }

        // Update the org Nums  - Copy
        for(let i = 0; i < nums.length; i++) {
            nums[i] = result[i]
        }

  };
```
- **Time Complexity**: O(n), where n is the length of the array, and we traverse the array 3 times.
- **Space Complexity**: O(n), because we used an extra array of the same length.


### Optimal In-place Approach

Use Two Pointers approach - [Same Direction (Slow & Fast)](Patterns/1_Two_Pointers.md) 

The main idea is to **shift all non-zero elements to the left** while keeping track of the last zero's position.

1) Use a pointer (**lastZeroAt**) to store the position of the last zero.
2) Loop through the array:
    * If the element is non-zero, swap it with the element at lastZeroAt.
    * Increase **lastZeroAt** to track the next zero position.
    * This ensures that all non-zero elements move to the left, and zeros shift to the right efficiently.

**Code**:
```javascript
    var moveZeroes = function (nums) {
      let lastZeroAt = 0;
      for (let i = 0; i < nums.length; i++) {
          if (nums[i] !== 0) {
              [nums[lastZeroAt], nums[i]] = [nums[i], nums[lastZeroAt]]
              lastZeroAt++;
          }
      }

  };
```
- **Time Complexity**: O(n), where n is the length of the array, Since we are iterate through arr once.
- **Space Complexity**: O(1), because we are performing operations in place without utilizing extra space.
