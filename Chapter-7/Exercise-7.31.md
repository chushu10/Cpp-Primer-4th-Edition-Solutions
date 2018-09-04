# Exercise 7.31

Write your own version of the `Sales_item` class, adding two new `public` members to read and write `Sales_item` objects. These functions should operate similarly to the input and output operators used in Chapter 1. Transactions should look lke the ones defined in that chapter as well. Use this class to read and write a set of transactions.

**Answer**:

```cpp
// Sales_item.h
#include <string>
#include <iostream>

class Sales_item {
public:
    double avg_price() const;
    bool same_isbn(const Sales_item &rhs) const
    {
        return isbn == rhs.isbn;
    }
    Sales_item(): units_sold(0), revenue(0.0) { }
    void input_item();
    void output_item() const;
private:
    std::string isbn;
    unsigned units_sold;
    double revenue;
};
```

```cpp
// Sales_item.cc
#include "Sales_item.h"

double Sales_item::avg_price() const
{
    if (units_sold) {
        return revenue / units_sold;
    } else {
        return 0;
    }
}

void Sales_item::input_item()
{
    std::cin >> isbn;
    std::cin >> units_sold;
    std::cin >> revenue;
}

void Sales_item::output_item() const
{
    std::cout << isbn << " ";
    std::cout << units_sold << " ";
    std::cout << revenue << " ";
    std::cout << Sales_item::avg_price() << std::endl;
}
```

```cpp
// ex731.cc
// g++ Sales_item.cc ex731.cc -o ex731

#include "Sales_item.h"

int main(int argc, char const *argv[])
{
    Sales_item book;
    book.input_item();
    book.output_item();
    return 0;
}
```