# Exercise 15.32

In practice, our programs are unlikely to run correctly the first time we run them or the first time we run them against real data. It is often useful to incorporate a debugging strategy into the design of our classes. Implement a virtual `debug` function for our `Item_base` class hierarchy that displays the data members of the respective classes.

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
    virtual void debug() const
        { std::cout << isbn << " " << price << std::endl; }
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
    void debug() const
        { Item_base::debug(); std::cout << min_qty << " " << discount << std::endl; }
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