# Exercise 12.20

Choose one of the following abstractions (or an abstraction of your own choosing). Determine what data is needed in the
class. Provide an appropriate set of constructors. Explain your decisions.

(a) `Book` (b) `Date` (c) `Employee` (d) `Vehicle` (e) `Object` (f) `Tree`

**Answer**:

`Vehicle` for example, talk is cheap, so I'll show you the code:

```cpp
class Vehicle {
public:
    Vehicle(): wheel_num(4), need_gas(true), door_num(5) {}
    Vehicle(const std::string &);
private:
    int wheel_num;
    bool need_gas;
    int door_num;
    std::string brand;
};

// main
Vehicle benz = Vehicle("Mercedes Benz");
```