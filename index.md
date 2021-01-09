
# CSE 110 Lab1

![BST](header_v2.png)

###### This page will provide all the tools and tricks for fellow CSE undergraduates to excel in coding interviews. It includes: [Data Structures](#data-structures), [Programming Languages](#programming-languages), [Sorting Algorithms](#sorting-algorithms), [Preparation](#how-to-prepare), & [Common Questions](#common-questions). Designed by: [ntrappe](https://github.com/ntrappe) ###### 


![LN](line.png)

## Data Structures:

### :pushpin: BINARY SEARCH TREE
#### Useful for: 
Sorting data and everything, including rebalancing, can be done in O(log n).
#### Notes: 
Generally use ***unique*** values (don't want duplicates).

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Insert      | O(log n)    | O(n)        |      like if we have a linked-list
| Remove      | O(log n)    | O(n)        |
| Search      | O(log n)    | O(n)        |

---

### :pushpin: ARRAYS
#### Useful for: 
Storing and accessing sequential data, temporarily storing, as an IO buffer
(when reading from a file), lookup table, and hack for multiple return values.

#### Notes: 
Can implement a *dynamic array* from static ones by continuously allocating double the space
once the array is full.

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Access      | O(1)        | O(1)        |
| Append      | ---         | O(1)        | scales well
| Insert      | ---         | O(n)        | if insert to front, have to shove everything over
| Remove      | ---         | O(n)        | to remove an item, create new array and copy over vals to keep
| Search      | O(n)        | O(n)        |

---

### :pushpin: LINKED-LISTS
#### Useful for: 
Useful in lists, queues, and stacks. Often used for circular (round robin) or adjacency lists.

#### Notes: 
Singly-linked will save up on space and it's simpler to implement but it can make it more difficult to access previous nodes.
Doubly-linked takes up ***double*** the space since we have 2x the pointers but easier to traverse backwards.

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Insert (T/H)| O(1)        | O(1)        | for inserting at the head or tail
| Insert      | O(n)        | O(n)        | for items in the middle, need to traverse
| Remove      | O(n)        | O(n)        | 
| Search      | O(n)        | O(n)        |

---

### :pushpin: STACKS
#### Useful for: 
Useful for undo functions, checking for matching braces, other syntax (or TMs), supports recursion 
behind the scenes, and is used in DFS on a graph.

#### Notes: 
Has 2 primary operations: *push* and *pop*. **Last in, first out**: what you most recently pushed will be
what comes out when you pop.

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Push        | O(1)        | O(1)        | 
| Pop         | O(1)        | O(1)        | 
| Peek/Top    | O(1)        | O(1)        | 
| Search      | O(n)        | O(n)        | scan all elements if not on top

---

### :pushpin: QUEUES
#### Useful for: 
Used to model a real-world queue like standing in line, a sequence of elements, web server 
manager for first come, first serve, or BFS graph traversal.

#### Notes: 
It's a linear data structure with has 2 main operations: *dequeue* ("polling") and *enqueue* ("offering"). 
You **remove** elements from the **front** and add elements to the back. Often done via singly-linked list since
arrays (static) might not be big enough.

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Enqueue     | O(1)        | O(1)        | 
| Dequeue     | O(1)        | O(1)        | 
| Peek/Top    | O(1)        | O(1)        | 
| Contains    | O(n)        | O(n)        | might need to scan thru all elements
| Remove      | O(n)        | O(n)        |

---

### :pushpin: HASH MAP
#### Useful for: 
Helpful for tracking item frequencies, if large files have equal contents (without opening files), 

#### Notes: 
Provides a mapping from keys to values via hashing (called a *"key-value" pair* where keys are unique). 
Keys are immutable.

#### Collision Resolution Methods:
1. **Open Addressing:** Find another place within hash table by using an offset from original hash.

2. **Separate Chaining:** Use a separate data structure like a list to hold all different values (key-value pairs).

#### Time Complexity:
| Operation   | Average     | Worst       | 
| ----------- | ----------- | ----------- |
| Lookup      | O(1)        | O(n)        | lots of hash collisions
| Remove      | O(1)        | O(n)        | 
| Insert      | O(1)        | O(n)        | 

![LN](line.png)

## Programming Languages
* C: Procedural-oriented language; no references (just pointers), no function overloading, + memory management.
  * **Basic ex:** 
  ```c
     #include <stdio.h>
     int main() {
       printf(“Hello World!”);
       return 0;
     } 
  ```
  * **To Run:** `gcc -o hi Helloworld.c` then run `hi`
* C++: Object-oriented language; references, pointers, function overloading + memory management.
  * **Basic ex:** 
  ```c++
     #include <stdio.h>
     int main() {
       cout << "Hello World!" << endl;
       return 0;
     }
  ```
  * **To Run:** `g++ -o hi Helloworld.c` then run `./hi`
  * **Tip**: to avoid having to write "std:" constantly, use `using namespace std;`
* Python: Object-oriented/scripting language; pointers, function overloading + automatic garbage collection.
  * **Basic ex:** 
  ```python
     def hello():
       print("Hello World!")
     hello()
  ```
  * **To Run:** `python Helloworld.c`
  * **Tip**: use [Tensorflow](https://www.tensorflow.org/)/[Keras](https://keras.io/) if you need general ML models like regression, 
  PCA, Decision Trees, KNN, SVM, etc.
    * To use these packages, treat them the same as any other import: `import tensorflow as tf`
* Java: Object-oriented language; references, method overloading + automatic garbage collection.
  * **Basic ex:**
  ```java
     public class HelloWorld {
       public static void main (String[] args) {
	        System.out.println ("Hello World!");
       }
     }
  ```
  * **To Run:** compile with `javac Helloworld.java` then run `java Helloworld`
  * **Tip**: know the difference between abstact classes and interfaces

![LN](line.png)

## Sorting Algorithms

### :pushpin: [INSERTION SORT](https://www.interviewcake.com/concept/java/insertion-sort)
#### Useful for: 
Small dataset and partially sorted.
#### Time Complexity:
| Best        | Average     | Worst       | Space       | 
| ----------- | ----------- | ----------- | ----------- |
| O(n)        | O(n^2)      | O(n^2)      | O(1)        | 

---

### :pushpin: [SELECTION SORT](https://www.interviewcake.com/concept/java/selection-sort)
#### Useful for: 
Small dataset and partially sorted.
#### Time Complexity:
| Best        | Average     | Worst       | Space       | 
| ----------- | ----------- | ----------- | ----------- |
| O(n^2)      | O(n^2)      | O(n^2)      | O(1)        | 

---

### :pushpin: [MERGE SORT](https://www.interviewcake.com/concept/java/merge-sort)
#### Useful for: 
Ideal for combining lists.
#### Time Complexity:
| Best        | Average     | Worst       | Space       | 
| ----------- | ----------- | ----------- | ----------- |
| O(nlogn)    | O(nlogn)    | O(nlogn)    | O(n)        | 

---

### :pushpin: [QUICK SORT](https://www.interviewcake.com/concept/java/quicksort)
#### Useful for: 
...
#### Time Complexity:
| Best        | Average     | Worst       | Space       | 
| ----------- | ----------- | ----------- | ----------- |
| O(nlogn)    | O(nlogn)    | O(n^2)      | O(logn)     | 

---

### :pushpin: [HEAP SORT](https://www.interviewcake.com/concept/java/heapsort)
#### Useful for: 
Can be chosen over quick sort because, in the case of a partially sorted array, it's worst case will always be O(nlogn) not O(n^2).
#### Time Complexity:
| Best        | Average     | Worst       | Space       | 
| ----------- | ----------- | ----------- | ----------- |
| O(n)        | O(nlogn)    | O(nlogn)    | O(1)        | 

![LN](line.png)


## How to Prepare
- [x] Review major data structures
- [ ] Review your resume and be able to discuss all previous work experience/research/projects 
- [ ] Review sorting algorithms
- [ ] Practice LeetCode/HackerRank
- [ ] Run through common behavioral questions
- [ ] Practice adding comments to your code like:
```c++
/**
 * Insertion Sort
 * Starting from left to right, select current number and if it's smaller than previous ones, keep moving it over to the left 
 */ 
int* insertion_sort(int arr[]) {}
```

![LN](line.png)

## Other Notes
#### BFS Graph:
~~Start at a node, add its neighbors to queue, and visit their neighbors (add to queue).~~
We know if all nodes have been visited by marking them as visited (bool).

---

#### Common Questions:
> How would you make this more efficient? (general)

> Is there a better data structure to use? (general)

> Find the longest nonrepeating/even/odd/etc substring. (Google/Amazon)

> Determine if the string is an anagram or palindrome. (Amazon)

> Count all the leaf nodes. Count all the nodes in a level. Count all the nodes with one child. (Uber)

> When you square a list of numbers, how would you resort them in ascending order? (Uber)

![foot](footer.png)
