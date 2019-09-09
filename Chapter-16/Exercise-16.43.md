# Exercise 16.43

Add the `assign` member and a constructor that takes a pair of iterators to your `List` class.

**Answer**:

```cpp
#include <iostream>
#include <vector>
using namespace std;

template <class Type> class List;
template <class T> std::ostream& operator<<(std::ostream&, const List<T>&);

template <class Type> class ListItem {
    friend class List<Type>;
    friend std::ostream& operator<< <Type> (std::ostream&, const List<Type>&);
    ListItem(const Type &t): item(t), prev(0), next(0) { }
    Type item;
    ListItem *prev;
    ListItem *next;
};

template <class Type> class List {
    friend std::ostream& operator<< <Type> (std::ostream&, const List<Type>&);
public:
    template <class Iter> List(Iter beg, Iter end):
        head(0), tail(0) { copy_elems(beg, end); }
    template <class Iter> void assign(Iter, Iter);
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
private:
    ListItem<Type> *head;
    ListItem<Type> *tail;
    void destroy();
    void copy_elems(const List&);
    template <class Iter> void copy_elems(Iter, Iter);
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

template <class Type>
ostream& operator<<(ostream &os, const List<Type> &q)
{
    os << "< ";
    ListItem<Type> *p;
    for (p = q.head; p; p = p->next) {
        os << p->item << " ";
    }
    os << ">";
    return os;
}

template <class Type> template <class Iter>
void List<Type>::assign(Iter beg, Iter end)
{
    destroy(); // remove existing elements in this List
    copy_elems(beg, end); // copy elements from the input range
}

template <class Type> template <class Iter>
void List<Type>::copy_elems(Iter beg, Iter end)
{
    while (beg != end) {
        push_back(*beg);
        ++beg;
    }
}

int main()
{
    short a[4] = { 0, 3, 6, 9 };
    // instantiates List<int>::List(short *, short *)
    List<int> qi(a, a + 4); // copies elements from a into qi
    std::cout << qi << std::endl;
    std::vector<int> vi(a, a + 3);
    // instantiates List<int>::assign(vector<int>::iterator,
    //                                 vector<int>::iterator)
    qi.assign(vi.begin(), vi.end());
    std::cout << qi << std::endl;
    return 0;
}
```
