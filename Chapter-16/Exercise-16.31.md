# Exercise 16.31

The following definition of List is incorrect. How would you fix it?

```cpp
template <class elemType> class ListItem; template <class elemType> class List {
public:
    List<elemType>();
    List<elemType>(const List<elemType> &);
    List<elemType>& operator=(const List<elemType> &);
    ~List();
    void insert(ListItem *ptr, elemType value);
    ListItem *find(elemType value);
private:
    ListItem *front;
    ListItem *end;
};
```

**Answer**:

```cpp
template <class elemType> class ListItem;
template <class elemType> class List {
public:
    List<elemType>();
    List<elemType>(const List<elemType> &);
    List<elemType>& operator=(const List<elemType> &);
    ~List();
    void insert(ListItem<elemType> *ptr, elemType value);
    ListItem<elemType> *find(elemType value);
private:
    ListItem<elemType> *front;
    ListItem<elemType> *end;
};
```
