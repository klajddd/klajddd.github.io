---
title: Algorithm - Breadth first search
date: "2015-05-06T23:46:37.121Z"
---

Breadth first search is an algorithm used for searching through all the nodes in a graph or tree structure.

Python implementation: 

```python
# Time: O(node + edge)
# Space: O(node)
def breadthFirstSearch(self, resultList):
    # Create a queue, a FIFO strucutre, to contain
    # all nodes that will be processed
    queue = [self]
    while len(queue) > 0:
        current = queue.pop(0)
        resultList.append(current.name)
        # Add child nodes to the queue
        for child in current.children:
            queue.append(child)
    return resultList
```
