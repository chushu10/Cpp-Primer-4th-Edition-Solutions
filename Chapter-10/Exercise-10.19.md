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

    map<string, vector<pair<string, string> > > family_children;
    ifstream surname_file, firstname_file, birthday_file;
    string surname, firstname, birthday;

    if (!open_file(surname_file, "surname.txt")) {
        throw runtime_error("no surname file");
    }
    while (surname_file >> surname) {
        vector<pair<string, string> > children;
        if (!open_file(firstname_file, "firstname.txt")) {
            throw runtime_error("no firstname file");
        }
        if (!open_file(birthday_file, "birthday.txt")) {
            throw runtime_error("no birthday file");
        }
        while (firstname_file >> firstname &&
               birthday_file >> birthday) {
            children.push_back(make_pair(firstname, birthday));
        }
        family_children.insert(make_pair(surname, children));
    }

    // Test
    map<string, vector<pair<string, string> > >::iterator map_it;
    map_it = family_children.find(argv[1]);
    if (map_it != family_children.end()) {
        vector<pair<string, string> > children = map_it->second;
        vector<pair<string, string> >::iterator it = children.begin();
        for (; it != children.end(); ++it) {
            cout << it->first << " " << map_it->first
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