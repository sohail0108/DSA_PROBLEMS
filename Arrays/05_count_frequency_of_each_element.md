# Count frequency of each element in the array
**Problem Statement:** Given an array, we have found the number of occurrences of each element in the array.
# Example
**Input :** arr[] = {10,5,10,15,10,5};

**Output :**  
10  3

5  2
         
15  1

**Explanation :** 

   10 occurs 3 times in the array
  
   5 occurs 2 times in the array
   
   15 occurs 1 time in the array

  ---

# Optimal Approach
We want to count how many times each element appears in the array. Using a hash map allows us to track frequencies efficiently as we traverse the array, avoiding the need for nested loops.

```
Create an unordered_map to store element-frequency pairs.

Traverse the array and for each element, increment its count in the map.

After processing the array, iterate through the map and print each element along with its frequency.
```
# code
```java
// Function to count frequency of each element in the array using HashMap
    public void Frequency(int[] arr, int n) {
        // Create a HashMap to store frequency of each element
        HashMap<Integer, Integer> map = new HashMap<>();

        // Traverse the array and count frequencies
        for (int i = 0; i < n; i++) {
            map.put(arr[i], map.getOrDefault(arr[i], 0) + 1);
        }

        // Traverse through the HashMap and print frequencies
        for (Map.Entry<Integer, Integer> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " " + entry.getValue());
        }
    }
```
**Time Complexity:** `O(N)` , where N is the number of elements in the array. Each element is processed once.

**Space Complexity:** ``O(N)``, for storing frequencies of unique elements in the unordered_map.

