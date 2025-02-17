# [Leetcode 169: Majority Element](https://leetcode.com/problems/majority-element/)

## Approaches

1. [Brute Force Approach](#brute-force-approach)
2. [Optimal In-place Approach](#optimal-in-place-approach)

### Brute Force Approach

#### Hash Map Approach

Use a HashMap to count the occurrences of each element in the array. The element with a count greater than n/2 is the majority element.

**Code**:

```javascript
function majorityElement(nums) {
  let countMap = new Map();

  for (let num of nums) {
    countMap.set(num, (countMap.get(num) || 0) + 1);

    if (countMap.get(num) > Math.floor(nums.length / 2)) {
      return num;
    }
  }
}
```

- **Time Complexity**: O(n), We loop over the nums Once.
- **Space Complexity**: O(n), we store counts upto n/2 + 1 elm.

---

#### Sorting Approach

Sort the array, the majority element (which appears more than n/2 times) must be present in the middle of the array.

**Code**:

```javascript
function majorityElement(nums) {
  nums.sort((a, b) => a - b); // SORT

  return nums[Math.floor(nums.length / 2)];
}
```
- **Time Complexity**: O(n log n), Since we are using sort.
- **Space Complexity**: O(1)



### Optimal In-place Approach

#### Boyer-Moore Voting Algorithm

This optimal approach involves counting a candidate element against others. If a number is the majority, it will be the last element standing after cancellations.

Steps:

1. Initialize count as 0 and candidate as undefined at the start.
2. Loop through the array:
    If count is 0, set the current number as candidate and increment count.

    If the current number is the same as candidate, increment count.

    Otherwise, decrement count.
3. Return candidate, the majority element.

**Code**:

```javascript
function majorityElement(nums) {
    let count = 0;
    let candidate = undefined;

    for(let num of nums) {
        if( count === 0) {
            candidate = num;
        }

        count += (candidate === num) ? 1 : -1;
    }
    return candidate;
    
}
```