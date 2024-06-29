
# C++
## 📝1.Searching Algorithms

### 1.1 Linear search - Iterates through each element of the array sequentially until the target element is found or the end of the array is reached.
(line by line going on a element and search target )
##### Time complexity of Linear search  is O(n)

### 1.2 Binary Search - Requires a sorted array. Divides the array into halves and compares the target value with the middle element. Continues narrowing down the search until the element is found or deemed not present.
#### Time complexity of Binary search  is O(logn)
=> n/2^k = 1
##### n = 2^k 
### O(k) = O(logn)

### 1.2.1 condition  for Binary Search 
#### 1. Element should be Shorted 
#### 2. Comparison Operation:
The elements in the array must support comparison operations (usually <, >, <=, >=, ==) so that the algorithm can determine whether the target value is less than, greater than, or equal to the middle element.
#### 3. Continuous Indexing:
Binary search uses indices to access elements. Make sure the indexing mechanism (like array indexing in C++) is continuous and straightforward without gaps or missing elements.
#### 4. Single Occurrence:
Binary search assumes that each element in the array is unique. If there are duplicate elements, binary search may not return the desired index consistently, or it may not work at all unless you adapt the algorithm to handle duplicates in a specific way.

#### 5. Memory Access:
 Ensure that memory access is well-defined and within the bounds of the array. Improper memory access can lead to undefined behavior or runtime errors.

### 1.2.2 Binary Search STL
Header file : 
## <algorithm>
#### 1.2.2.1 For Vector 
##### vector intialisation : vector<int> array;

### binary_search(array.begin() , array.end() , target );

#### 1.2.2.2 For static array 
##### vector intialisation : int arr[] = { 1,2,3,4,5,6,7,8,9}; 
### binary_search( base Address , last Address , target ); 
Example - binary_search( arr , arr + size , target);

### 1.2.2.3 Occurrence using STL
### Lower_bound(v.begin() , v.end() , target ); 
for finding first Occurrence

### upper_bound(v.begin() , v.end() , target ); 
for finding last Occurrence
### C++ linear Search 

```javascript
int linearSearch(int arr[], int n, int target) {
    for (int i = 0; i < n; ++i) {
        if (arr[i] == target) {
            return i;  // Return the index if found
        }
    }
    return -1;  // Return -1 if target is not found
}
```

### C++ Binary Search

```javascript
int binarySearch(int arr[], int start, int end, int target) {
    //here start = 0 and end = size-1 ; target is what you want to search 

    while (start <= end) {
        int mid = start + (end - start) / 2;
        if (arr[mid] == target) {
            return mid;  // Return the index if found
        } else if (arr[mid] < target) {
            start = mid + 1;
        } else {
            end = mid - 1;
        }
    }
    return -1;  // Return -1 if target is not found
}
```

