# Circular Rotation of an Array

## Problem Statement
Given an array of **N elements**, perform a **circular rotation to the right by one position**.

In circular rotation, the last element moves to the first position and all other elements shift one position to the right.

---

## Example

### Input
```
arr = [1, 2, 3, 4, 5]
```

### Output
```
[5, 1, 2, 3, 4]
```

---

## Approach
1. Store the last element of the array in a variable.
2. Traverse the array from right to left and shift each element one position to the right.
3. Place the stored last element at index `0`.
4. Return the rotated array.

---

## Code

```java
public static void circularRotate(int[] arr){

    int n = arr.length;

    int last = arr[n - 1];

    for(int i = n - 1; i > 0; i--){
        arr[i] = arr[i - 1];
    }

    arr[0] = last;
}
```

---

## Complexity

**Time Complexity**

```
O(N)
```

**Space Complexity**

```
O(1)
```
