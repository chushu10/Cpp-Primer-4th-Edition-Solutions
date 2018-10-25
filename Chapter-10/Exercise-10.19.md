# Exercise 10.19

Extend the `map` from the previous exercise by having the `vector` store a `pair` that holds a child's name and birthday. Revise the program accordingly. Test your modified test program to verify its correctness.

**Answer**:

```cpp
#include <string>
#include <vector>
#include <iostream>
#include <map>
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
    if (argc != 2) {
        throw runtime_error("wrong number of arguments");
    }

    map<string, vector<pair<string, string> > > familyChildren;
    ifstream surnameFile, firstnameFile, birthdayFile;
    string surname, firstname, birthday;

    if (!open_file(surnameFile, "surname.txt")) {
        throw runtime_error("no surname file");
    }
    while (surnameFile >> surname) {
        vector<pair<string, string> > children;
        if (!open_file(firstnameFile, "firstname.txt")) {
            throw runtime_error("no firstname file");
        }
        if (!open_file(birthdayFile, "birthday.txt")) {
            throw runtime_error("no birthday file");
        }
        while (firstnameFile >> firstname &&
               birthdayFile >> birthday) {
            children.push_back(make_pair(firstname, birthday));
        }
        familyChildren.insert(make_pair(surname, children));
    }

    // Test
    map<string, vector<pair<string, string> > >::iterator mapIt;
    mapIt = familyChildren.find(argv[1]);
    if (mapIt != familyChildren.end()) {
        vector<pair<string, string> > children = mapIt->second;
        vector<pair<string, string> >::iterator it = children.begin();
        for (; it != children.end(); ++it) {
            cout << it->first << " " << mapIt->first
                 << " born in: " << it->second << endl;
        }
    } else {
        cout << argv[1] << " not found!" << endl;
    }

    return 0;
}
```

```bash
# firstname.txt
David
Michael
Luis
Angel
Julia
```

```bash
# surname.txt
Jackson
Smith
Williams
Johnson
Chang
Lee
```

```bash
# birthday.txt
2001.01.15
2008.02.14
2006.11.13
2010.12.24
2000.05.07
```