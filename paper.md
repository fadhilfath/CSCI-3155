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



