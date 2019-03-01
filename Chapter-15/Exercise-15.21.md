# Exercise 15.21

Redefine your `Item_base` hierarchy to include a `Disc_item` class.

**Answer**:

```cpp
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

class Disc_item : public Item_base {
public:
    std::pair<size_t, double> discount_policy() const { return std::make_pair(quantity, discount); }
protected:
    std::size_t quantity;
    double discount;
};
```