[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=13004583&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

**- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.**
    1.	The first thing that comes to mind for me is the fact that constants are ignored. This makes sense when working with very large numbers of data as it will not affect much, but input size can make the actual performance vary. Even a simple constant function can make the time longer if the input size is right. 
    2.	Another obvious, yet important one could be the performance of the machine used. Even on the same machine, no two input times will be identical because many operations are happening on a computer. So of course, time will vary from different machines. Programming languages also compile various operations differently, especially moving from something like java to assembly. Small changes can make a huge difference in the runtime of an algorithm.
    3.	Different operation executions can also change the time. Depending how the program was written/organized could increase or decrease the runtime. An obvious example would be using a nested loop when it could be done in a much more efficient way.


**- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.**
    We know that, in general, a BST has a runtime of O(log<sub>2</sub>n) (in the most common case) which represents the height of the tree. When searching through 1000 elements, of course, no two runtimes will be the exact same. That said, we can generalize and get a rough idea of what it should be as we do in asymptotic analysis. We know that with O(logn), as input size increases exponentially, the time will increase linearly. This would mean that  1000x=10000 or x = log1000(10000) where x = 1.33333. So, if it took 5 seconds to search 1000 elements, we can guess that it will take a little under 7 seconds to compute 10000 elements. T(n) <= c log2n or 5sec = c log21000 where c can be found, as well as x = c log<sub>2</sub>10000 should result in 6 2/3 seconds, roughly. Linearly of course would be 10x as long (50 seconds).


**- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.**
    1.	There is some unknown operation it does that takes much longer to execute than the typical BST. This could be something like checking every node rather than utilizing the BST structure (with some, much slower type of search) or doing an additional operation like deleting/adding nodes or performing an operation as you search. These are the constant values we ignore when finding the runtime of an algorithm.
    2.	Another reason (and most likely) could be that the binary search tree is skewed to one side or another, for example, the right side of the tree has many more elements than the left side(all nodes are larger than start node). This would increase the height and path it needs to take to find an element and thus, increase the complexity and time of the algorithm (O(n) depending on the desired node).
    3.	One more reason, but certainly not the last, could be that the program is poorly written. This could mean it has to search many times to find the desired node or go through some other function(s) to see if the current node matches. This could increase the runtime of the algorithm.


Nicholas Matter, Assignment 2, 1 November 2022
  >Corrected version
