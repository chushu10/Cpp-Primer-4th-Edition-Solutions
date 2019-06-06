# Exercise 16.2

Write a function template that takes a reference to an `ostream` and a value, and writes the value to the stream. Call the function on at least four different types. Test your program by writing to `cout`, to a `file`, and to a `stringstream`.

**Answer**:

```cpp
#include <iostream>
#include <fstream>
#include <sstream>

template <typename T>
inline void WriteToStream(std::ostream &os, const T &value)
{
    os << value;
}

int main()
{
    // cout
    WriteToStream(std::cout, "Hello World");
    WriteToStream(std::cout, 12345);
    WriteToStream(std::cout, 3.1415926);
    WriteToStream(std::cout, '\n');

    // file
    std::ofstream outfile("ex1602.txt");
    WriteToStream(outfile, "Hello World");
    WriteToStream(outfile, 12345);
    WriteToStream(outfile, 3.1415926);
    WriteToStream(outfile, '\n');

    // stringstream
    std::ostringstream oss;
    WriteToStream(oss, "Hello World");
    WriteToStream(oss, 12345);
    WriteToStream(oss, 3.1415926);
    WriteToStream(oss, '\n');

    return 0;
}
```
