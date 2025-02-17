# Two Pointers Technique 

## Why ?
- Powerful technique that **improves efficiency**, often reducing **O(N²) problems to O(N)**.
- Useful in **array-based problems**, **linked lists**, **searching**, and **sliding window techniques**.

## Types of Two Pointers
1) **Opposite Direction (Start & End)** :

   Used for problems that require checking conditions from both ends of an array.

    **Example**: Check if a string is a **palindrome**

3) **Same Direction (Slow & Fast)** :
  
     Used for problems where one pointer moves faster than the other, such as removing duplicates, finding cycle in a linked list, and merging sorted arrays.
   
     **Example**: Remove duplicates from a sorted array

5) **Two Pointers for Subarrays (Sliding Window)** :

    Used for finding subarrays with a sum or checking conditions within a window.

      **Example**: Find the longest substring without repeating characters

6) **Trigger Based Pointers** :
   
    In this approach, we first move one pointer until it reaches a specific condition. Once it does, we start moving a second pointer to gather more details based on what the first pointer found.
    * Helps when we need to process elements in different stages.
      
      **Example**:
      Finding the 4th element from the end of a linked list:
      1) Move the first pointer 4 steps ahead.
      2) Then, start moving a second pointer from the beginning at the same pace.
      3) When the first pointer reaches the end, the second pointer will be at the 4th element from the end.

## When to use it ? 

1) Searching pairs in sorted arrays (e.g., finding a pair that sums to a target).
2) Reversing an array or linked list.
3) Removing duplicates from a sorted array.
4) Merging two sorted arrays or lists.
5) Finding subarrays with a certain property.
6) Solving problems related to palindromes, sliding windows, and partitioning arrays.

## Leetcode Examples -
https://leetcode.com/problems/move-zeroes/
https://leetcode.com/problems/remove-duplicates-from-sorted-array/
