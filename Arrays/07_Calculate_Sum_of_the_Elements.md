# Calculate Sum of the Elements of the Array
**Problem Statement:** Given an array arr of size n, the task is to find the sum of all the elements in the array .
# Example
Input: N = 5, array[] = {1,2,3,4,5}

Output: 15

Explanation: Sum of all the elements is 1+2+3+4+5 = 15

---

# Optimal Approach

Most languages provide built-in functions or methods that efficiently sum all elements of an array. Using these eliminates the need to write explicit loops, making code concise and sometimes faster due to optimized internal implementations.
Use the language's built-in sum or reduce function to get the sum of all elements.

Return the result directly.

# code:

```java
 public int arraySum(int[] arr) {
        // Use Arrays.stream to create IntStream and sum it
        return Arrays.stream(arr).sum();
    }
```
**Time Complexity:** ``O(N)``, where N is the number of elements. Even built-in functions must touch every element to sum.

**Space Complexity:** ``O(1)``, only constant extra space is used.
