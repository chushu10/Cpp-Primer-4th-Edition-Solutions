# Exercise 15.35

Write your own version of the `compare` function and `Basket` class and use them to manage a sale.

**Answer**:

```cpp
class Basket {
    // type of the comparison function used to order the multiset
    typedef bool (*Comp)(const Sales_item&, const Sales_item&);
public:
    // make it easier to type the type of our set
    typedef std::multiset<Sales_item, Comp> set_type;
    // typedefs modeled after corresponding container types
    typedef set_type::size_type size_type;
    typedef set_type::const_iterator const_iter;
    Basket(): items(compare) { } // initialze the comparator void add_item(const Sales_item &item)
        { items.insert(item); }
    size_type size(const Sales_item &i) const
        { return items.count(i); }
    double total() const; // sum of net prices for all items in the basket
private:
    std::multiset<Sales_item, Comp> items;
};

double Basket::total() const {
    double sum = 0.0; // holds the running total
    /* find each set of items with the same isbn and calculate
     * the net price for that quantity of items
     * iter refers to first copy of each book in the set
     * upper_bound refers to next element with a different isbn
     */
    for (const_iter iter = items.begin();
                    iter != items.end();
                    iter = items.upper_bound(*iter))
        // we know there's at least one element with this key in the Basket
        // virtual call to net_price applies appropriate discounts, if any
    {
        sum += (*iter)->net_price(items.count(*iter));
    }
    return sum;
}
```