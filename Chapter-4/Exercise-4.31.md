# Exercise 4,31

Write a program that reads a string into a character array from the standard input. Describe how your program handles varying size inputs. Test your program by giving it a string of data that is longer than the array size you've allocated.

**Answer**:

```cpp
#include <string>
#include <iostream>
using std::string;
using std::cin;
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    size_t size;
    char input;
    // you have to tell me the length
    cout << "Input length of string: ";
    cin >> size;
    // so that I can new a proper char array
    char *str = new char[size];
    cout << "Input your string: ";
    for (size_t i = 0; i < size; ++i) {
        cin >> input;
        str[i] = input;
    }

    cout << str << endl;
    delete [] str;
    return 0;
}

```