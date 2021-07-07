## Read: Stacks & Queues

### Stacks

A stack is a data structure that consists of Nodes. Each Node references the next Node in the stack, but does not reference its previous.

#### to insert node or items: **push()**
to push a specific node to the head for example; we need to set a refrence for the new node to the next of the head and a refrence to the next of next head.

#### to remove operation: **pop()**
Popping a Node off a stack is the action of removing a Node from the top. When conducting a pop, the top Node will be re-assigned to the Node that lives below and the top Node is returned to the user.

- the top of the stack: **Top**

#### view the value of the top Node in the stack: **peek**
When conducting a peek, you will only be inspecting the top Node of the stack.

#### IsEmpty O(1)
returns true when stack is empty otherwise returns false.


### Stack concepts: 

1. FILO (First In Last Out):the first item added in the stack will be the last item popped out of the stack.
2. LIFO (Last In First Out): last item added to the stack will be the first item popped out of the stack.

***

### Queue

Queue is a linear structure which follows a particular order in which the operations are performed.

#### To add Items: Enqueue O(1)

#### To remove Items: Dequeue O(1)

#### Peek O(1)
When conducting a peek, you will only be inspecting the front Node of the queue.

#### IsEmpty O(1)
same as in stacks


### Queue concepts: 
1. FIFO (First In First Out):  the first item in the queue will be the first item out of the queue.
2. LILO: (Last In Last Out): the last item in the queue will be the last item out of the queue.


***

### Stacks VS Queue

* Stack A stack is a linear data structure in which elements can be inserted and deleted only from one side of the list, called the top. 
* Queue: A queue is a linear data structure in which elements can be inserted only from one side of the list called rear, and the elements can be deleted only from the other side called the front.

