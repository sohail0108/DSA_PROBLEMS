# Average of Elements in an Array

## Problem Statement
Given an array of **N integers**, calculate the **average of all elements present in the array**.

The average of an array is calculated using the formula:

```
Average = (Sum of all elements) / Number of elements
```

---

## Example

### Input
```
N = 5
Array = [2, 4, 6, 8, 10]
```

### Calculation
```
Sum = 2 + 4 + 6 + 8 + 10 = 30
Average = 30 / 5 = 6.0
```

### Output
```
6.0
```

---

# Approach

1. Read the number of elements **N**.
2. Create an array of size **N**.
3. Take input for all array elements.
4. Initialize a variable **sum = 0**.
5. Traverse the array and add each element to **sum**.
6. Calculate the average using:

```
average = sum / N
```

7. Print the average.

---

# Java Code

```java
import java.util.Scanner;

public class AverageOfArray {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the number of elements:");
        int n = sc.nextInt();

        int[] arr = new int[n];

        // Input array elements
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        int sum = 0;

        // Calculate sum
        for (int i : arr) {
            sum += i;
        }

        // Calculate average
        float avg = (float) sum / n;

        System.out.println("The average of the array is " + avg);

        sc.close();
    }
}
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
