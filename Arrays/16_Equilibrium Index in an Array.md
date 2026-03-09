# Equilibrium Index in an Array

## Problem Statement
Given an array of **N integers**, find the **equilibrium index** of the array.

An equilibrium index is an index such that the **sum of elements on the left side is equal to the sum of elements on the right side**.

If no such index exists, return **-1**.

---

## Example

### Input
```
arr = [-7, 1, 5, 2, -4, 3, 0]
```

### Output
```
3
```

### Explanation
```
Left Sum  = -7 + 1 + 5 = -1
Right Sum = -4 + 3 + 0 = -1
```

Both sums are equal, so index **3** is the equilibrium index.

---

## Approach
1. Calculate the **total sum** of the array.
2. Initialize a variable `leftSum = 0`.
3. Traverse the array.
4. For each index:
   - Subtract the current element from the total sum (this becomes the right sum).
   - Compare `leftSum` and `rightSum`.
5. If both are equal, return the current index.
6. Otherwise update `leftSum` by adding the current element.

---

## Code

```java
public static int equilibriumIndex(int[] arr) {

    int totalSum = 0;

    for(int num : arr){
        totalSum += num;
    }

    int leftSum = 0;

    for(int i = 0; i < arr.length; i++){

        totalSum -= arr[i];

        if(leftSum == totalSum){
            return i;
        }

        leftSum += arr[i];
    }

    return -1;
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
