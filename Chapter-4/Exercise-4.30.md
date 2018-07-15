# Exercise 4.30

Write a program to concatenate two C-style string literals, putting the result int a C-style string. Write a program to concatenate two library `string` that have the same value as the literals used in the first program.

**Answer**:

```cpp
#include <cstring>
#include <iostream>
#include <string>
using std::string;
using std::cout;
using std::endl;

// C-Style string concatenate
// Parameters: two C-Style string literals
// Return value: a dynamically allocated char array
//               terminated with null, the array
//               should be freed by caller
char *cStyleStrcat(const char *a, const char *b)
{
    size_t len1 = strlen(a);
    size_t len2 = strlen(b);
    // 1 for null
    char *result = new char[len1 + len2 + 1];
    for (size_t i = 0; i < len1; ++i) {
        result[i] = a[i];
    }
    for (size_t i = 0; i < len2; ++i) {
        result[i + len1] = b[i];
    }
    result[len1 + len2] = 0;
    return result;
}

// Library string concatenate
// Parameters: two library string literals
// Return value: a library string type, no need to
//               be freed by caller
string libStrcat(const string a, const string b) {
    return a + b;
}

int main(int argc, char const *argv[])
{
    const char *a = "Hello";
    const char *b = "World";
    char *result = cStyleStrcat(a, b);
    cout << result << endl;
    delete [] result;

    string str1 = "Hello";
    string str2 = "World";
    cout << libStrcat(str1, str2) << endl;
    return 0;
}

```