# Exercise 12.11

Define a pair of classes `X` and `Y`, in which `X` has a pointer to `Y`, and `Y` has an object of type `X` .

**Answer**:

```cpp
class Y;

class X
{
    Y *pointer_to_y;
};

class Y
{
    X object_of_x;
};

int main(int argc, char const *argv[])
{
    X x;
    Y y;
    return 0;
}
```