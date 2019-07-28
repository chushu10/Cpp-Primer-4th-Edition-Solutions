# Exercise 16.32

Implement the assignment operator for class `Queue`.

**Answer**:

```cpp
#include <iostream>
using namespace std;

template <class Type> class Queue;

template <class Type> class QueueItem {
    friend class Queue<Type>;
// private class: no public section
    QueueItem(const Type &t): item(t), next(0) { }
    Type item;       // value stored in this element
    QueueItem *next; // pointer to next element in the Queue
};

template <class Type> class Queue {
public:
    // empty Queue
    Queue(): head(0), tail(0) { }
    // copy control to manage pointers to QueueItems in the Queue
    Queue(const Queue &Q): head(0), tail(0) { copy_elems(Q); }
    Queue& operator=(const Queue&);
    ~Queue() { destroy(); }
    // return element from head of Queue
    // unchecked operation: front on an empty Queue is undefined
    Type& front() { return head->item; }
    const Type &front() const { return head->item; }
    void push(const Type &);
    void pop ();
    bool empty () const { return head == 0; }
    void display_elems();
private:
    QueueItem<Type> *head;
    QueueItem<Type> *tail;
    // utility functions used by copy constructor, assignment, and destructor
    void destroy();
    void copy_elems(const Queue&);
};

template <class Type> void Queue<Type>::destroy()
{
    while (!empty()) {
        pop();
    }
}

template <class Type> void Queue<Type>::pop()
{
    // pop is unchecked: Popping off an empty Queue is undefined
    QueueItem<Type>* p = head; // keep pointer to head so we can delete it
    head = head->next;         // head now points to next element
    delete p;                  // delete old head element
}

template <class Type> void Queue<Type>::push(const Type &val)
{
    // allocate a new QueueItem object
    QueueItem<Type> *pt = new QueueItem<Type>(val);
    // put item onto existing queue
    if (empty()) {
        head = tail = pt; // the queue now has only one element
    } else {
        tail->next = pt;  // add new element to end of the queue
        tail = pt;
    }
}

template <class Type>
void Queue<Type>::copy_elems(const Queue &orig)
{
    // copy elements from orig into this Queue
    // loop stops when pt == 0, which happens when we reach orig.tail
    for (QueueItem<Type> *pt = orig.head; pt; pt = pt->next) {
        push(pt->item); // copy the element
    }
}

template <class Type>
Queue<Type>& Queue<Type>::operator=(const Queue &orig)
{
    copy_elems(orig);
    return *this;
}

template <class Type> void Queue<Type>::display_elems()
{
    for (QueueItem<Type> *pt = head; pt; pt = pt->next) {
        cout << pt->item << " ";
    }
    cout << endl;
}

int main()
{
    Queue<int> queue;
    queue.push(1);
    queue.push(2);
    queue.push(3);
    Queue<int> queue2(queue);
    Queue<int> queue3 = queue2;
    queue.display_elems();
    queue2.display_elems();
    queue3.display_elems();
    return 0;
}
```
