---
title: Algorithm of Depth First Search
date: "2015-05-06T23:46:37.121Z"
---

Depth first search is an algorithm used for searching through nodes in a graph or a tree structure.

Python implementation:

```python
# Time: O(node + edge)
def depthFirstSearch(self, resultList):
    # Append node to the result list
    resultList.append(self.name)
    # Continue calling the function on the child nodes
    # going through the deeper levels of the tree structure
    for child in self.children:
        child.depthFirstSearch(resultList)
    return resultList
```
