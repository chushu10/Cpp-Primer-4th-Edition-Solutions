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