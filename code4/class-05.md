## Linked Lists

The LinkedList class is a collection which can contain many objects of the same type.
The LinkedList stores its items in "containers." The list has a link to the first container and each container has a link to the next container in the list. To add an element to the list, the element is placed into a new container and that container is linked to one of the other containers in the list.

A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

Linked Lists types:
1. Singly (refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list).
2. Doubly (refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node).

* next: the reference to the next node.
* Head: reference of type Node to the first node in a linked list.
* current: reference of type Node to the node that is currently being looked at.

### Array List vs Linked List:

- Array List takes much than linked list.
- if we want to delete from the middile of the array, array list needs to shift all next elements to the deleted elements while in linked list it just changed the pointer so it takes less time for implementation for short arrays.


