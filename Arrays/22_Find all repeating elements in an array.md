# Find all repeating elements in an array

**Problem Statement:** Find all the repeating elements present in an array.

# Example: 

**Input:** Arr[] = [1,1,2,3,4,4,5,2]

**Output:**  1,2,4

**Explanation:** 1,2 and 4 are the elements which are occurring more than once.

---

# Optimal Approach

```
Store the elements in the hashmap with its frequency of occurrence.

Iterate through the hashmap. If occurrence is more than 1, return the element.
```
# Code:

```java
class Solution {
    // Function to find repeating elements in an array
    public static void findRepeatingElements(int[] arr) {
        Map<Integer, Integer> elementCount = new HashMap<>();
        
        // Count occurrences of each element
        for (int i : arr) {
            elementCount.put(i, elementCount.getOrDefault(i, 0) + 1);
        }
        
        System.out.print("The repeating elements are: ");
        // Print the elements that appear more than once
        for (Map.Entry<Integer, Integer> entry : elementCount.entrySet()) {
            if (entry.getValue() > 1) {
                System.out.print(entry.getKey() + " ");
            }
        }
    }

```

**Time Complexity:** `O(N)`, The entire array is traversed once to insert elements into the map.


**Space Complexity:** ` O(N)`, A map is used to store the frequency/count of each element in the array.
