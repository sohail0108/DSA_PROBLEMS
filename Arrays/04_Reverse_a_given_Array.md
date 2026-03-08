# Reverse a given Array

**Problem Statement:** You are given an array. The task is to reverse the array and print it.

# Examples

**Input:** N = 5, arr[] = {5,4,3,2,1}

**Output:** {1,2,3,4,5}

**Explanation:** Since the order of elements gets reversed the first element will occupy the fifth position, the second element occupies the fourth position and so on.

---
# Brute Force Approach
We want to reverse the elements of an array, so the first element becomes last and the last becomes first. A straightforward way is to create a new array and start placing the original array's elements from the back into the front of the new array. This way, we preserve the original and get the reversed version separately.

```

Initialize an empty array of the same size as the original array.
Start a loop from the last index of the original array and go backward.
For each element while going backward, insert it at the current forward index of the new array.
Continue until all elements are copied in reverse order.
Return or print the reversed array.
```
# Code:
```java
  public int[] reverseArray(int[] arr) {
        // Get the length of the input array
        int n = arr.length;

        // Create a new array of same size to store reversed elements
        int[] ans = new int[n];

        // Loop to fill ans[] from the back of arr[]
        for (int i = 0; i < n; i++) {
            // Place elements from the end of arr into the start of ans
            ans[i] = arr[n - 1 - i];
        }

        // Return the reversed array
        return ans;
    }
```
**Time Complexity:** O(n) Each element is visited once in a loop, where n is the number of elements in the input array.

**Space Complexity:** O(n) An additional array of the same size is used to store the reversed elements.

---
# Better Approach
This approach improves on the previous one by reversing the array in-place, avoiding the need for extra space. It uses two pointers to simultaneously traverse the array from both ends, swapping the elements until the center is reached. This way, we avoid creating a new array and perform the reverse operation efficiently using constant space.
```
Initialize a pointer p1 at the start of the array (index 0).
Initialize another pointer p2 at the end of the array (index n - 1).
While p1 is less than p2, do the following:
Swap the elements at positions p1 and p2.
Increment p1 by 1.
Decrement p2 by 1.
Continue this process for only the first n/2 elements of the array.
```
<img width="633" height="359" alt="image" src="https://github.com/user-attachments/assets/5018273b-f07a-48fb-a8e8-b2a2296fb6cd" />
<img width="633" height="359" alt="image" src="https://github.com/user-attachments/assets/4ff696c9-e624-41e3-8059-4365add7c837" />

# Code
```java
  // Function to reverse the array in-place
    public void reverseArray(int[] arr) {
        // Initialize pointer to the beginning of the array
        int p1 = 0;

        // Initialize pointer to the end of the array
        int p2 = arr.length - 1;

        // Loop until the two pointers meet in the middle
        while (p1 < p2) {
            // Swap the elements at p1 and p2
            int temp = arr[p1];
            arr[p1] = arr[p2];
            arr[p2] = temp;

            // Move the left pointer one step to the right
            p1++;

            // Move the right pointer one step to the left
            p2--;
        }
    }
```
**Time Complexity:** O(n) Where n is the number of elements in the array. Each element is visited at most once due to the two-pointer approach.
**Space Complexity:** O(1) No extra space is used other than a few pointers and variables. The array is reversed in-place.

---
# Built-in Library Function Approach
Java (using Collections.reverse()): In Java, the Collections.reverse() method can be used to reverse a list in-place. Arrays need to be converted to a list first, as the Collections utility works with List types, not primitive arrays.
```java
public void reverseArray(List<Integer> arr) {
        // Call Collections.reverse to reverse list in-place
        Collections.reverse(arr);
    }
```
**Time Complexity:** O(n), because each element is visited once and possibly swapped once with its mirror index.

**Space Complexity:** O(1) for C++, Java, and JavaScript (in-place), but O(n) for Python slicing since it creates a new list and then assigns back (unless using two pointers).









