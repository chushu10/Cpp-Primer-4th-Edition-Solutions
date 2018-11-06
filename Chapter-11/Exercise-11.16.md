# Exercise 11.16

Rewrite the program on 410 to use the `copy` algorithm to write the contents of a file to the standard output.

**Answer**:

```cpp
#include <iostream>
#include <iterator>
#include <string>
#include <fstream>
using namespace std;

ifstream& open_file(ifstream &in, const string &file)
{
    in.close(); // close in case it was already open
    in.clear(); // clear any existing errors
    // if the open fails, the stream will be in an invalid state
    in.open(file.c_str()); // open the file we were given
    return in; // condition state is good if open succeeded
}

int main(int argc, char const *argv[])
{
    ifstream infile;
    if (argc < 2 || !open_file(infile, argv[1])) {
        cerr << "No input file!" << endl;
        return EXIT_FAILURE;
    }
    istream_iterator<string> infile_iter(infile), eof;
    ostream_iterator<string> output(cout, "\n");
    copy(infile_iter, eof, output);

    return 0;
}
```