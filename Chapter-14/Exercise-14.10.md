# Exercise 14.10

What is wrong with the following `Sales_item` input operator?

```cpp
istream& operator>>(istream& in, Sales_item& s) {
    double price;
    in >> s.isbn >> s.units_sold >> price;
    s.revenue = s.units_sold * price;
    return in;
}
```

What would happen if we gave this operator the data in the previous exercise?

**Answer**:

There is no check for the correctness of the input stream `in`, variables like `price` might be undefined when it is being used. If we gave this operator data (a) from [Exercise 14.9](Exercise-14.9.md), it will be ok. However, given data (b), we would get a type mismatch when reading `units_sold` and `price`, making them undefined.