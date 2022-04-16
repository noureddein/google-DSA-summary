# Linked Lists

## What is linked lists?

- Linked lists can be similar to paper chain.
- Linked lists is an extension of lists, but it is not an array.
- It have an order but without indices.
- Linked lists characterized by there links.
- Each element in the linked list will told you what is the next element.

## How to implement linked lists?

- To implement a linked list we need a constructor to create the single unit of linked list:
  - This constructor will have two attributes **value** and **next**
    - **value**: will be hold the value which can be any type of data.
    - **next**: will reference to the next unit of the linked lists, actually the next value represent the location of the next unit in memory.

```python
    class Element:
        def __init__(self, value):
            self.value = value
            self.next = None
```

- Now, to implement the linked list, we need a constructor to linked each unit together
  - The constructor will have an attribute called head, which represent the first element in the linked list.

```python
    class LinkedList:
        def __init__(self, head=None):
            self.head = head
```

- Now, we need a method to add a new unit to the end of the linked list
  - This method will loop through the units, until it reach the last unit that reference to a None value

```python
    def append(self, new_element):
        current = self.head
        if self.head:
            while current.next:
                current = current.next
            current.next = new_element
        else:
            self.head = new_element
```
