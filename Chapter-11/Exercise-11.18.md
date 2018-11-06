# Exercise 11.18

Write a program to read a sequence of integer numbers from the standard input using an `istream_iterator`. Write the odd numbers into one file, using an `ostream_iterator`. Each value should be followed by a space. Write the even numbers into a second file, also using an `ostream_iterator`. Each of these values should be placed on a separate line.

**Answer**:

```cpp
#include <vector>
#include <iterator>
#include <iostream>
#include <fstream>
using namespace std;

ofstream& open_file(ofstream &out, const string &file)
{
    out.close(); // close in case it was already open
    out.clear(); // clear any existing errors
    // if the open fails, the stream will be in an invalid state
    out.open(file.c_str()); // open the file we were given
    return out; // condition state is good if open succeeded
}

int main(int argc, char const *argv[])
{
    ofstream odd_file, even_file;
    open_file(odd_file, "odd.txt");
    open_file(even_file, "even.txt");
    ostream_iterator<int> odd_iter(odd_file, " ");
    ostream_iterator<int> even_iter(even_file, "\n");
    istream_iterator<int> input_iter(cin), eof;
    while (input_iter != eof) {
        if (*input_iter % 2 != 0) {
            *odd_iter++ = *input_iter++;
        } else {
            *even_iter++ = *input_iter++;
        }
    }
    return 0;
}
```