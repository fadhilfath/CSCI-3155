## Python BList ##
**Fadhil Suhendi**
**Zhilli Yang**
**Thomas Kelly**

### - What is “BList” ? ###

Python introduced the new data structure in 2007. This new data structure is called “BList”, with the purpose of replacing current data structure in python, which is List. BList has array-based and tree-based aspects. The idea of creating BList is that we want to have a data structure that performs better, and faster in the larger set of data. Unlike Array-based list, deleting and inserting array take O(n) times in worst case scenario. And this becomes problematic when it comes to the large set of an array. The BList in this PEP is based on the principle of B+tree. 

Based on the proposal of BList, BList is aimed to replace List data structure. However, there are some cases in which list outperforms the BList. First of all, it is on the LIFO stack, and a large unchanging list. And also the only time where list faster is when it has small list. According to Raymond Hettinger as a python developer, in some of the uncommon cases BList take an important role on performing better compare to List. However, in some of the common cases in data structure, BList has a little performance. And this is one of the reasons why BList python was rejected in the community. There are pros and cons that talks a lot on this PEP from the performance, and user interface. Even though it was rejected, we still can use this powerful data structure as an library extension for python programming language. 


### -Why is BList useful? ###

Python developer will be familiar with the concept of List data structure in python programming language. Often times we want to use list for inserting, deleting, and copying data. Although list is commonly used for storing data, and it is one of the standard of python data structure, there are some of the lacking aspects of using list in terms of performance. If we take a look at the worst case performance of list, it takes O(n) for inserting and copying. This performance will be good on the short amount of data. However, let say that we have large amount of data on the array, and want to manipulate the data by inserting a new data. This will be painful to perform. Since it takes a linear time, it will be really slow to check every element on the array. 

Here is come the benefits of BList in python programming language. BList’s performance will works better on some of the important cases, such as copying, and inserting a data. The algorithm of BList takes O(log n) for inserting, and O(1) for copying. If we compare to the algorithm of List, list takes O(n) for inserting, which is not efficient. Since BList is based on the B+tree, which we are going to cover more about B+tree on this paper. BList is also offering asymptotic performance. However, list and BList have the common performance on the smaller sets of data. BList data structure will be more useful for large input of data. 


### -Implementation of BList & the data structure B+tree ###

Although BList has been rejected, it is still released as an extension module of Python language. Therefore, the programmers could download the library online and import it when then need. There are some implementation codes for BList:
```
>>> from blist import blist
>>> items = blist([5, 6, 2])
>>> more_items = blist(function_that_returns_a_list())
```
Different from implementing array list, we need to pass a value in the type of list as a parameter for initializing the BList. The way to use BList is similar to array list, it offers same interface as what we familiar with array list. These are codes for using BList:
```
>>> from blist import *
>>> x = blist([0])             # x is a blist with one element
>>> x *= 2**29                 # x is a blist with > 500 million elements
>>> x.append(5)                # append to x
>>> y = x[4:-234234]           # Take a 500 million element slice from x
>>> del x[3:1024]              # Delete a few thousand elements from x
```

As what we mentioned above, BList is a data structure based on B+tree. The reason why is B+tree owns some features unique.
It is an N-ary tree, which means each node could have more than two children. But different from B-tree, internal nodes of B+tree have no data, they only contain the keys and the pointers to next level. All data are stored in the leaves.
The other special feature is all leaves of B+tree are in the same level, which means B+tree is always balance. And all leaves nodes are linked, therefore doing a full scan in a tree requires just one linear pass through all leaves.

### -Pros and Cons ###

Everything could be double-edge sword, so as BList. 
As what we mentioned in Implementation, the interface of BList tree is similar to array list, which could reduce the time a beginner spends on getting familiar with  the library.
The performance of BList with a large number of elements is better than the array-based list. The reason why is the data structure, which has array-like and tree-like aspects. 

“A wide variety of data structure provide good asymptotic performance for insertions and deletions, but they either have O(n) performance for other operations (e.g., linked lists) or have inferior performance for small lists (e.g., binary trees and skip lists).” Therefore, BList might not perform as well as regular list in small amount of elements.
Adding BList to Python’s default library may have an impact on extension modules, requiring extensive debugging. Performance & desirability in real-world applications has yet to be proven -- more testing is required.
Finally, increasing the number of data types available to developers makes  their job more difficult. It seems one of the most important reasons that why BList got rejected. The users prefer more friendly over more powerful code.
As we can see, although BList owns a powerful performance, it also owns disadvantages which prevent it from being accepted. As future developers, we also need to pay attention on user friendly but not just on efficiency.