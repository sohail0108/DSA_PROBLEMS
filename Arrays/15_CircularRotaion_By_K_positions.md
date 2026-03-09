# Circular Rotation of an Array by K Positions

## Problem Statement
Given an array of **N elements** and an integer **K**, perform a **circular rotation of the array to the right by K positions**.

In circular rotation, elements shifted out from the end of the array reappear at the beginning.

---

## Example

### Input
```
arr = [1, 2, 3, 4, 5]
k = 2
```

### Output
```
[4, 5, 1, 2, 3]
```

---

## Approach
1. Compute `k = k % n` to handle cases where `k > n`.
2. Reverse the entire array.
3. Reverse the first `k` elements.
4. Reverse the remaining `n-k` elements.
5. The array becomes rotated by `k` positions.

---

## Code

```java
public static void rotateArray(int[] arr, int k) {

    int n = arr.length;
    k = k % n;

    reverse(arr, 0, n - 1);
    reverse(arr, 0, k - 1);
    reverse(arr, k, n - 1);
}

public static void reverse(int[] arr, int start, int end) {

    while(start < end) {

        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;

        start++;
        end--;
    }
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
