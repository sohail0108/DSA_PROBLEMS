# Adding Element in an Array

***Problem Statement:*** Given an array of N integers, write a program to add an array element at the beginning, end, and at a specific position.

# Example

**Input:** N = 5, array[] = {1,2,3,4,5}

insertbeginning(6)

insertending(7)

insertatpos(8,4)

**Output:** 6,1,2,8,3,4,5,7

**Explanation:** 6 is added at the beginning and 7 is added at the end and 8 is added at position 4.

---

# Insertion at beginning

For inserting the element at the beginning we should first shift all elements of the array to left by 1 index and then insert an element at the 0th position

```java
import java.util.*;

// Class to handle insertion
class Solution {
    // Function to insert at beginning
    public static int[] insertAtBeginning(int[] arr, int x) {
        // Create new array of bigger size
        int[] newArr = new int[arr.length + 1];
        // Insert new element at first position
        newArr[0] = x;
        // Copy old elements after it
        for (int i = 0; i < arr.length; i++) {
            newArr[i + 1] = arr[i];
        }
        return newArr;
    }
}
```
**Time Complexity:** O(n), since n iterations are required to shift the array element to right by 1 position

**Space Complexity:** O(n+1). 

---

# Insetion at ending

For adding the elements at the end, just add the element at the nth index.

```java

// Class to handle insertion
class Solution {
    // Function to insert at end of array
    public static int[] insertAtEnd(int[] arr, int x) {
        // Create new array with +1 size
        int[] newArr = new int[arr.length + 1];
        // Copy old elements
        for (int i = 0; i < arr.length; i++) {
            newArr[i] = arr[i];
        }
        // Place new element at the end
        newArr[arr.length] = x;
        return newArr;
    }
}
```
**Time Complexity:** O(n), since n iterations are required to shift the array element to right by 1 position

**Space Complexity:**  O(n+1). 

---

# Insertion at a specific position

For adding the element at a specific position, just shift array elements to right by one position, and after that add an element at the desired position.
```java
import java.util.*;

// Class to handle insertion
class Solution {
    // Function to insert at a given position (0-based index)
    public static int[] insertAtPosition(int[] arr, int pos, int x) {
        // Create new array of +1 size
        int[] newArr = new int[arr.length + 1];

        // Copy elements before position
        for (int i = 0; i < pos; i++) {
            newArr[i] = arr[i];
        }

        // Insert new element at pos
        newArr[pos] = x;

        // Copy remaining elements
        for (int i = pos; i < arr.length; i++) {
            newArr[i + 1] = arr[i];
        }

        return newArr;
    }
}
```
**Time Complexity:** O(n), since n iterations are required to shift the array element to right by 1 position

**Space Complexity:**  O(n+1). 

----
