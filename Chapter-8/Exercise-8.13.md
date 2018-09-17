# Exercise 8.13

Write a program similar to `open_file` that opens a file for output.

**Answer**:

```cpp
ifstream& open_file_for_output(ifstream &in, const string &file)
{
    in.close();
    in.clear();
    in.open(file.c_str(), ofstream::out);
    return in;
}
```