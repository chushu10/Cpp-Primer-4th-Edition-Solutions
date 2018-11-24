# Exercise 12.35

Define a nonmember function that reads an `istream` and stores what it reads into a `Sales_item`.

**Answer**:

```cpp
friend bool read_item(istream &is)
{
    if (std::cin >> isbn_ &&
        std::cin >> units_sold_ &&
        std::cin >> revenue_)
    {
        return true;
    }
    return false;
}
```