# Exercise 13.3

Assuming `Point` is a class type with a public copy constructor, identify each use of the copy constructor in this program fragment:

```cpp
Point global;

Point foo_bar(Point arg)
{
    Point local = arg;
    Point *heap = new Point(global);
    *heap = local;
    Point pa[ 4 ] = { local, *heap };
    return *heap;
}
```

**Answer**:

```cpp
Point global;

Point foo_bar(Point arg) // the parameter is non-reference type, so that arg is copied from the caller
{
    Point local = arg; // explicit copy when initialize local
    Point *heap = new Point(global); // explicit copy when initialize object pointed by heap
    *heap = local;
    Point pa[ 4 ] = { local, *heap }; // twice, explicit copy when initialize array pa
    return *heap; // implicit copy when return
}
```

The example code below prints every use of copy constructor by setting a `static` member of class `Point`:

```cpp
#include <iostream>
#include <string>

class Point {
public:
    Point()
    {
        x_ = 0;
        y_ = 0;
    }
    Point(const Point& point)
    {
        std::cout << copy_info << ": copy invoked." << std::endl;
    }
    static void set_copy_info(const char *str)
    {
        copy_info = std::string(str);
    }
private:
    static std::string copy_info;
    int x_;
    int y_;
};

Point global;
std::string Point::copy_info = "init";

Point foo_bar(Point arg)
{
    Point::set_copy_info("when initialize local");
    Point local = arg;
    Point::set_copy_info("when initialize pointer heap");
    Point *heap = new Point(global);
    Point::set_copy_info("when assign to heap");
    *heap = local;
    Point::set_copy_info("when initialize array pa");
    Point pa[ 4 ] = { local, *heap };
    Point::set_copy_info("when return heap");
    return *heap;
}

int main(int argc, char const *argv[])
{
    Point::set_copy_info("when passed to foo_bar");
    Point point = foo_bar(global);
    return 0;
}
```

The output is:

```bash
when passed to foo_bar: copy invoked.
when initialize local: copy invoked.
when initialize pointer heap: copy invoked.
when initialize array pa: copy invoked.
when initialize array pa: copy invoked.
when return heap: copy invoked.
```