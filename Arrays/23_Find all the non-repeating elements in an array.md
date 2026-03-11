# Find all the non-repeating elements in an array

***Problem Statement:*** Find all the non-repeating elements for a given array. Outputs can be in any order.

# Example

**Input:** Nums = [1,2,-1,1,3,1]

**Output:** 2,-1,3

**Explanation:**

1 is the only element in the given array which occurs thrice in the array. -1,2,3 occurs only once and hence, these are non-repeating elements of the given array.

---

# Optimal Approach

```
Declare a hashmap for storing elements as the key and their number of occurrences as value..

Iterate through the array and store elements and their occurrences in the map.

Print elements whose occurrences were equals to 1.
```

---

# Code:
```java

import java.util.*;

class Solution {
    // Function to find non-repeating elements in an array
    public void findNonRepeatingElement(int[] nums) {
        Map<Integer, Integer> hashMap = new HashMap<>();  // HashMap to store element counts

        // Count occurrences of each element
        for (int num : nums) {
            hashMap.put(num, hashMap.getOrDefault(num, 0) + 1);
        }

        // Print non-repeating elements (count == 1)
        System.out.print("Non-repeating numbers are: ");
        for (Map.Entry<Integer, Integer> entry : hashMap.entrySet()) {
            if (entry.getValue() == 1) {
                System.out.print(entry.getKey() + " ");
            }
        }
    }
}
```


**Time Complexity:** `O(N)`, The array is traversed only once to process each element.


**Space Complexity:** `O(N)`, A map (or hashmap) is used to store the elements, requiring linear space.

