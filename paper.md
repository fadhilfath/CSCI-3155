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
from blist import blist
items = blist([5, 6, 2])
more_items = blist(function_that_returns_a_list())
```
Different from implementing array list, we need to pass a value in the type of list as a parameter for initializing the BList. The way to use BList is similar to array list, it offers same interface as what we familiar with array list. These are codes for using BList:
```
from blist import *
x = blist([0])             # x is a blist with one element
x *= 2**29                 # x is a blist with > 500 million elements
x.append(5)                # append 5 to x
y = x[4:-234234]           # Take a 500 million element slice from x
del x[3:1024]              # Delete a few thousand elements from x
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

### - Reasons for Rejection ###

BList was rejected by the Python developer community for many reasons, but mostly because it wasn't user-friendly enough.  Raymond Hettinger, one of Python's core developers, had this to say about BList:

> “There is too much value in a simple C API, low space overhead for small lists, good performance [in] common use cases, and having performance that is easily understood.  The BList implementation lacks these virtues and it trades-off a little performance in common cases ... for much better performance in uncommon cases.”

Hettinger therefore points out four primary reasons why BList does not belong in the native Python library:  First, the standard array-based List utilizes a much simpler API than BList, so adopting BList would create unnecessary complexity in their code base and would likely require extensive debugging.  Second, array-based Lists require less physical memory than BLists for smaller numbers of elements.  Third, array-based Lists perform just as well as BLists for lists containing less than 100 elements, which is the most common use case.  Finally, the B+tree data structure used by BList is much more difficult for users to understand than the simple array structure used by List.

These are certainly important issues that need to be taken under consideration.  However, Hettinger's comments reveal something about the motivation behind the Python programming language itself -- it is more important for code to be user-friendly than to have powerful performance.

### - Relation to Topics Learned in the Course ###

Throughout this course, we have been progressively implementing a custom programming language called JavaScripty.  It started off simply, with a syntax interpreter capable of understanding basic mathematical and logical operations.  We then implemented a method that allowed us to declare constant variables, as well as a binary search tree to store these variables so that they could be called later.  Later, we implemented partial functions that were able to be called by the interpreter, replacing variables either by substitution or by looking up their values in the variable environment.  By the end of the course, our JavaScripty language was capable of specifying the mutability of variables, specifying the return type of functions, and casting values from one type to another.

The evolution of JavaScripty allowed it to become much more powerful and capable of performing a wide range of functions, but at the cost of increased complexity.  Historically, the computer science community has seemed to welcome this sort of evolution in programming languages.  More powerful code has seemed to always win out over simpler code.  However, today we are seeing a resurgence of simplicity.  It seems as if programmers have come to the realization that modern students of computer science do not have the extensive experience that is required to understand today's complicated libraries and code bases, and that there is a need for a simpler & more elegant language to soften the learning curve.  Python appears to be one of the languages at the forefront of this movement, and their rejection of BList is a perfect example of their commitment to this purpose.

### - Conclusion ###

While the Python developer community's reasons for rejecting BList make perfect sense, it does not necessarily need to be the last nail in the coffin.  There are ways of altering BList so that it maintains its powerful performance without sacrificing usability.  For example, the API that controls BList methods could be rewritten to fall more in line with that of the current array-based List, allowing it to become much more compatible with the rest of the native Python library.  If the B+tree structure were also simplified or explained in a more easily-understandible way, the learning curve would be reduced to nearly zero.  The higher amount of memory required by small BLists could also be made more efficient, but with the near-exponential growth of storage capacity on modern hard drives, this may become unnecessary.  The most important thing that could be done to save BList, however, is to simply use it.  It is currently available as a third-party extension to Python, but we are confident that if the number of programmers who use it increases, it may yet become a native Python type.
