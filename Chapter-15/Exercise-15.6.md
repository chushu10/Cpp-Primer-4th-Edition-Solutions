# Exercise 15.6

Write your own version of the `Bulk_item` class.

**Answer**:

```cpp
class Item_base {
public:
    Item_base(const std::string &book = "",
              double sales_price = 0.0):
              isbn(book), price(sales_price) { }
    std::string book() const { return isbn; }
    virtual double net_price(std::size_t n) const
        {return n * price; }
    virtual ~Item_base() { }
private:
    std::string isbn;
protected:
    double price;
};

class Bulk_item : public Item_base {
public:
    double net_price(std::size_t n) const;
private:
    std::size_t min_qty;
    double discount;
};

double Bulk_item::net_price(size_t cnt) const {
    if (cnt >= min_qty) {
        return cnt * (1 - discount) * price;
    } else {
        return cnt * price;
    }
}
```