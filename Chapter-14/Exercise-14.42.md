# Exercise 14.42

Define a conversion operator to `bool` for the `CheckoutRecord` class from the exercises in Section 14.2.1 (p. 515 ).

**Answer**:

```cpp
class CheckoutRecord {
public:
    operator bool() const { return book_id; }
private:
    double book_id;
    string title;
    Date date_borrowed;
    Date date_due;
    pair<string,string> borrower;
    vector< pair<string,string>* > wait_list;
};
```