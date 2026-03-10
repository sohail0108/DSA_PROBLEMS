# Remove Duplicates in-place from Sorted Array

***Problem Statement:*** Given an integer array sorted in non-decreasing order, remove the duplicates in place such that each unique element appears only once.
The relative order of the elements should be kept the same.

If there are k elements after removing the duplicates, then the first k elements of the array should hold the final result. It does not matter what you leave beyond the first k elements.

# Example:

**Input:** arr[]=[1,1,2,2,2,3,3]

**Output:** [1,2,3,_,_,_,_]

**Explanation:** Total number of unique elements are 3, i.e[1,2,3] and Therefore return 3 after assigning [1,2,3] in the beginning of the array.

---

# Brute Force Approach

**Approach:**
```
Since we need to store only unique elements, we can use the set data structure. We can insert all the elements of the array in the set irrespective of their frequency as set only allows one occurence of each element.

1.Declare a set and insert all the elements of the array into the set.
2.The number of unique elements in array is equal to size of the set.
3.Traverse the set and fill the first k indices with elements in set.
```

# Code:
```java
import java.util.HashSet;

// Solution class containing removeDuplicates method
class Solution {
    // Removes duplicates using HashSet and returns count of unique elements
    public int removeDuplicates(int[] nums) {
        // HashSet to store unique elements we have seen
        HashSet<Integer> seen = new HashSet<>();

        // Position to overwrite next unique element
        int index = 0;

        // Loop over each number in nums
        for (int num : nums) {
            // If num is not in the set, it is unique
            if (!seen.contains(num)) {
                // Add num to the set
                seen.add(num);

                // Write num at current index position
                nums[index] = num;

                // Move index forward
                index++;
            }
        }
        // Return number of unique elements
        return index;
    }
}

```

**Time Complexity:** ``O(N)``, We traverse the entire array and insert elements into set.


**Space Complexity:** `` O(N)``, additional space used to store elements in set.

---
# Optimal Approach:
```
Instead of using a set to store the unique elements, we can implement a two pointer strategy to optimize the space. Since the array is sorted, we know that all the duplicate values will be adjacent to each other.

1.Begin at the first position, which will always be part of the final unique list.
2.Move through the list one item at a time, comparing the current item with the most recently kept unique item.
3.If the current item is the same as the last kept one, skip it because it’s a duplicate.
4.If it’s different, place it right after the last kept unique item to keep all unique values grouped at the front.
5.Continue until every element in the list has been checked.

The first part of the list now contains all the unique values in their original order, and the rest can be ignored.
```

# Code :
```java

class Solution {
    // Function to remove duplicates from sorted array in-place
    public int removeDuplicates(int[] nums) {
        // If array is empty, return 0
        if (nums.length == 0) return 0;

        // Pointer for last unique element
        int i = 0;

        // Start from second element
        for (int j = 1; j < nums.length; j++) {
            // If new unique element is found
            if (nums[j] != nums[i]) {
                // Move unique position forward
                i++;
                // Place new unique element
                nums[i] = nums[j];
            }
        }

        // i is last index of unique element, count = i + 1
        return i + 1;
    }
}

```
**Time Complexity:** ``O(N)``, We traverse the entire original array only once.

**Space Complexity:** `` O(1)``, constant additional space is used to check unique ele
