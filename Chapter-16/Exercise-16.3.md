# Exercise 16.3

When we called compare on two `string`s, we passed two `string` objects, which we initialized from string literals. What would happen if we wrote:

```cpp
compare ("hi", "world");
```

**Answer**:

For the following program:

```cpp
#include <string>
#include <iostream>

template <typename T>
int compare(const T &v1, const T &v2)
{
    if (v1 < v2) return -1;
    if (v2 < v1) return 1;
    return 0;
}

int main()
{
    std::cout << compare("hi", "world") << std::endl;
    return 0;
}
```

I got compiling error like this:

```bash
$ make ex1603
g++ -Wall -Werror -Wextra -pedantic -std=c++17 -g -fsanitize=address  -fsanitize=address  ex1603.cc   -o ex1603
ex1603.cc:14:18: error: no matching function for call to 'compare'
    std::cout << compare("hi", "world") << std::endl;
                 ^~~~~~~
ex1603.cc:5:5: note: candidate template ignored: deduced conflicting types for parameter 'T' ('char [3]' vs. 'char [6]')
int compare(const T &v1, const T &v2)
    ^
1 error generated.
make: *** [ex1603] Error 1
```

The correct way to use `compare` is like this:

```cpp
std::cout << compare(std::string("hi"), std::string("world")) << std::endl;
```

Or, like this:

```cpp
std::string s1("hi");
std::string s2("world");
std::cout << compare(s1, s2) << std::endl;
```

As mentioned in section 3.2.1:

> Caution: Library string Type and String Literals
> For historical reasons, and for compatibility with C, character string literals are not the same type as the standard library string type. This fact can cause confusion and is important to keep in mind when using a string literal or the string data type.  
