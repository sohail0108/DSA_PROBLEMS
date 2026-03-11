# Find all Symmetric Pairs in the array of pairs

**Problem Statement:** Given an array of pairs, find all the symmetric pairs in the array.

# Example

**Input:**
 (1,2),(2,1),(3,4),(4,5),(5,4)
 
**Output:**
 (2,1) (5,4)
 
**Explanation:**
 Since (1,2) and (2,1) are symmetric pairs and (4,5) and (5,4) are symmetric pairs.

 ---

# Optimal Approach:

```
Intuition: We will store the pairs in a hash map and then check if the symmetric pair exists or not.

Store pairs in the hashmap.

Let “first” be the first element of the pair and “second” be the second element of the pair.

While iterating through the pairs we will check if {second,first} exists by using map.

If {second,first} exists then print the pair,else store it in the map.

```

# Code:

```java
import java.util.*;

class Solution {
    // Function to find symmetric pairs in an array
    public void findSymmetricPairs(int[][] arr) {
        Map<Integer, Integer> mp = new HashMap<>();  // Map to store first element and its pair
        System.out.println("The Symmetric Pairs are:");

        // Loop through the array to find symmetric pairs
        for (int i = 0; i < arr.length; i++) {
            int first = arr[i][0];
            int second = arr[i][1];

            // Check if {second, first} existed previously
            if (mp.containsKey(second) && mp.get(second) == first) {
                System.out.print("(" + first + " " + second + ") ");
            } else {
                // Store {first, second} pair in the map
                mp.put(first, second);
            }
        }
    }
}
```
**Time Complexity:** `O(N)`, Each element is processed once while inserting and checking in the hashmap.


**Space Complexity:** ` O(N)`, A hashmap is used to store previously seen elements for quick lookup.
