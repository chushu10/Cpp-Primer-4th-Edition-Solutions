# Exercise 15.22

Redefine `Bulk_item` and the class you implemented in the exercises from Section 15.2.3 (p. 567 ) that represents a limited discount strategy to inherit from `Disc_item`.

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
    virtual double net_price(std::size_t n) const;
protected:
    std::size_t quantity;
    double discount;
};

class Bulk_item : public Disc_item {
public:
    double net_price(std::size_t) const;
};
```