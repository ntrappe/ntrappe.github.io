![BST](header.png)
***Data Structures, Sorting Algorithms, Runtimes, Interview Questions, & Common Questions. Designed by: @github/ntrappe***

---
## Data Structures:

### :pushpin: BINARY SEARCH TREE
#### Useful for: 
Sorting data and everything, including rebalancing, can be done in O(log n).
#### Notes: 
*Generally use unique values (don't want duplicates).*

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Insert      | O(log n)    | O(n)        |      like if we have a linked-list
| Remove      | O(log n)    | O(n)        |
| Search      | O(log n)    | O(n)        |


### :pushpin: ARRAYS
#### Useful for: 
Storing and accessing sequential data, temporarily storing, as an IO buffer
(when reading from a file), lookup table, and hack for multiple return values.

#### Notes: 
*Can implement a dynamic arrays from static ones by continuously allocating double the space
once the array is full.*

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Access      | O(1)        | O(1)        |
| Append      | ---         | O(1)        | scales well
| Insert      | ---         | O(n)        | if insert to front, have to shove everything over
| Remove      | ---         | O(n)        | to remove an item, create new array and copy over vals to keep
| Search      | O(n)        | O(n)        |


### :pushpin: LINKED-LISTS
#### Useful for: 
Useful in lists, queues, and stacks. Often used for circular (round robin) or adjacency lists.

#### Notes: 
*Singly-linked will save up on space and it's simpler to implement 
but it can make it more difficult to access previous nodes.
Doubly-linked takes up double the space since we have 2x the pointers but easier to traverse backwards.*

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Insert (T/H)| O(1)        | O(1)        | for inserting at the head or tail
| Insert      | O(n)        | O(n)        | for items in the middle, need to traverse
| Remove      | O(n)        | O(n)        | 
| Search      | O(n)        | O(n)        |


### :pushpin: STACKS
#### Useful for: 
Useful for undo functions, checking for matching braces, other syntax (or TMs), supports recursion 
behind the scenes, and is used in DFS on a graph.

#### Notes: 
*Has 2 primary operations: push and pop. Last in, first out: what you most recently pushed will be
what comes out when you pop.*

