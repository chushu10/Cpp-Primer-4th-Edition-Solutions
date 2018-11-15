# Exercise 12.10

Explain each member in the following class:

```cpp
class Record {
    typedef std::size_t size;
    Record(): byte_count(0) { }
    Record(size s): byte_count(s) { }
    Record(std::string s): name(s), byte_count(0) { }
    size byte_count;
    std::string name;
public:
    size get_count() const { return byte_count; }
    std::string get_name() const { return name; }
};
```

**Answer**:

```cpp
class Record {
    typedef std::size_t size; // rename std::size_t to size
    Record(): byte_count(0) { } // default constructor that initialize byte_count to 0
    Record(size s): byte_count(s) { } // constructor that initialize byte_count to s
    Record(std::string s): name(s), byte_count(0) { } // constructor that initialize byte_count to 0 and name to s
    // The constructors above are all private, so they are useless

    size byte_count; // private member byte_count
    std::string name; // private member name
public:
    size get_count() const { return byte_count; } // getter for byte_count
    std::string get_name() const { return name; } // getter for name
};
```