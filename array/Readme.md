# Array

Array is a data structure that represents the collection of the same
type data, such as a 32-bit integer. Array provides methods to access,
add, or remove elements. An element of an array is specified with a
non-negative index. Index *n* indicates *n-th* element of an array.

The data collection of an array is stored in a single sequencial
and contiguous address space in memory. The data is filled from the
beginning of the memory space. Index of an array starts from zero in
general. Index zero indicates the beginning of the contiguous memory
space. Each element has the same length (byte), so computing an address
of *n-th* element is fast. Therefore accessing an element of an array
is very fast.

An array keeps track of the number of elements it contains. An array
may throw an exception for an access to an element that exceeds the
element counter.

Adding an element to the end of an array is fast because the address of
the new element can be calculated quickly, the *count-th* element is the
location where the new data will be added. The new data is stored
there, and then the counter is incremented.

Removing an element from the end of an array is also fast. The element
that is removed is the *(count - 1)-th* element. The data of the removed
element is cleared, and then the counter is decreased. Even the data
may not need to be cleared because the removed element won't be accessible
due to the out of bounds. And the data will be overridden when a new
element will be added.

Conversely, inserting or removing an element somewhere else is slow
because all the elements after the instered or removed elements need to
shift.

Merging arrays is also slow because elements need to be copied.

## Dynamic Array

Basic array is fixed size. The capacity of an array is defined when
it is created. If you attempt to add more elements than the capacity
the array may throw an exception.

Dynamic Array is an advanced array data structure that resolves this
limitation. It automatically extends the capacity when reaching the
capacity.

It allocates a new memory space that is bigger than the current one,
for example doubled size, and then copies the elements. So is is slow.

This capacity extension happens when attempting to add a new element.
Adding a new element is fast (O(1)) but if this extension happens
it will be slow (O(n)).

## Methods and speed (complexity)

T.B.D.

### new(capacity) : O(1)

### get(index) : O(1)

### push(data) : O(1) or O(n)

### pop() : O(1)

### size() : O(1)

### capacity() : O(1)

### insert(index, data) : O(n)

### remove(index) : O(n)

### find(data) : O(n)

### resize(new_capacity) : O(n)

## Ring buffer approach

T.B.D.
