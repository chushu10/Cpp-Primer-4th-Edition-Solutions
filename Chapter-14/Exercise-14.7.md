# Exercise 14.7

Define an output operator for the following `CheckoutRecord` class:

```cpp
class CheckoutRecord {
public:
    // ...
private:
    double book_id;
    string title;
    Date date_borrowed;
    Date date_due;
    pair<string,string> borrower;
    vector< pair<string,string>* > wait_list;
};
```

**Answer**:

```cpp
std::ostream& operator<<(std::ostream &out, const CheckoutRecord &cr)
{
    out << book_id << "\t"
        << title << "\t"
        << date_borrowed << "\t"
        << date_due << "\t"
        << borrower.first << ", " << borrower.second << "\t";
    for (vector< pair<string, string>* >::iterator it = wait_list.begin();
                                                   it != wait_list.end();
                                                   it++) {
        out << it->first << ", " << it->second << "\t";
    }
    return out;
}
```