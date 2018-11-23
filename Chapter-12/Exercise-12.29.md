# Exercise 12.29

Explain what operations happen during the following definitions:

```cpp
string null_isbn = "9-999-99999-9";
Sales_item null1(null_isbn);
Sales_item null("9-999-99999-9");
```

**Answer**:

```cpp
string null_isbn = "9-999-99999-9";
Sales_item null1(null_isbn); // null_isbn is a non-const string, it will be converted to const string first, and then it will be passed to the constructor that takes a string, and create a object named null1
Sales_item null("9-999-99999-9"); // use the constructor that takes a string, and create a object named null
```