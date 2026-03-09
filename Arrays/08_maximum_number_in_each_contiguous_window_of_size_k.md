# Maximum number in each contiguous window of size k.
**Problem statement:** You are given an array of integers, arr, and an integer k. Your task is to find and print the maximum number in each contiguous window of size k.
# Example:
**Input:** arr = [1, 3, -1, -3, 5, 3, 6, 7] k=3

**Output:** [3, 3, 5, 5, 6, 7]

---

## Brute Force Approach

We solve the problem using the sliding window concept in a simple brute force way.

1. We take a window of size `k` and move it across the array from left to right.
2. For each window, we iterate through all `k` elements inside that window.
3. While iterating, we keep track of the maximum element in that window.
4. After checking all elements in the current window, we store the maximum value in the result array.
5. Then we shift the window by one position and repeat the same process until the array ends.

Since for every window we are scanning `k` elements, the time complexity becomes **O(N × K)**.

# Code

```java
public class Max {
    public static void main(String[] args) {
        int[] arr = { 1, 3, -1, -3, 5, 3, 6, 7 };
        int k = 3;
        int[] arr1 = new int[arr.length - k + 1];
        for (int i = 0; i < arr.length - k + 1; i++) {
            int max = arr[i];
            for (int j = i; j < i + k; j++) {
                if (arr[j] > max) {
                    max = arr[j];
                }
            }
            arr1[i] = max;
        }
        for (int i : arr1) {
            System.out.print(i + " ");
        }
    }
}

```

### Time Complexity
```
O(N * K)
```

### Space Complexity
```
O(N - K + 1)
```

---

## Optimal Approach (Using Deque)

To optimize the solution, we use a **Deque (Double Ended Queue)** to efficiently track the maximum element for each sliding window.

Instead of checking all `k` elements for every window, we maintain the indices of useful elements in the deque.

### Steps

1. We use a deque to store **indices of array elements**.
2. The deque will maintain elements in **decreasing order of values**.
3. Before inserting a new element:
   - Remove elements from the **front** if they are outside the current window.
4. Remove elements from the **back** of the deque if they are smaller than the current element, since they can never be the maximum.
5. Add the current index to the deque.
6. The element at the **front of the deque** will always be the maximum element of the current window.
7. Store this value in the result array.

This way each element is added and removed from the deque at most once.

# code:

```java
import java.util.*;

public class SlidingWindowMax {

    public static int[] maxSlidingWindow(int[] nums, int k) {

        int n = nums.length;
        int[] ans = new int[n - k + 1];

        Deque<Integer> dq = new LinkedList<>();

        for (int i = 0; i < n; i++) {

            // remove elements out of window
            if (!dq.isEmpty() && dq.peekFirst() <= i - k) {
                dq.pollFirst();
            }

            // remove smaller elements
            while (!dq.isEmpty() && nums[dq.peekLast()] < nums[i]) {
                dq.pollLast();
            }

            dq.offerLast(i);

            if (i >= k - 1) {
                ans[i - k + 1] = nums[dq.peekFirst()];
            }
        }

        return ans;
    }
}
```

### Time Complexity
```
O(N)
```

### Space Complexity
```
O(K)
```
