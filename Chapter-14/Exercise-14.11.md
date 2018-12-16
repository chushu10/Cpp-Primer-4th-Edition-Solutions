# Exercise 14.11

Define an input operator for the `CheckoutRecord` class defined in the exercises for Section 14.2.1 (p. 515 ). Be sure the operator handles input errors.

**Answer**:

```cpp
std::istream& operator>>(std::istream &in, CheckoutRecord &cr)
{
    string first, second;
    in >> cr.book_id >> cr.title >> cr.date_borrowed >> cr.date_due >> first >> second;
    if (in) {
        cr.borrower = make_pair(first, second);
    }
    while (in >> first >> second, !in.eof()) {
        pair<string, string> tmp = make_pair(first, second);
        cr.wait_list.push_back(&tmp);
    }
    return in;
}
```