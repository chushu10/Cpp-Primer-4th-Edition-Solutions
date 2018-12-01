# Exercise 13.10

Define an `Employee` class that contains the employee's name and a unique employee identifier. Give the class a default constructor and a constructor that takes a `string` representing the employee's name. If the class needs a copy constructor or assignment operator, implement those functions as well.

**Answer**:

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

int Employee::next_id_ = 0;

Employee::Employee(const std::string& name)
{
    name_ = name;
    id_ = ++next_id_;
}

Employee::Employee(const Employee& employee)
{
    name_ = employee.get_name();
    id_ = employee.get_id();
}

Employee& Employee::operator=(const Employee& employee)
{
    name_ = employee.get_name();
    id_ = employee.get_id();
    return *this;
}
```