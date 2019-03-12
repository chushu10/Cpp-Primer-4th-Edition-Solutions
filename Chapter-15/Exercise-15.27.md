# Exercise 15.27

Try to define an object of type `Disc_item` and see what errors you get from the compiler.

**Answer**:

```bash
x1527.cc:29:15: error: variable type 'Disc_item' is an abstract class
    Disc_item disc_item;
              ^
ex1527.cc:19:12: note: unimplemented pure virtual method 'net_price' in 'Disc_item'
    double net_price(std::size_t) const = 0;
           ^
1 error generated.
```