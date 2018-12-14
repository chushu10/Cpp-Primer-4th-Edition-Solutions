# Exercise 14.3

Explain the following program, assuming that the `Sales_item` constructor that takes a `string` is not `explicit`. Explain what happens if that constructor is `explicit`.

```cpp
string null_book = "9-999-99999-9";
Sales_item item(cin);
item += null_book;
```

**Answer**:

In the second line, the code implicitly converts `cin` to a `Sales_item`. This conversion executes the `Sales_item` constructor that takes an `istream`. That constructor creates a (temporary) `Sales_item` object by reading the standard input. That object is then passed to `item`.

In the third line, the compiler uses the `Sales_item` constructor that takes a `string` to generate a new `Sales_item` object from `null_book`, then add it up to `item`.

If the constructor that takes a `string` is `explicit`, then the third line will incur a type mismatch error.