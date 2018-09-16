# Exercise 8.6

Because `ifstream` inherits from `istream`, we can pass a `ifstream` object to a function that takes a reference to an `istream`. Use the function you wrote for the first exercise in Section 8.2(p. 291) to read a named file.

**Answer**:

```cpp
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
    ifstream ifs("ex86.txt");
    if (ifs) {
        printWhatYouEnter(ifs);
        ifs.close();
    }
    return 0;
}

// $ cat ex86.txt
// Hello, this is exercise 8.6
```