# Sum of Table of a Number

## Problem Statement
Given a number **N**, your task is to calculate and print the **sum of the multiplication table of N from 1 to 10**.

The multiplication table of a number N is:

N × 1, N × 2, N × 3, ..., N × 10

You need to compute the sum of all these values.

---

## Example 1

### Input
```
N = 10
```

### Calculation
```
10 × (1 + 2 + 3 + ... + 10)
= 10 × 55
= 550
```

### Output
```
550
```

---

## Example 2

### Input
```
N = 68
```

### Calculation
```
68 × (1 + 2 + ... + 10)
= 68 × 55
= 3740
```

### Output
```
3740
```

---

# Approach

The multiplication table of a number **N** consists of:

```
N × 1 + N × 2 + N × 3 + ... + N × 10
```

We can factor out **N**:

```
N × (1 + 2 + 3 + ... + 10)
```

The sum of numbers from **1 to 10** is:

```
55
```

Therefore the formula becomes:

```
Sum = 55 × N
```

Using this formula we can compute the answer in **constant time**.

---

# Code

```java
public class SumOfTable {

    public static int sumOfTable(int n) {
        return 55 * n;
    }

    public static void main(String[] args) {

        int n = 68;

        int result = sumOfTable(n);

        System.out.println(result);
    }
}
```

---

# Complexity Analysis

### Time Complexity
```
O(1)
```

### Space Complexity
```
O(1)
```
