# Exercise 15.20

Recalling the exercise from Section 13.3 (p. 487 ) in which you wrote a class whose copy-control members printed a message, add print statements to the constructors of the `Item_base` and `Bulk_item` classes. Define the copy-control members to do the same job as the synthesized versions but that also print a message. Now write programs using objects and functions that use the `Item_base` types. In each case, predict what objects will be created and destroyed and compare your predictions with what your programs generate. Continue experimenting until you can correctly predict which copy-control members are executed for a given bit of code.

**Answer**:

```cpp
#include <string>
#include <iostream>

class Item_base {
public:
    Item_base(const std::string &book = "",
              double sales_price = 0.0):
              isbn(book), price(sales_price) { }
    std::string book() const { return isbn; }
    virtual double net_price(std::size_t n) const
        { return n * price; }
    // copy controls
    Item_base(const Item_base &orig): isbn(orig.isbn), price(orig.price) { std::cout << "base copy" << std::cout; }
    Item_base& operator=(const Item_base &rhs)
    {
        std::cout << "base assign" << std::endl;
        isbn = rhs.isbn;
        price = rhs.price;
        return *this;
    }
    // If we write our own destructor, the synthesized destructor is still run.
    virtual ~Item_base() { std::cout << "base destructor" << std::endl; }
private:
    std::string isbn;
protected:
    double price;
};

class Bulk_item : public Item_base {
public:
    double net_price(std::size_t n) const;
    // copy controls
    Bulk_item(const Bulk_item &orig): min_qty(orig.min_qty), discount(orig.discount) { std::cout << "derived copy" << std::cout; }
    Bulk_item& operator=(const Bulk_item &rhs)
    {
        std::cout << "derived assign" << std::endl;
        min_qty = rhs.min_qty;
        discount = rhs.discount;
        return *this;
    }
    // If we write our own destructor, the synthesized destructor is still run.
    ~Bulk_item() { std::cout << "derived destructor" << std::endl; }
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

int main()
{
    return 0;
}
```