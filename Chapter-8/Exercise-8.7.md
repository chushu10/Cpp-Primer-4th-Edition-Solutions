# Exercise 8.7

The two programs we wrote in this section used a `break` to exit the while loop if the open failed for any file in the `vector`. Rewrite these two loops to print a warning message if a file can't be opened and continue processing by getting the next file name from the `vector`.

**Answer**

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
    ifstream input;
    vector<string> files;
    files.push_back("ex87-1.txt");
    files.push_back("ex87-2,txt"); // mistakes file name deliberately
    files.push_back("ex87-3.txt");
    vector<string>::const_iterator it = files.begin();
    while (it != files.end()) {
        input.open(it->c_str());
        if (!input) {
            cerr << "File "
                 << *it << " cannot be opened."
                 << endl;
            // input.clear(); // no need to clear the stream
            ++it;
            continue;
        }
        printWhatYouEnter(input);
        input.close();
        input.clear();
        ++it;
    }
    return 0;
}

// $ cat ex87-1.txt
// This is file ex87-1.txt
// $ cat ex87-2.txt
// This is another file, but named ex87-2.txt
// $ cat ex87-3.txt
// Ok, this is the last file ex87-3.txt
```