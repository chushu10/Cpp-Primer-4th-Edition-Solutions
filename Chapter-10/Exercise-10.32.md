# Exercise 10.32

Re-implement the text-query program to use a `vector` instead of a `set` to hold the line numbers. Note that because lines appear in ascending order, we can append a new line number to the `vector` only if the last element of the `vector` isn't that line number. What are the performance and design characteristics of the two solutions? Which do you feel is the preferred design solution? Why?

**Answer**:

If using `vector`, the `build_map` member function will be like this:

```cpp
void TextQuery::build_map()
{
    for (line_no i = 0; i != lines_of_text.size(); ++i) {
        std::string word;
        std::istringstream is(lines_of_text[i]);
        while (is >> word) {
            if (!word_map[word].empty()) {
                line_no last = *(word_map[word].end() - 1);
                if (last != i) {
                    word_map[word].push_back(i);
                }
            } else {
                word_map[word].push_back(i);
            }
        }
    }
}
```

Absolutely, the `set` version is much more efficient, since there will always be an empty check in the implementation of the `vector` version. I prefer `set`, because it is simpler and more efficient.