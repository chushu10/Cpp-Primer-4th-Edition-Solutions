# Exercise 12.42

Which, if any, of the following static data member declarations and definitions are errors? Explain why.

```cpp
// example.h
class Example {
public:
    static double rate = 6.5;
    static const int vecSize = 20;
    static vector<double> vec(vecSize);
};

// example.C
#include "example.h"
double Example::rate;
vector<double> Example::vec;
```

**Answer**:

```cpp
// example.h
class Example {
public:
    static double rate = 6.5; // error, not integral, cannot be initialized in class
    static const int vecSize = 20;
    static vector<double> vec(vecSize); // error, not integral, cannot be initialized in class
};

// example.C
#include "example.h"
double Example::rate; // error, should provide initialization
vector<double> Example::vec;
```

Correct version:

```cpp
// example.h
#include <vector>

class Example {
public:
    static double rate;
    static const int vecSize = 20;
    static std::vector<double> vec;
};

// example.cc
double Example::rate;
const int Example::vecSize;
std::vector<double> Example::vec(vecSize);
```