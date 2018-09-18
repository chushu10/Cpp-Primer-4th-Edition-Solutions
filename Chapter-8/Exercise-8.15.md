# Exercise 8.15

Use the function you wrote for the [first exercise](Exercise-8.4.md) in Section 8.2 (p. 291) to print the contents of an `istringstream` object.

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
    istringstream iss("Hello World!");
    printWhatYouEnter(iss);
    return 0;
}
```