---
title: Algorithm of Quick Sort
date: "2015-05-06T23:46:37.121Z"
---

Quick Sort

Python implementation:

```python
# Best:
# Time - O(nlog(n))
# Space - O(log(n))

# Worst:
# Time - O(n^2)
# Space - O(log(n))

# Step 1 we select a pivot, every number < pivot goes to the left
# of the pivot, every number > pivot goes to the right of the pivot.
# At the end, the pivot is at its sorted position in the list.


def quickSort(list):
    quickSortHelperFunction(list, 0, len(list)-1)
    return list


def quickSortHelperFunction(list, start, end):
    # Base case
    if start >= end:
        return
    # Start pointer
    startPointer = start + 1
    # End pointer
    endPointer = end
    # Select the pivot of the list (here the first element is arbitrarily selected)
    pivot = start

    # Specify where should the pivot element be placed in the sorted list
    while endPointer >= startPointer:
        if (list[startPointer] > list[pivot]
                and list[endPointer] < list[pivot]):
            list[startPointer], list[endPointer] = list[endPointer], list[startPointer]

        if list[startPointer] <= list[pivot]:
            startPointer += 1

        if list[endPointer] >= list[pivot]:
            endPointer -= 1
    # Swap the pivot element with the end pointer element
    list[pivot], list[endPointer] = list[endPointer], list[pivot]
    # The pivot is now placed in the exact position of the sorted
    # list, with the elements to the left being smaller than it, and
    # the elements to the right being larger than it

    leftPartitionLengthSmaller = (endPointer - 1) - start < end - (endPointer + 1)

    if leftPartitionLengthSmaller:
        quickSortHelperFunction(list, start, endPointer - 1)
        quickSortHelperFunction(list, endPointer + 1, end)

    else:
        quickSortHelperFunction(list, endPointer + 1, end)
        quickSortHelperFunction(list, start, endPointer - 1)

```
