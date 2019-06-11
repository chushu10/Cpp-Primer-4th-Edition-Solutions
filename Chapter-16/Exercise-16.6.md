# Exercise 16.6

Similar to our a simplified version of `queue`, write a class template named `List` that is a simplified version of the standard `list` class.

**Answer**:

```cpp
template <class Type> class List {
public:
    List() {}       // default constructor
    Type &front(); // return element from head of List
    Type &back();  // return element from back of List
    const Type &front () const;
    const Type &back () const;
    void insert (const Type &); // inserts elements
    void pop_back();            // remove the last element
    bool empty() const;         // true if no elements in the List
private:
    // ...
};

int main()
{
    List<int> list;
    return 0;
}
```
