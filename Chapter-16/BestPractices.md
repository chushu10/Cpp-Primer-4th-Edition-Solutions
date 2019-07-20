# Best Practices

- Inside the scope of a class template, we may refer to the class using its unqualified name.
  
    ```cpp
    template <class Type> class QueueItem {
    // private class: no public section
        QueueItem(const Type &t): item(t), next(0) { }
        Type item; // value stored in this element
        QueueItem *next; // pointer to next element in the Queue, we can refer to the class using its unqualified name.
    };
    ```

- ...
