# Exercise 12.24

Using the version of `Sales_item` from page 458 that defined two constructors, one of which has a default argument for its single string parameter, determine which constructor is used to initialize each of the following variables and list the values of the data members in each object:

```cpp
Sales_item first_item(cin);
int main() {
    Sales_item next;
    Sales_item last("9-999-99999-9");
}
```

**Answer**:

```cpp
class Sales_item {
public:
    Sales_item(const std::string &book = ""):
        isbn(book), units_sold(0), revenue(0.0) { }
    Sales_item(std::istream &is);
};

Sales_item first_item(cin); // use Sales_item(std::istream &is), isbn = "", units_sold = 0, revenue = 0.0
int main() {
    Sales_item next; // use Sales_item(const std::string &book = ""), isbn = "", units_sold uninitialized, revenue uninitialized
    Sales_item last("9-999-99999-9"); // use Sales_item(const std::string &book = ""), isbn = "9-999-99999-9", units_sold = 0, revenue = 0.0
}
```