# Exercise 13.14

A good way to understand copy-control members and constructors is to define a simple class with these members in which each member prints its name:

```cpp
struct Exmpl {
    Exmpl()
    {
        std::cout << "Exmpl()" << std::endl;
    }
    Exmpl(const Exmpl&)
    {
        std::cout << "Exmpl(const Exmpl&)" << std::endl;
    } // ...
};
```

Write a class like `Exmpl`, giving it the copy-control members and other constructors. Now write a program using objects of type `Exmpl` in various ways: pass them as non-reference and reference parameters; dynamically allocate them; put them in containers, and so forth. Studying which constructors and copy-control members are executed and when can be helpful in cementing your understanding of these concepts.

**Answer**:

```cpp
#include <iostream>
#include <vector>

struct Exmpl {
    Exmpl()
    {
        std::cout << "Exmpl()" << std::endl;
    }
    Exmpl(const Exmpl&)
    {
        std::cout << "Exmpl(const Exmpl&)" << std::endl;
    }
    ~Exmpl()
    {
        std::cout << "~Exmpl()" << std::endl;
    }
};

void func1(Exmpl exmpl) // calls copy constructor Exmpl(const Exmpl&)
{

} // calls destructor ~Exmpl()

void func2(Exmpl& exmpl) { } // calls no copy-control members

int main(int argc, char const *argv[])
{
    Exmpl exmpl; // calls constructor Exmpl()
    func1(exmpl);
    func2(exmpl);
    Exmpl *p = new Exmpl(); // calls constructor Exmpl()
    delete p;  // calls destructor ~Exmpl(), if not delete explicitly, the object pointed to by p will not be destructed
    std::vector<Exmpl> vec;
    vec.push_back(exmpl); // calls copy constructor Exmpl(const Exmpl&), the element copied will be destructed by the end
    return 0;
} // calls destructor ~Exmpl()
```