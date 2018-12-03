# Exercise 13.13

Determine whether the `Employee` class, defined in the exercises on page 484, needs a destructor. If so, implement it.

**Answer**:

It only has a `string` member and an `int` member, so that it doesn't need a destructor.

```cpp
class Employee {
public:
    Employee(const std::string& name);
    Employee(const Employee& employee);
    Employee& operator=(const Employee& employee);
    std::string get_name() const { return name_; }
    int get_id() const { return id_; }
private:
    std::string name_;
    int id_;
    static int next_id_;
};
```