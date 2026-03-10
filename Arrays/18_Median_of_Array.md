# Find Median of the given Array

***Problem Statement:*** Given an unsorted array, find the median of the given array.

***What is a Median?***

Median is defined as the value which is present in the middle for a series of values. Note, in order to find the median of an array of integers, we must make sure they are sorted.

# Example

**Input:** [2,4,1,3,5]
 
**Output:** 3

**Explanation :**

After sorting Array: [1,2,3,4,5] now the middle element of series is 3

---

# Approach

```
The problem requires us to simply implement the mathematical formula programmatically.
Hence, we need to make sure that the array is sorted and calculate the answer based on whether n is odd or even.

1.Sort the array in ascending order
2.Check whether n is odd or even
3.Calculate the median accordingly.
```
---

# Code :

```java
import java.util.Arrays;

class Solution {
    // Function to calculate the median of the array
    public void getMedian(int[] arr, int n) {
        Arrays.sort(arr);  // Sort the array to arrange elements in order

        if (n % 2 == 0) {
            // If the array size is even, calculate the average of two middle elements
            int ind1 = (n / 2) - 1;
            int ind2 = (n / 2);
            System.out.println((double) (arr[ind1] + arr[ind2]) / 2);  // Return the median for even-sized array
        } else {
            // If the array size is odd, return the middle element
            System.out.println(arr[n / 2]);
        }
    }
}
```
---

# complexity Analysis

**Time Complexity:** `O(N*log N)`, as sorting of array is involved.


**Space Complexity:** `O(1)`, no extra space required.
