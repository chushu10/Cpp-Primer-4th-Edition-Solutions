# Exercise 7.33

Add a member that adds two `Sales_items`. Use the revised class to re-implement your solution to the average price problem presented in Chapter 1.

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
    bool input_item();
    void output_item() const;
    bool add_item(const Sales_item &item);
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

bool Sales_item::input_item()
{
    if (std::cin >> isbn &&
        std::cin >> units_sold &&
        std::cin >> revenue) {
            return true;
        }
    return false;
}

void Sales_item::output_item() const
{
    std::cout << isbn << " ";
    std::cout << units_sold << " ";
    std::cout << revenue << " ";
    std::cout << Sales_item::avg_price() << std::endl;
}

bool Sales_item::add_item(const Sales_item &item)
{
    if (Sales_item::same_isbn(item)) {
        units_sold += item.units_sold;
        revenue += item.revenue;
        return true;
    } else {
        std::cout << "Not the same isbn!" << std::endl;
        return false;
    }
}
```

```cpp
// ex731.cc
// g++ Sales_item.cc ex733.cc -o ex733

#include "Sales_item.h"

int main(int argc, char const *argv[])
{
    Sales_item total, trans;
    if (total.input_item()) {
        while (trans.input_item()) {
            if (!total.add_item(trans)) {
                total.output_item();
                total = trans;
            }
        }
    } else {
        std::cout << "No data?!" << std::endl;
        return -1;
    }
    return 0;
}
```