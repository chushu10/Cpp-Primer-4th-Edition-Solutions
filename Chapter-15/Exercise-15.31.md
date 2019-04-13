# Exercise 15.31

Define and implement the `clone` operation for the limited discount class implemented in the exercises for Section 15.2.3 (p. 567 ).

**Answer**:

```cpp
class Item_base {
public:
    Item_base(const std::string &book = "",
              double sales_price = 0.0):
              isbn(book), price(sales_price) { }
    std::string book() const { return isbn; }
    virtual double net_price(std::size_t n) const
    virtual ~Item_base() { }
    virtual Item_base* clone() const
        { return new Item_base(*this); }
private:
    std::string isbn;
protected:
    double price;
};

class Bulk_item : public Item_base {
public:
    double net_price(std::size_t n) const;
    Bulk_item* clone() const
        { return new Bulk_item(*this); }
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