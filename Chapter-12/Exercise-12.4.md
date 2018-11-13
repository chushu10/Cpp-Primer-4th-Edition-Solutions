# Exercise 12.4

Indicate which members of `Person` you would declare as `public` and which you would declare as `private`. Explain your choice.

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

The data members should be `private` because we don't want anyone to modify them directly. However, the constructor and member functions should be `public` because these are all the operations provided by our class `Person`.