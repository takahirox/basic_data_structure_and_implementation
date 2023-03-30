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

### new(capacity) : O(1)

Generates a new Array data with allocated memory.

### get(index) : O(1)

Returns the value of an slement at specified location.

### set(index, value) : O(1)

Update the value of an element at specified location.

### push(value) : O(1) or O(n)

Adds an element with value to end. Dynamic Array may extend capacity
if the number of elements reaches a threashold. See resize().

The speed depends on whether resize happens. O(1) in general, but
O(n) with resize.

### pop() : O(1) or O(n)

Removes an element from end and returns the value of it. Dynamic
array may downsize the capacity if the number of elements becomes
under a threashold. See resize().

The speed depends on whether resize happens. O(1) in general, but
O(n) with resize.

### size() : O(1)

Returns the number of items.

### capacity() : O(1)

Returns the number of items the array can hold.

### insert(index, value) : O(n)

Inserts a new elements with value at specified location. The elements
after it will be shifted. Dynamic Array may extend capacity if the
number of elements reaches a threashold. See resize().

### remove(index) : O(n)

Removes an element from speicfied location. The elements after it
will be shifted.

### find(value) : O(n)

Finds a first element whose value matches the specified value by
traversing all the elements, and returns the index of it. It may
return -1 if not found.

### resize(new_capacity) : O(n)

Resizes the capacity by allocating a new memory space, copying
elements to the new space, and releasing the old memory space.

## Ring buffer approach

With Ring buffer approach, adding or removing an element from the
start can be O(1). See [Queue](../../queue/Readme.md) for the details.
