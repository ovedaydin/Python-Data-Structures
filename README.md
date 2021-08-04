# Python-Data-Structures

## List
General Purpose

Most widely used data structure

Grow and shrink size as needed

Sequence type

Sortable

## Tuple
Immutable (can't add/change)

useful for fixed data

Faster than lists

sequence type

## Set
Store non-duplicate items

Very fast access vs Lists

Math Set ops (union, intersect)

Unordered

## Dict
Key/Value pairs

Associative array, like Java Hashmap

Unordered


# How does python work with memory

Most of Python’s memory management is done by the Python Memory Manager

### Static Memory Allocation

C/C++

static int a=10;

In this case, memory can not be reused.

### Dynamic Memory Allocation

C/C++

int *p;

p=new int;

Heap is used for implementing dynamic allocation. In this case, memory can be freed and reused when not required.



The good thing about Python is that everything in Python is an object. This means that Dynamic Memory Allocation underlies Python Memory Management. When objects are no longer needed, the Python Memory Manager will automatically reclaim memory from them.


The Python memory manager manages Python’s memory allocations. There’s a private heap that contains all Python objects and data structures. The Python memory manager manages the Python heap on demand. The Python memory manager has object-specific allocators to allocate memory distinctly for specific objects such as int, string, etc… 


Below that, the raw memory allocator interacts with the memory manager of the operating system to ensure that there’s space on the private heap.

The Python memory manager manages chunks of memory called “Blocks”. A collection of blocks of the same size makes up the “Pool”. Pools are created on Arenas, chunks of 256kB memory allocated on heap=64 pools. If the objects get destroyed, the memory manager fills this space with a new object of the same size.

Objects and instance variables are created in Heap memory. As soon as the variables and functions are returned, dead objects will be garbage collected.

It is important to note that the Python memory manager doesn’t necessarily release the memory back to the Operating System, instead memory is returned back to the python interpreter. Python has a small objects allocator that keeps memory allocated for further use. In long-running processes, you may have an incremental reserve of unused memory.


