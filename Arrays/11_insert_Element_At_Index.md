# Insert Element at a Particular Index in an Array

## Problem Statement
Given an array and an element, insert the element at a specific index in the array.

After inserting the element, all the elements to the right of that index should shift one position to the right.

---

## Example

### Input
```
Array = [10, 20, 30, 40, 50]
Element = 25
Index = 2
```

### Output
```
[10, 20, 25, 30, 40, 50]
```

### Explanation
The element **25** is inserted at index **2**.  
All elements from index **2 onward** are shifted one position to the right.

---

# Approach

1. Create a new array with size **n + 1**.
2. Copy elements from the original array into the new array.
3. When the desired index is reached, insert the new element.
4. Shift the remaining elements to the right.
5. Print the new array.

---

# Java Code

```java
import java.util.Arrays;

public class InsertElement {

    public static void main(String[] args) {

        int[] arr = {10, 20, 30, 40, 50};
        int element = 25;
        int index = 2;

        int[] newArr = new int[arr.length + 1];

        // copy elements before index
        for (int i = 0; i < index; i++) {
            newArr[i] = arr[i];
        }

        // insert element
        newArr[index] = element;

        // shift remaining elements
        for (int i = index; i < arr.length; i++) {
            newArr[i + 1] = arr[i];
        }

        System.out.println(Arrays.toString(newArr));
    }
}
```

---

# Code Explanation

### Step 1
Create a new array with one extra space.

```
int[] newArr = new int[arr.length + 1];
```

---

### Step 2
Copy elements before the insertion index.

```
for (int i = 0; i < index; i++)
    newArr[i] = arr[i];
```

---

### Step 3
Insert the new element.

```
newArr[index] = element;
```

---

### Step 4
Shift the remaining elements to the right.

```
for (int i = index; i < arr.length; i++)
    newArr[i + 1] = arr[i];
```

---

# Complexity Analysis

### Time Complexity
```
O(N)
```

### Space Complexity
```
O(N)
```

---

# Final Output

```
[10, 20, 25, 30, 40, 50]
```
