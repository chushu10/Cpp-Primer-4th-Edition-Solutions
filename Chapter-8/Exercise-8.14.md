# Exercise 8.14

Use `open_file` and the program you wrote for the [first exercise](Exercise-8.4.md) in Section 8.2 (p. 291) to open a given file and read its contents.

**Answer**:

```cpp
ifstream& open_file(ifstream &in, const string &file)
{
    in.close();
    in.clear();
    in.open(file.c_str());
    return in;
}

istream &printWhatYouEnter(istream &is)
{
    string input;
    while (is >> input) {
        cout << input << endl;
    }
    is.clear();
    return is;
}

int main(int argc, char const *argv[])
{
    ifstream in;
    printWhatYouEnter(open_file(in, "ex87-1.txt"));
    return 0;
}

// $ cat ex87-1.txt
// This is file ex87-1.txt
```