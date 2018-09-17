# Exercise 8.11

In the `open_file` function, explain why we call `clear` before the call to `open`. What would happen if we neglected to make this call? What would happen if we called `clear` after the `open`?

**Answer**:

```cpp
ifstream& open_file(ifstream &in, const string &file)
{
    in.close();
    in.clear();
    in.open(file.c_str());
    return in;
}
```

When we encounter end-of-file, or any other error, the internal state of the stream is set so that further reads or writes are not allowed. If the last read or write operation failed, the state of the object remains in a failure mode until we execute `clear` to reset the condition of the stream (Section 8.4.1, p. 295).