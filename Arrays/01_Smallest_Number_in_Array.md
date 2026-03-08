# Find the smallest element in an array
**Problem Statement:** Given an array, we have to find the smallest element in the array.
**Example 1:**
**Input:**
 arr[] = {2, 5, 1, 3, 0}  
**Output:**
 0  
**Explanation:**
  0 is the smallest element in the array.
  
# Brute Force Approach
```
Sort the array in ascending order.
Print the element at the 0th index, which corresponds to the smallest element in the array.
```
# Code:
```java
  public static int smallestElement(int[] arr) {
        // Sort the array in ascending order
        Arrays.sort(arr);

        // Return the first element (smallest element) after sorting
        return arr[0];
    }
```
**Time Complexity:** `O(N log N)` where N is the size of the array, as we are sorting the array.
**Space Complexity:**  `O(1)` as we are using a constant

# Optimal Approach
```
Create a variable called min and initialize it with the value of the first element in the array.
Use a for loop to iterate through the remaining elements in the array.
In each iteration, compare the current element with the min variable.
If the current element is less than the min value, update the min value with the current element's value.
After completing the loop, print the min variable, which will hold the smallest value in the array.
```
# code:
```java
 public static int SmallestElement(int[] arr, int n) {
        int min = arr[0];  // Initialize the minimum element with the first element

        // Iterate through the array to find the smallest element
        for (int i = 1; i < n; i++) {
            if (arr[i] < min) {  // If the current element is smaller than min, update min
                min = arr[i];
            }
        }

        return min;  // Return the smallest element found
    }
```
**Time Complexity:** `` O(N)`` where N is the size of the array, as we are iterating through the array once.

Space Complexity: `O(1)`, as we are using a constant


