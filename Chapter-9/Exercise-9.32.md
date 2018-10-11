# Exercise 9.32

Explain what the following program does:

```cpp
vector<string> svec;
svec.reserve(1024);
string text_word;
while (cin >> text_word)
        svec.push_back(text_word);
svec.resize(svec.size()+svec.size()/2);
```

If the program reads 256 words, what is its likely capacity after it is resized? What if it reads 512? 1,000? 1,048?

**Answer**:

The best way to describe a snippet of code is by commenting it:

```cpp
vector<string> svec; // create an empty vector of strings
svec.reserve(1024); // make its capacity to 1,024
string text_word; // create an empty string
while (cin >> text_word) // read the string from standard input until eof
    svec.push_back(text_word); // push the string into the vector
svec.resize(svec.size()+svec.size()/2); // resize the size of the vector to 1.5 times of current size, populate empty strings into the rear of the vector
```

If the program reads 256 words, and it was resized to 1.5 * 256 = 384, the capacity should still be 1,024 since it can hold 384 elements for the time being.
If read 512 elements, the same.
If read 1,000 or 1,048 elements, the capacity will likely to be 2 * 1,024 = 2,048. The difference is, if read 1,000 elements the capacity will not be incremented until resize; However, if read 1,048 elements, the capacity will incremented to 2,048 directly, and remain the same after resize.
