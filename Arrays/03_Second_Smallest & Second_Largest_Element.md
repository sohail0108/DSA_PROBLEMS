# Find Second Smallest and Second Largest Element in an array

## Problem Statement
 Given an array, find the second smallest and second largest element in the array. Print ‘-1’ in the event that either of them doesn’t exist.

## Example

### Input
```
 arr = [1, 2, 4, 7, 7, 5]  
```

### Output
```
Second Smallest : 2

Second Largest : 5  
```

### Explanation

The elements are sorted as 1, 2, 4, 5, 7, 7.  
Hence, the second smallest element is 2, and the second largest element is 5.

---

## Brute Force Approach
```
Sort the array in ascending order.

The element at the second index (index 1) is the second smallest element.

The element at the second index from the end (index length-2) is the second largest element.
```



## Code

```java
  public static void getElements(int[] arr, int n) {
        
        // Edge case: when the array has less than 2 elements
        if (n == 0 || n == 1) {
            System.out.println(-1 + " " + -1);  // Print -1 for both second smallest and second largest
            return;
        }

        // Sort the array to easily find the second smallest and second largest elements
        Arrays.sort(arr);

        // Second smallest element is at index 1 after sorting
        int small = arr[1];

        // Second largest element is at index n-2 after sorting
        int large = arr[n - 2];

        // Output the second smallest and second largest elements
        System.out.println("Second smallest is " + small);
        System.out.println("Second largest is " + large);
    }
```

---

## Time Complexity
```
O(N log N), for sorting the array.
```

## Space Complexity
```
O(1), as we are using a constant amount of space for variables.
```

---

## Better Approach
```
Perform a single traversal to find the smallest and largest elements in the array.

After that, traverse the array again to find the element just greater than the smallest element (this will be the second smallest).

Similarly, find the element just smaller than the largest element (this will be the second largest).
```



## Code

```java
  public static void getElements(int[] arr, int n) {

        // Edge case: when the array has less than 2 elements
        if (n == 0 || n == 1) {
            System.out.println(-1 + " " + -1);  // Print -1 for both second smallest and second largest
            return;
        }

        // Initialize variables to track the smallest, second smallest, largest, and second largest elements
        int small = Integer.MAX_VALUE, second_small = Integer.MAX_VALUE;
        int large = Integer.MIN_VALUE, second_large = Integer.MIN_VALUE;

        // Find the smallest and largest elements in the array
        for (int i = 0; i < n; i++) {
            small = Math.min(small, arr[i]);  // Update the smallest element
            large = Math.max(large, arr[i]);  // Update the largest element
        }

        // Find the second smallest and second largest elements
        for (int i = 0; i < n; i++) {
            if (arr[i] < second_small && arr[i] != small) {
                second_small = arr[i];  // Update second smallest if a smaller element is found
            }
            if (arr[i] > second_large && arr[i] != large) {
                second_large = arr[i];  // Update second largest if a larger element is found
            }
        }

        // Output the second smallest and second largest elements
        System.out.println("Second smallest is " + second_small);
        System.out.println("Second largest is " + second_large);
    }
```



## Time Complexity
```
O(N), we do two linear traversals in our array.
```

## Space Complexity
```
O(1), as we are using a constant amount of space for variables.
```

---

## Optimal Approach 
```
We will need four variables: small, second_small, large, and second_large. Initialize small and second_small to INT_MAX, and large and second_large to INT_MIN.

Second Smallest Algorithm:

If the current element is smaller than 'small', update the values of second_small and small.
Else if the current element is smaller than 'second_small', update the value of second_small.
After traversing the array, the second smallest element will be stored in the variable second_small.

Second Largest Algorithm:

If the current element is larger than 'large', update the values of second_large and large.
Else if the current element is larger than 'second_large', update the value of second_large.
After traversing the array, the second largest element will be stored in the variable second_large.
```



## Code

```java
  // Function to find the second smallest element in the array
   public static int secondSmallest(int[] arr, int n) {
        // Edge case: if the array has fewer than 2 elements
        if (n < 2)
            return -1;

        int small = Integer.MAX_VALUE;
        int second_small = Integer.MAX_VALUE;

        // Loop through the array to find the second smallest element
        for (int i = 0; i < n; i++) {
            // Update the smallest and second smallest values
            if (arr[i] < small) {
                second_small = small;
                small = arr[i];
            } 
            else if (arr[i] < second_small && arr[i] != small) {
                second_small = arr[i];
            }
        }
        return second_small; // Return the second smallest element
    }

   // Function to find the second largest element in the array
   public static int secondLargest(int[] arr, int n) {
        // Edge case: if the array has fewer than 2 elements
        if (n < 2)
            return -1;

        int large = Integer.MIN_VALUE, second_large = Integer.MIN_VALUE;

        // Loop through the array to find the second largest element
        for (int i = 0; i < n; i++) {
            // Update the largest and second largest values
            if (arr[i] > large) {
                second_large = large;
                large = arr[i];
            } 
            else if (arr[i] > second_large && arr[i] != large) {
                second_large = arr[i];
            }
        }
        return second_large; // Return the second largest element
    }

```



## Time Complexity
```
O(N), we do two linear traversals in our array.
```

## Space Complexity
```
O(1), as we are using a constant amount of space for variables.
```

