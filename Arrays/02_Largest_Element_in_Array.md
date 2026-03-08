# Find the Largest element in an array
**Problem Statement:** Given an array, we have to find the largest element in the array.

# Example 1:
# Input:
 arr[] = {2, 5, 1, 3, 0}  
# Output:
 5  
# Explanation:
  
5 is the largest element in the array.

# Brute Force Approach
```
Sort the array in ascending order.

Print the element at the (size of the array - 1)th index, which corresponds to the largest element in the array.

```
# Code:
```java
 public static int sortArr(int[] arr) {
        // Sort the array in ascending order
        Arrays.sort(arr);
        
        // Return the last element (largest element) after sorting
        return arr[arr.length - 1];
    }
```
**Time Complexity:** `O(N log N)` where N is the size of the array, as we are sorting the array.
**Space Complexity:**  `O(1)` as we are using a constant

# Optimal Approach
```
Create a variable called max and initialize it with the value of the first element in the array.
Use a for loop to iterate through the rest of the elements in the array.
In each iteration, compare the current element with the max variable.
If the current element is greater than the max value, update the max value with the current element's value.
After completing the loop, print the max variable, which will hold the largest value in the array.
```
# code:
```java
   public static int findLargestElement(int[] arr, int n) {
        int max = arr[0];  // Initialize max with the first element in the array

        // Iterate through the array to find the maximum element
        for (int i = 1; i < n; i++) {
            if (arr[i] > max) {  // If the current element is greater than max, update max
                max = arr[i];
            }
        }

        return max;  // Return the largest element found
    }
```
**Time Complexity:** `` O(N)`` where N is the size of the array, as we are iterating through the array once.

Space Complexity: `O(1)`, as we are using a constant
