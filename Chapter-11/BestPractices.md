# Best Practices

- The call to `find` takes two iterators and a value, as soon as it sees an element that is equal to the given value, `find` returns an iterator referring to that element. If there is no match, then find returns its **second iterator** to indicate failure.
    ```cpp
    // example
    vector<int>::const_iterator result =
        find(vec.begin(), vec.end(), search_value);
    // if there is no match, find returns the second iterator, which is vec.end()
    ```
- The job of generic algorithm `find` is to find a particular element in an **unsorted** collection of elements.
- The element addressed by the second iterator, sometimes referred to as the **off-the-end iterator**, is not itself examined; it serves as a sentinel to terminate the traversal.
- Algorithms never directly change the size of a container. If we want to add or remove elements, we must use a container operation.
- When dealing with the algorithms, it is best to think of the iterators on associative containers as if they were input iterators that also support decrement, not as full bidirectional iterators.
- Errors in passing an invalid category of iterator to an algorithm are **not guaranteed to be caught at compile-time**.