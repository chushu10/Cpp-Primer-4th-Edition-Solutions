# Exercise 14.15

Define the class assignment operator for the `CheckoutRecord` introduced in the exercises to Section 14.2.1 (p. 515 ).

**Answer**:

```cpp
CheckoutRecord& CheckoutRecord::operator=(const CheckoutRecord &rhs)
{
    book_id = rhs.book_id;
    title = rhs.title;
    date_borrowed = rhs.date_borrowed;
    date_due = rhs.date_due;
    borrower = std::make_pair(rhs.borrower.first, rhs.borrower.second);
    for (vector< pair<string,string>* >::const_iterator it = rhs.wait_list.begin();
                                                        it != rhs.wait_list.end();
                                                      ++it) {
        wait_list.push_back(*it);
    }
    return *this;
}
```