# Big-O Notation - For Coding Interviews

## Introduction

Big O notation is a fundamental concept in computer science, representing the time and space complexity of algorithms. Understanding different complexities is crucial for optimizing code and solving problems efficiently.

## O(1) - Constant Time

- **Description**: Algorithms with constant time complexity.
- **Examples**:
  - Array operations like appending and accessing elements.
  - Hash map operations like insertion, lookup, and deletion.

### Code Example

```python
# Array
nums = [1, 2, 3]
nums.append(4)    # push to end
nums.pop()        # pop from end
nums[0]           # lookup
nums[1]
nums[2]


# HashMap / Set
hashMap = {}
hashMap["key"] = 10     # insert
print("key" in hashMap) # lookup
print(hashMap["key"])   # lookup
hashMap.pop("key")      # remove
```

## O(n) - Linear Time

- **Description**: Algorithms with linear time complexity.
- **Examples**:
  - Iterating through arrays.
  - Searching for elements in an array.

### Code Example

```python
nums = [1, 2, 3]
sum(nums)           # sum of array
for n in nums:      # looping
    print(n)

nums.insert(1, 100) # insert middle
nums.remove(100)    # remove middle
print(100 in nums)  # search

import heapq
heapq.heapify(nums) # build heap

# sometimes even nested loops can be O(n)
# (e.g. monotonic stack or sliding window)
```

## O(n^2) - Quadratic Time

- **Description**: Algorithms with quadratic time complexity.
- **Examples**:
  - Nested loops iterating over 2D arrays.
  - Certain sorting algorithms like insertion sort.

### Code Example

```python
# Traverse a square grid
nums = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
for i in range(len(nums)):
    for j in range(len(nums[i])): 
        print(nums[i][j])


# Get every pair of elements in array
nums = [1, 2, 3]
for i in range(len(nums)):
    for j in range(i + 1, len(nums)):
        print(nums[i], nums[j])

# Insertion sort (insert in middle n times -> n^2)
```

## O(n * m) - Polynomial Time

- **Description**: Algorithms with polynomial time complexity.
- **Examples**:
  - Nested loops with different ranges of iterations.
  - Operations involving two different input sizes.

### Code Example

```python
# Get every pair of elements from two arrays
nums1, nums2 = [1, 2, 3], [4, 5]
for i in range(len(nums1)):
    for j in range(len(nums2)):
        print(nums1[i], nums2[j])

# Traverse rectangle grid
nums = [[1, 2, 3], [4, 5, 6]]
for i in range(len(nums)):
    for j in range(len(nums[i])):
        print(nums[i][j])
```

## O(n^3) - Cubic Time

- **Description**: Algorithms with cubic time complexity.
- **Examples**:
  - Algorithms involving three nested loops or operations on three-dimensional data structures.

### Code Example

```python
# Get every triplet of elements in array
nums = [1, 2, 3]
for i in range(len(nums)):
    for j in range(i + 1, len(nums)):
        for k in range(j + 1, len(nums)):
            print(nums[i], nums[j], nums[k])
```

## O(log n) - Logarithmic Time

- **Description**: Algorithms with logarithmic time complexity.
- **Examples**:
  - Binary search on sorted arrays.
  - Operations on balanced binary search trees.

### Code Example

```python
# Binary search
nums = [1, 2, 3, 4, 5]
target = 6
l, r = 0, len(nums) - 1
while l <= r:
    m = (l + r) // 2
    if target < nums[m]:
        r = m - 1
    elif target > nums[m]:
        l = m + 1
    else:
        print(m)
        break

# Binary Search on BST
def search(root, target):
    if not root:
        return False
    if target < root.val:
        return search(root.left, target)
    elif target > root.val:
        return search(root.right, target)
    else: 
        return True

# Heap Push and Pop
import heapq
minHeap = []
heapq.heappush(minHeap, 5)
heapq.heappop(minHeap)
```

## O(n log n) - Linearithmic Time

- **Description**: Algorithms with linearithmic time complexity.
- **Examples**:
  - Efficient sorting algorithms like merge sort or heap sort.

### Code Example

```python
# HeapSort
import heapq
nums = [1, 2, 3, 4, 5]
heapq.heapify(nums)     # O(n)
while nums:
    heapq.heappop(nums) # O(logn)

# MergeSort (and most built-in sorting functions)
```

## O(2^n) - Exponential Time

- **Description**: Algorithms with exponential time complexity.
- **Examples**:
  - Recursive algorithms with branching.

### Code Example

```python
# Recursion, tree height n, two branches
def recursion(i, nums):
    if i == len(nums):
        return 0
    branch1 = recursion(i + 1, nums)
    branch2 = recursion(i + 2, nums)

## O(c^n)

# c branches, where c is sometimes n.
def recursion(i, nums, c):
    if i == len(nums):
        return 0
    
    for j in range(i, i + c):
        branch = recursion(j + 1, nums)
```

## O(sqrt(n)) - Square Root Time

- **Description**: Algorithms with square root time complexity.
- **Examples**:
  - Specific algorithms like finding factors of a number.

### Code Example

```python
# Get all factors of n
import math
n = 12
factors = set()
for i in range(1, int(math.sqrt(n)) + 1):
    if n % i == 0:
        factors.add(i)
        factors.add(n // i)
O( n! )
# Permutations
# Travelling Salesman Problem
```

## O(n!) - Factorial Time

- **Description**: Algorithms with factorial time complexity.
- **Examples**:
  - Permutation problems or complex graph problems like the traveling salesman problem.

### Code Example

```python
# Permutations
# Travelling Salesman Problem
# (These problems often involve factorial time complexity.)
```

## Big-O Notation for Coding Interviews

Understanding the time and space complexities of algorithms is crucial for effective problem-solving in coding interviews. Here's a comprehensive breakdown of various complexities and their practical applications in code:

- **O(1)**: Constant time complexity, applicable to operations like array access or hash map insertion and lookup.
- **O(n)**: Linear time complexity, common in iterating through arrays or searching unsorted arrays.
- **O(n^2)**: Quadratic time complexity, seen in nested loops or certain sorting algorithms.
- **O(n * m)**: Polynomial time complexity, involving nested loops with different variables.
- **O(n^3)**: Cubic time complexity, less frequent but relevant in certain scenarios.
- **O(log n)**: Logarithmic time complexity, typical in binary search or operations on balanced trees.
- **O(n log n)**: Linearithmic time complexity, observed in efficient sorting algorithms like merge sort.
- **O(2^n)**: Exponential time complexity, found in recursive algorithms with branching.
- **O(sqrt(n))**: Square root time complexity, rare but utilized in specific algorithms like factorization.
- **O(n!)**: Factorial time complexity, highly inefficient and limited to permutation-related problems.

Understanding these complexities aids in recognizing optimal solutions and optimizing code for efficiency, making it invaluable in coding interviews and real-world software development scenarios.

## Conclusion

Understanding these complexities is crucial for optimizing algorithms in coding interviews or real-world scenarios. Interviewers often seek efficient solutions, so being able to recognize the efficiency of your code can be valuable. However, for rare complexities like O(sqrt(n)) or O(n!), focusing on general understanding rather than precision might be more practical.

Remember, the goal is not necessarily to memorize all these complexities but to comprehend their characteristics and implications on runtime efficiency when analyzing or creating algorithms.

## References
https://neetcode.io/courses/lessons/big-o-notation
