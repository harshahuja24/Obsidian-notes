
| Data Structure           | Inserting | Delete | Access                                                                                 | Searching                | Traversing |
| ------------------------ | --------- | ------ | -------------------------------------------------------------------------------------- | ------------------------ | ---------- |
| Arrays                   | n         | n      | 1(indexing)                                                                            | n                        | n          |
| Lists                    | n         | n      | 1                                                                                      | n                        | n          |
| Queue                    | 1         | 1      | 1                                                                                      | n                        | n          |
| Stack                    | 1         | 1      | 1(peek)                                                                                | n                        | n          |
| Set                      | 1         | 1      | cannot                                                                                 | 1                        | n          |
| Map                      | 1         | 1      | cannot in keys<br>can in values. 1                                                     | 1 in keys<br>n in values | n          |
| LinkedList               | n         | n      | n                                                                                      | n                        | n          |
| Trees                    | TODO      |        |                                                                                        |                          | n          |
| Graphs                   | TODO      |        |                                                                                        |                          | n          |
| Priority Queue<br>Heap!! | logN      | logN   | 1 to direct access<br>the Root node <br>Which can be Changed<br>acc to min or max prio | n                        |            |
### Arrays :
having indexing, continous memory location, same data type,
### Lists:
dynamic memory allocation, no fixed size is to be informed before, can store various data types
### Queue:
Follows FIFO, knows only first element in empty queue agar zabardasti then pop and store again ie poora queue traversal.
### Stack:
Can only be interted in the top of the element , Follows LIFO, searching poora traversal,
### Set:
unordered, stores unique value, hashing hote hai , cannot store any value, hashing is done by setting the available bit 0 or 1 and hence hashing has constant time operations the values wont be stored in an order 
### Map:
is a combo of key value pair, has hash, is undordered , to search for keys constant time operation but for values poora map ke keys ko puchna padega is your key the key i am looking for? if key updated value will be overriden.
### LinkedList:
Start ka reference hai o(n) but if i have end O(1) is possible, cannot do binary search in linkedlist because we dont have the option of indexing and accessing the value of mid
### Priority Queue:
We have a special type of priority queue which is also known as heap data structure. a type of queue that does not follow a fifo it depends on your max prio queue or min prio queue
Insertion Log(N) and same in deletetion because of shuffling, maintaines sorting keeps order acc to the min or max prio internally works as a tree where the min/max is the root and rest are followed along 

>  *ArrayList vs vector the main difference is where only one thread is allowed to access the vector while in ArrayList multiple threads are allowed to change the values!!!*

