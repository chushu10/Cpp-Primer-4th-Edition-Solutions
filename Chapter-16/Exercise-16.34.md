# Exercise 16.34

Write the member function definitions of the `List` class that you defined for the exercises in Section 16.1.2 (p. 628).

**Answer**:

```cpp
#include <iostream>
using namespace std;

template <class Type> class List;

template <class Type> class ListItem {
    friend class List<Type>;
    ListItem(const Type &t): item(t), prev(0), next(0) { }
    Type item;
    ListItem *prev;
    ListItem *next;
};

template <class Type> class List {
public:
    List(): head(0), tail(0) {}          // default constructor
    List(const List &L): head(0), tail(0) { copy_elems(L); }
    List& operator=(const List&);
    ~List() { destroy(); }
    Type &front() { return head->item; }
    Type &back() { return tail->item; }
    const Type &front () const { return head->item; }
    const Type &back () const { return tail->item; }
    void push_back(const Type &);
    void pop_back();
    bool empty() const {return tail == 0; }
    void display_elems();
private:
    ListItem<Type> *head;
    ListItem<Type> *tail;
    void destroy();
    void copy_elems(const List&);
};

template <class Type> void List<Type>::pop_back()
{
    ListItem<Type> *p = tail;
    tail = tail->prev;
    if (tail != 0) {
        tail->next = 0;
    }
    delete p;
}

template <class Type> void List<Type>::destroy()
{
    while (!empty()) {
        pop_back();
    }
}

template <class Type> void List<Type>::push_back(const Type &val)
{
    ListItem<Type> *pt = new ListItem<Type>(val);
    if (empty()) {
        head = tail = pt;
    } else {
        pt->prev = tail;
        tail->next = pt;
        tail = pt;
    }
}

template <class Type> void List<Type>::display_elems()
{
    for (ListItem<Type> *pt = head; pt; pt = pt->next) {
        cout << pt->item << " ";
    }
    cout << endl;
}

int main()
{
    List<int> list;
    list.display_elems(); // nothing
    list.push_back(1);
    list.push_back(2);
    list.push_back(4);
    list.push_back(3);
    list.display_elems(); // 1 2 4 3
    list.pop_back();
    list.push_back(5);
    list.display_elems(); // 1 2 4 5
    return 0;
}
```
