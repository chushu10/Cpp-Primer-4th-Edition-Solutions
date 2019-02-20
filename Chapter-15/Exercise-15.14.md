# Exercise 15.14

Redefine the `Bulk_item` and `Item_base` classes so that they each need to define only a single constructor.

**Answer**:

```cpp
class Item_base {
public:
    Item_base(const std::string& book = "", double sales_price = 0.0): isbn(book), price(sales_price) {}
private:
    std::string isbn;
    double price;
};

class Disc_item : public Item_base {
public:
    Disc_item(const std::string& book = "", double sales_price = 0.0, std::size_t qty = 0, double disc_rate = 0.0): Item_base(book, sales_price), quantity(qty), discount(disc_rate) { }
protected:
    std::size_t quantity;
    double discount;
};

class Bulk_item : public Disc_item {
public:
    Bulk_item(const std::string& book = "", double sales_price = 0.0, std::size_t qty = 0, double disc_rate = 0.0): Disc_item(book, sales_price, qty, disc_rate) { }
    double net_price(std::size_t) const;
};
```