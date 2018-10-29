# Exercise 10.24

Write a program that generates the non-plural version of a word by stripping the 's' off the end of the word. Build an exclusion `set` to recognize words in which the trailing 's' should not be removed. Two examples of words to place in this `set` are success, class. Use this exclusion `set` to write a program that strips plural suffixes from its input but leaves words in the exclusion set unchanged.

**Answer**:

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <set>
#include <fstream>
using namespace std;

ifstream& open_file(ifstream &in, const string &file) {
    in.close(); // close in case it was already open
    in.clear(); // clear any existing errors
    // if the open fails, the stream will be in an invalid state
    in.open(file.c_str()); // open the file we were given
    return in; // condition state is good if open succeeded
}

int main(int argc, char const *argv[])
{
    set<string> exclusions;
    ifstream exclusion_file;
    string exclusion;
    if (!open_file(exclusion_file, "exclusion.txt")) {
        throw runtime_error("no exclusion file");
    }
    while (exclusion_file >> exclusion) {
        exclusions.insert(exclusion);
    }

    ifstream plural_file;
    string plural;
    if (!open_file(plural_file, "plural.txt")) {
        throw runtime_error("no plural file");
    }
    while (plural_file >> plural) {
        if (!exclusions.count(plural)) {
            cout << plural.substr(0, plural.size() - 1) << endl;
        } else {
            cout << plural << endl;
        }
    }
    return 0;
}
```

```bash
# exclusion.txt
success
class
jesus
```

```bash
# plural.txt
apples
oranges
jesus
success
flowers
animals
```