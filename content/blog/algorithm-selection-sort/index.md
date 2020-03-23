---
title: Algorithm of selection sort
date: "2015-05-06T23:46:37.121Z"
---

Selection sort is an in-place sorting algorithm, which divides the list that it sorts into two parts, the ordered and the unordered parts. It gradually moves the elements of the list from the unordered part to the ordered part of the list.

Python implementation:

```python
# Time - O(n^2)
# Space - O(1)
def selectionSort(list):
    currentIndex = 0
    while currentIndex < len(list) - 1:
        minimumIndex = currentIndex
        # Iterate the list from the second element onwards to find the minimum value
        for i in range(currentIndex + 1, len(list)):
            if list[i] < list[minimumIndex]:
                minimumIndex = i
        # Swap the minimum value of the unordered part of the list
        # with the current value of the ordered part of the list
        list[currentIndex], list[minimumIndex] = list[minimumIndex], list[currentIndex]
        currentIndex += 1
    return list
```
