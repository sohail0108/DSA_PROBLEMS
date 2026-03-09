# Sum of Cubes in a Range

## Problem Statement

Given two integers **a** and **b**, determine the **sum of the cubes of all numbers** in the range from **a to b (inclusive)**.

In other words, calculate:

```
a³ + (a+1)³ + (a+2)³ + ... + b³
```

---

# Example

### Input

```
a = 4
b = 9
```

### Calculation

```
4³ + 5³ + 6³ + 7³ + 8³ + 9³
= 64 + 125 + 216 + 343 + 512 + 729
= 1989
```

### Output

```
1989
```

---

# Approach

1. Read two integers **a** and **b**.
2. Initialize a variable **total = 0**.
3. Run a loop from **a to b**.
4. For every number **i**, compute its cube:

```
i * i * i
```

5. Add it to **total**.
6. After the loop ends, print **total**.

This approach simply iterates through the range and accumulates the cube values.

---

# Java Code

```java
import java.util.Scanner;

public class prev3 {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int b = sc.nextInt();

        int total = 0;

        for (int i = a; i <= b; i++) {
            total += i * i * i;
        }

        System.out.println(total);
    }
}
```

---

# Complexity Analysis

### Time Complexity

```
O(b - a + 1)
```

We iterate through every number between **a and b**.

### Space Complexity

```
O(1)
```

Only a few variables are used.
