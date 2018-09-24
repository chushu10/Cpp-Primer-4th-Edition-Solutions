# Exercise 9.6

Given a class type named `Foo` that does not define a default constructor but does define a constructor that takes `int` values, define a list of `Foo` that holds 10 elements.

**Answer**:

```cpp
class Foo {
public:
    Foo(int i)
    {
        num = i;
    }
    int getNum() const
    {
        return num;
    }
private:
    int num;
};

int main(int argc, char const *argv[])
{
    list<Foo> fooList(10, 2);
    list<Foo>::const_iterator it = fooList.begin();
    for ( ; it != fooList.end(); ++it) {
        cout << it->getNum() << endl;
    }
    return 0;
}
```