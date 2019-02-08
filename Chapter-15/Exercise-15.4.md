# Exercise 15.4

A library has different kinds of materials that it lends outbooks, CDs, DVDs, and so forth. Each of the different kinds of lending material has different check-in, check-out, and overdue rules. The following class defines a base class that we might use for this application. Identify which functions are likely to be defined as virtual and which, if any, are likely to be common among all lending materials. (Note: we assume that `LibMember` is a class representing a customer of the library, and `Date` is a class representing a calendar day of a particular year.)

```cpp
class Library {
public:
    bool check_out(const LibMember&);
    bool check_in (const LibMember&);
    bool is_late(const Date& today);
    double apply_fine();
    ostream& print(ostream& = cout);
    Date due_date() const;
    Date date_borrowed() const;
    string title() const;
    const LibMember& member() const;
};
```

**Answer**:

```cpp
class Library {
public:
    virtual bool check_out(const LibMember&);
    virutal bool check_in (const LibMember&);
    bool is_late(const Date& today);
    double apply_fine();
    ostream& print(ostream& = cout);
    virtual Date due_date() const;
    Date date_borrowed() const;
    string title() const;
    const LibMember& member() const;
};
```