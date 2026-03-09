# Problem: Check if One Array is a Subset of Another
# Problem Statement

Given two arrays arr1[] and arr2[], check whether arr2 is a subset of arr1 or not.

An array arr2 is considered a subset of arr1 if every element of arr2 exists in arr1.

# Example

**Example 1**

**Input**

arr1 = [1, 2, 3, 4, 5]
arr2 = [2, 4]

**Output**

Yes

**Explanation**

All elements of arr2 exist in arr1.

---

**Example 2**

**Input**

arr1 = [1, 2, 3, 4, 5]

arr2 = [2, 6]

**Output**

No

**Explanation**

Element 6 is not present in arr1.

#  Brute Force Approach

```
Traverse each element of arr2.

For every element in arr2, check if it exists in arr1.

If any element is not found in arr1, return false.

If all elements are found, return true.
```

# code:

```java
public class ArraySubset {

    public static boolean isSubset(int[] arr1, int[] arr2) {

        for (int i = 0; i < arr2.length; i++) {

            boolean found = false;

            for (int j = 0; j < arr1.length; j++) {

                if (arr2[i] == arr1[j]) {
                    found = true;
                    break;
                }
            }

            if (!found) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {

        int[] arr1 = {1,2,3,4,5};
        int[] arr2 = {2,4};

        if (isSubset(arr1, arr2)) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
    }
}
```

# Complexity

**Time Complexity:** `O(N × M)` N = size of arr1
M = size of arr2

**Space Complexity:** `O(1)`

# Optimal Approach (Using HashSet)

```
Store all elements of arr1 in a HashSet

Check every element of arr2 in the set

If any element is missing → not subset
```
# code:

```java
import java.util.HashSet;

public class ArraySubset {

    public static boolean isSubset(int[] arr1, int[] arr2) {

        HashSet<Integer> set = new HashSet<>();

        for (int num : arr1) {
            set.add(num);
        }

        for (int num : arr2) {
            if (!set.contains(num)) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {

        int[] arr1 = {1,2,3,4,5};
        int[] arr2 = {2,4};

        System.out.println(isSubset(arr1, arr2));
    }
}
```
# Optimal Complexity
**Time Complexity:** `O(N + M)`

**Space Complexity:** ` O(N)`
