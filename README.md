# Grokking-Algorithms--Notes

# Binary Search

Code in Python:

```python
def binary_search(mlist, item):
    low = 0
    high = len(mlist) - 1

    while low <= high:
        mid = (low + high) // 2  # Calculate the middle of the list
        guess = mlist[mid]  

        if guess == item:
            return mid  # Item found, return its index
        elif guess > item:
            high = mid - 1  # Search the left half
        else:
            low = mid + 1  # Search the right half

    return None  # Item not found
```

### Testing:


```python
my_list = [1, 3, 5, 7, 9]

# Trying
print(binary_search(my_list, 3))  # -> 1
print(binary_search(my_list, -1))  # -> None
```

The number of steps in binary search is calculated using log2(). For example, log2(128) is 7.

---

# Some common Big O run times

- O(log n), also known as log time. Example: Binary search. --> Fastest
    
- O(n), also known as linear time. Example: Simple search. -->  faseter
    
- O(n * log n). Example: A fast sorting algorithm, like quicksort. --> Slower
    
- O(n²). Example: A slow sorting algorithm, like selection sort. --> Much slower
    
- O(n!). Example: A really slow algorithm, like the traveling salesperson. --> Slowest
    

### Notes:

- Algorithm speed isn’t measured in seconds, but in the growth of the number of operations.
    
- Instead, we talk about how quickly the run time of an algorithm increases as the size of the input increases.
    
- Run time of algorithms is expressed in Big O notation.
    
- O(log n) is faster than O(n), but it gets a lot faster as the list of items you’re searching grows.
    

---

# Arrays and linked lists

- Your computer’s memory is like a giant set of drawers.
    
- When you want to store multiple elements, use an array or a list.
    
- With an array, all your elements are stored right next to each other.
    
- With a list, elements are strewn all over, and one element stores the address of the next one.
    
- Arrays allow fast reads. Linked lists allow fast inserts and deletes.
    
- All elements in the array should be the same type (all ints, all doubles, and so on).
    

### Function to find the smallest element in an array:



```python
def findSmallest(arr):
    smallest = arr[0]
    smallest_index = 0
    for i in range(1, len(arr)):
        if arr[i] < smallest:
            smallest = arr[i]
            smallest_index = i
    return smallest_index
```

### Function to sort an array:



```python
def selectionSort(arr):
    newArr = []
    for i in range(len(arr)):
        smallest = findSmallest(arr)
        newArr.append(arr.pop(smallest))
    return newArr

print(selectionSort([5, 3, 6, 2, 10]))
```

