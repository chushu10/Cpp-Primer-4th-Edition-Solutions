# Exercise 12.26

Would it be legal for both the constructor that takes a `string` and the one that takes an `istream&` to have default
arguments? If not, why not?

**Answer**:

It's illegal when both of them appears in one class. Because when users create object without specifying arguments to the constructor of the class, the compiler don't know which one to use. See the compile error below:

```bash
ex1226.cc:21:16: error: call to constructor of 'Sales_item' is ambiguous
    Sales_item item;
               ^
ex1226.cc:6:5: note: candidate constructor
    Sales_item(const std::string &book = ""):
    ^
ex1226.cc:10:5: note: candidate constructor
    Sales_item(std::istream &is = std::cin) {
    ^
1 error generated.
```