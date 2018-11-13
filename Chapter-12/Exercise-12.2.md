# Exercise 12.2

Provide a constructor for `Person` that takes two `string`s.

**Answer**:

```cpp
class Person {
public:
    Person(std::string name, std::string address);
private:
    std::string name;
    std::string address;
}
```