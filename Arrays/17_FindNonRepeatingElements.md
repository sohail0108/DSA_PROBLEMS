# Find Repeating Elements in an Array (Using HashMap)

## Problem Statement
Given an array of **N integers**, find all the **repeating elements** in the array.

An element is considered repeating if it appears **more than once** in the array.

---

## Example

### Input
```
arr = [1, 2, 3, 1, 3, 6, 6]
```

### Output
```
[1, 3, 6]
```

---

## Approach
1. Create a **HashMap** to store the frequency of each element.
2. Traverse the array and update the count of each element in the HashMap.
3. Traverse the map and collect elements whose frequency is **greater than 1**.
4. Return the list of repeating elements.

---

## Code

```java
import java.util.*;

public static List<Integer> findRepeating(int[] arr){

    HashMap<Integer, Integer> map = new HashMap<>();
    List<Integer> result = new ArrayList<>();

    for(int num : arr){
        map.put(num, map.getOrDefault(num, 0) + 1);
    }

    for(int key : map.keySet()){
        if(map.get(key) > 1){
            result.add(key);
        }
    }

    return result;
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
O(N)
```
