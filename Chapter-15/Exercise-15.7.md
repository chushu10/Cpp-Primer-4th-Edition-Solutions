# Exercise 15.7

We might define a type to implement a limited discount strategy. This class would give a discount for books purchased up to a limit. If the number of copies purchased exceeds that limit, then the normal price should be applied to any books purchased beyond the limit. Define a class that implements this strategy.

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

class Limit_item : public Item_base {
public:
    double net_price(std::size_t n) const;
private:
    std::size_t max_qty;
    double discount;
};

double Limit_item::net_price(size_t cnt) const {
    if (cnt >= max_qty) {
        double discount_part = max_qty * (1 - discount) * price;
        double normal_part = (cnt - max_qty) * price;
        return discount_part + normal_part;
    } else {
        return cnt * (1 - discount) * price;
    }
}
```