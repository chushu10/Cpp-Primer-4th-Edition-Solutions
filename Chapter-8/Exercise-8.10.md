# Exercise 8.10

Rewrite the previous program to store each word in a separate element.

**Answer**:

```cpp
vector<string> fileToStrVec(string filename) {
    ifstream input(filename.c_str());
    string s;
    vector<string> svec;
    if (!input) {
        cerr << "File " << filename
             << " cannot be opened." << endl;
        return svec;
    }
    while (input >> s) {
        svec.push_back(s);
    }
    input.close();
    return svec;
}

int main(int argc, char const *argv[])
{
    vector<string> svec = fileToStrVec("ex89.txt");
    vector<string>::const_iterator it = svec.begin();
    for ( ; it != svec.end(); ++it) {
        cout << *it << endl;
    }
    return 0;
}
```