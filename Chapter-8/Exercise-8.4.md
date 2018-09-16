# Exercise 8.4

Test your function by calling it passing `cin` as an argument.

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
    printWhatYouEnter(cin);
    return 0;
}
```