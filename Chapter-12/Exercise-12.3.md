# Exercise 12.3

Provide operations to return the name and address. Should these functions be `const`? Explain your choice.

**Answer**:

```cpp
class Person {
public:
    Person(std::string name, std::string address);
    std::string get_name()
    {
        return name;
    }
    std::string get_address()
    {
        return address;
    }
private:
    std::string name;
    std::string address;
}
```

The functions that return name and address needn't to be `const`, because we return the copy of the `string`s. However, if we want to return the reference to the `string`s, they should be `const`.