# Exercise 15.34

Modify your `debug` function to let users turn debugging on or off. Implement the control two ways:
a. By defining a parameter to the `debug` function
b. By defining a class data member that allows individual objects to turn on or turn off the display of debugging information.

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

// b. By defining a class data member that allows individual objects to turn on or turn off the display of debugging information.
class Bulk_item : public Item_base {
public:
    double net_price(std::size_t n) const;
    Bulk_item* clone() const
        { return new Bulk_item(*this); }
    void debug() const;
    void debug_with_switch(bool on) const;
    bool debug_on;
private:
    std::size_t min_qty;
    double discount;
};

// a. By defining a parameter to the `debug` function
void Bulk_item::debug() const {
    if (debug_on) {
        Item_base::debug();
        std::cout << min_qty << " " << discount << std::endl;
    }
}

void Bulk_item::debug_with_switch(bool on) const {
    if (on) {
        Item_base::debug();
        std::cout << min_qty << " " << discount << std::endl;
    }
}

double Bulk_item::net_price(size_t cnt) const {
    if (cnt >= min_qty) {
        return cnt * (1 - discount) * price;
    } else {
        return cnt * price;
    }
}
```