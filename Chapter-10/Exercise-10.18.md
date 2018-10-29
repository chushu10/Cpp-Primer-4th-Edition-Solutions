# Exercise 10.18

Define a `map` for which the key is the family surname and the value is a `vector` of the children's names. Populate the `map` with at least six entries. Test it by supporting user queries based on a surname, which should list the names of children in that family.

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

    map<string, vector<string> > family_children;
    ifstream surname_file, firstname_file;
    string surname, firstname;

    if (!open_file(surname_file, "surname.txt")) {
        throw runtime_error("no surname file");
    }
    while (surname_file >> surname) {
        vector<string> children;
        if (!open_file(firstname_file, "firstname.txt")) {
            throw runtime_error("no firstname file");
        }
        while (firstname_file >> firstname) {
            children.push_back(firstname);
        }
        family_children.insert(make_pair(surname, children));
    }

    // Test
    map<string, vector<string> >::iterator map_it;
    map_it = family_children.find(argv[1]);
    if (map_it != family_children.end()) {
        vector<string> children = map_it->second;
        vector<string>::iterator it = children.begin();
        for (; it != children.end(); ++it) {
            cout << *it << " " << map_it->first << endl;
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