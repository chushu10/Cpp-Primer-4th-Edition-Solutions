# Exercise 4.34

Write a program to read `string`s into a `vector`. Now, copy that `vector` into an array of character pointers. For each element in the `vector`, allocates a new character array and copy the data from the `vector` element into that character array. Then insert a pointer to the character array into the array of character pointers.

**Answer**:

```cpp
#include <vector>
#include <string>
#include <iostream>
using std::vector;
using std::string;
using std::cin;
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    size_t num;
    vector<string> svec;
    string input;

    cout << "Input number of strings: ";
    cin >> num;

    cout << "Input each string: ";
    for (size_t i = 0; i < num; ++i) {
        cin >> input;
        svec.push_back(input);
    }

    char **sarr = new char*[num];
    for (size_t i = 0; i < num; ++i) {
        size_t size = svec[i].size();
        char *str = new char[size + 1];
        for (size_t j = 0; j < size; ++j) {
            str[j] = svec[i][j];
        }
        str[size] = 0;
        sarr[i] = str;
        cout << sarr[i] << " ";
    }
    cout << endl;

    for (size_t i = 0; i < num; ++i) {
        delete [] sarr[i];
    }
    delete [] sarr;
    return 0;
}

```