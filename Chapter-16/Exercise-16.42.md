# Exercise 16.42

Write an input operator that reads an `istream` and puts the values it reads into a `Queue`.

**Answer**:

```cpp
#include <iostream>

template <class Type> class Queue;
template <class T> std::ostream& operator<<(std::ostream&, const Queue<T>&);
template <class T> std::istream& operator>>(std::istream&, const Queue<T>&);

template <class Type> class QueueItem {
    friend class Queue<Type>;
    friend std::ostream& operator<< <Type> (std::ostream&, const Queue<Type>&);
// private class: no public section
    QueueItem(const Type &t): item(t), next(0) { }
    Type item;       // value stored in this element
    QueueItem *next; // pointer to next element in the Queue
};

template <class Type> class Queue {
    friend std::ostream& operator<< <Type> (std::ostream&, const Queue<Type>&);
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
    void pop();
    bool empty() const { return head == 0; }
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
    QueueItem<Type> *p = head; // keep pointer to head so we can delete it
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
std::ostream& operator<<(std::ostream &os, const Queue<Type> &q)
{
    os << "< ";
    QueueItem<Type> *p;
    for (p = q.head; p; p = p->next) {
        os << p->item << " ";
    }
    os << ">";
    return os;
}

template <class Type>
std::istream& operator>>(std::istream &is, Queue<Type> &q)
{
    Type elem;
    Queue<Type> temp;

    while (is >> elem) {
        temp.push(elem);
    }

    q = temp;

    return is;
}

template <class Type>
Queue<Type>& Queue<Type>::operator=(const Queue &orig)
{
    copy_elems(orig);
    return *this;
}

int main()
{
    Queue<int> queue;
    queue.push(1);
    queue.push(2);
    queue.push(3);
    Queue<int> queue2(queue);
    Queue<int> queue3 = queue2;
    std::cout << queue << std::endl;
    std::cout << queue2 << std::endl;
    std::cout << queue3 << std::endl;
    std::cin >> queue;
    std::cout << queue << std::endl;
    return 0;
}
```
