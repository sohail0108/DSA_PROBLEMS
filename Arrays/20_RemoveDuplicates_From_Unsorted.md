# Remove Duplicates From an Unsorted Array

**Problem Statement:** Given an unsorted array, remove duplicates from the array.

# Example
**Input:** arr[]={2,3,1,9,3,1,3,9}

**Output:** {2,3,1,9}

**Explanation:** Removed all the duplicate elements.

# Approach:
```
To check which all elements have already occured, we can simply start from first index again and for each element check whether it is equal to current element or not.

1.Initialize an answer array and iterate over the original array.
2.For every element, start iterating from first index till current index and check whether it has occured before or not
3.If the element is present before, skip that element now. If it is not present, add it to our answer array.
4.Return the answer array once the original array is traversed completely.
```
---

# Code:
```java
class Solution {
    // Function to remove duplicates from an array
    public ArrayList<Integer> removeDuplicates(int[] arr) {
        // Result list to store unique elements
        ArrayList<Integer> result = new ArrayList<>();

        // Traverse each element in arr
        for (int i = 0; i < arr.length; i++) {
            // Flag to check if element already exists in result
            boolean found = false;

            // Check for duplicates in result
            for (int j = 0; j < result.size(); j++) {
                if (arr[i] == result.get(j)) {
                    found = true;
                    break;
                }
            }

            // If not found, add to result
            if (!found) {
                result.add(arr[i]);
            }
        }

        // Return the result list
        return result;
    }
}
```
**Time Complexity:** O(N^2), We traverse the entire array again for every element in the array.

**Space Complexity:** O(N), additional space used to store resultant array.

---

# Optimal Approach
```
Instead of traversing the entire array again for every element, we can simply store the element appearing in a map for faster look up. This helps in improving the time complexity of our solution by making it faster to check whether a element is duplicate or not.

1.Initialize an hash map and iterate over the original array.
2.Initialize an answer string. For every element, check if it is present in the map or not.
3.If the element is present, skip that element. If it is not present, add it to our answer array and mark it as true in map.
4.Return the answer array once the original array is traversed completely.

```
# Code:
```java
class Solution {
    // Function to remove duplicates using HashMap 
    public List<Integer> removeDuplicates(int[] arr) {
        HashMap<Integer, Boolean> seen = new HashMap<>();
        List<Integer> result = new ArrayList<>();

        // Traverse each element
        for (int val : arr) {
            // If not already seen, add to result
            if (!seen.containsKey(val)) {
                result.add(val);
                seen.put(val, true);
            }
        }

        return result;
    }
}
```
**Time Complexity:** ``O(N)``, We traverse the entire original array only once.

**Space Complexity:** ``O(N)``, additional space used to store resultant array and occurence of elements in map.
