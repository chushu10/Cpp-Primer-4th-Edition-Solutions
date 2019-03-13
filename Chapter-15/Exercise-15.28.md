# Exercise 15.28

Define a `vector` to hold objects of type `Item_base` and copy a number of objects of type `Bulk_item` into the `vector`. Iterate over the vector and generate the `net_price` for the elements in the container.

**Answer**:

```cpp
#include <string>
#include <vector>
#include <iostream>

class Item_base {
public:
    Item_base(const std::string &book = "",
              double sales_price = 0.0):
              isbn(book), price(sales_price) { }
    std::string book() const { return isbn; }
    virtual double net_price(std::size_t n) const
        { return n * price; }
private:
    std::string isbn;
protected:
    double price;
};

class Bulk_item : public Item_base {
public:
    Bulk_item(const std::string& book, double sales_price, std::size_t qty = 0, double disc_rate = 0.0):
        Item_base(book, sales_price),
        min_qty(qty), discount(disc_rate) { }
    double net_price(std::size_t) const;
private:
    std::size_t min_qty;
    double discount;
};

double Bulk_item::net_price(std::size_t cnt) const
{
    if (cnt >= min_qty) {
        return cnt * (1 - discount) * price;
    } else {
        return cnt * price;
    }
}

int main()
{
    Item_base item_base("The Chronicles of Narnia", 19.98);
    Bulk_item bulk_item("Harry Porter", 17.99, 10, 0.8);
    std::vector<Item_base> item_vec;
    item_vec.push_back(item_base);
    item_vec.push_back(bulk_item);
    std::vector<Item_base>::iterator it = item_vec.begin();
    for (; it != item_vec.end(); ++it) {
        std::cout << it->net_price(5) << std::endl;
    }
    return 0;
}

// output:
// 99.9
// 89.95
```