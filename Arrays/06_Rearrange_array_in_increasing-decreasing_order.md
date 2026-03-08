# Rearrange array in increasing-decreasing order
**Problem Statement:** Rearrange a given array such that the first half is arranged in increasing order, and the second half is arranged in decreasing order

Examples

**Input:** [8 7 1 6 5 9]

**Output:** [1 5 6 9 8 7]

**Explanation:** First three elements are in the ascending order and next three elements are in the descending order.

---
# Approach

Since we need to arrange the first half in ascending order and second half in descending order, we have to first sort the entire array to convert both the halves in ascending order.

Now, to arrange the second half in descending order, we can simply reverse all the elements of second half as they are already arranged in ascending order.

<img width="763" height="474" alt="image" src="https://github.com/user-attachments/assets/2534e773-9a4d-4df9-8466-765f5a8b447d" />

# code :


```java
// Function to rearrange first half ascending and second half descending
    public void rearrangeArray(int[] arr) {
        // Sort the array
        Arrays.sort(arr);

        int n = arr.length;
        // Reverse the second half
        for (int i = n / 2, j = n - 1; i < j; i++, j--) {
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
        }
    }
```
**Time Complexity:** `O(N*logN)`, We sort the entire array and then reverse the second half.

**Space Complexity:** `O(1)`, constant additional space is used.







