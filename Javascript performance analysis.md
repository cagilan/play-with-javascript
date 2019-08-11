https://medium.com/hackernoon/3-javascript-performance-mistakes-you-should-stop-doing-ebf84b9de951

1. Looping over an Array:
--------------------------

Sum an array.

Comparison of summing random 10k items using for, for-of, while, forEach and reduce.

For loop, average 10 ms
For-of, 110ms
ForEach, 77ms
while, 11 ms
Reduce, 113ms

For loop provides the best performance 10x better

*Reduce and for-of requries a callback function to be executed which is called recursively.

2. Duplicate any array:
------------------------

Slice, average 367ms
Map, average 469ms
Spread, average 512ms
Conct, average 366ms
Array From, average 1436 
manually, average 412ms

3. Iterating Objects:
----------------------

Object iterate For-In, average 240ms
For Each, 294 ms
For-Of, 535ms

The cause is creating of enumerable arrays of values, instead of traversing the object directly.

Conclusion:
----------------

If key of applicaiton is fast performance or small project, more readable, cleaner.



