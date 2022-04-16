# What is collections?
  - Collections is a mixed of things that the order does not make that huge difference.
  - Collections doesn't need to have the same type of object.

## Lists 
  - Lists has all the property of a collection.
  - So it can have a group of things but the objects have an order.
  

## Arrays
  - Arrays is a list with a few added rules, so we have some things in some order.
  - The big feature that differentiates arrays from lists is array has a location called **index**.
  - Index is just a number associated with that place in the array.
    - For example [3, 2, 8, 16, 12] ==> **3** has index of **0**, **2** has index of **1**
      - 3  ==> 0
      - 2  ==> 1
      - 8  ==> 2
      - 16 ==> 3
      - 12 ==> 4
    - operations with arrays are really messy:
      - Insertion in the end can be easy, but it can be hard if the array has a set size and you have already filled it up.
      - Insertion at the middle is difficult, because we need to move all the elements after the inserted element back into a different indices
      - Deletion causes a similar problem, because we will have an empty index after deletion, so we need forward back all the elements with one step to the back, then all the elements after the deleted element will have an index of (index - 1)


## Difference between array and lists

| List | Array |
| ----------- | ----------- |
| Can consist of elements belonging to different data types	 | Only consists of elements belonging to the same data type|
| No need to explicitly import a module for declaration	 | Need to explicitly import a module for declaration|
| Cannot directly handle arithmetic operations | Can directly handle arithmetic operations|
| Can be nested to contain different type of elements | Must contain either all nested elements of same size|
| Preferred for shorter sequence of data items | Preferred for longer sequence of data items|
| Greater flexibility allows easy modification (addition, deletion) of data	 | Less flexibility since addition, deletion has to be done element wise|
| The entire list can be printed without any explicit looping | A loop has to be formed to print or access the components of array |
| Consume larger memory for easy addition of elements | Comparatively more compact in memory size |
|[Source](https://www.geeksforgeeks.org/difference-between-list-and-array-in-python/)|