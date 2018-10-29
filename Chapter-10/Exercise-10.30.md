# Exercise 10.30

The member functions of `TextQuery` use only capabilities that we have already covered. Without looking ahead, write your own versions of the member functions. Hint: The only tricky part is what to return from `run_query` if the line number set is empty. The solution is to construct and return a new (temporary) `set`.

**Answer**:

```cpp
#include "text_query.h"
#include <sstream>

std::set<TextQuery::line_no> TextQuery::run_query(const std::string& word) const
{
    return (word_map.find(word))->second;
}

std::string TextQuery::text_line(line_no line_num) const
{
    return lines_of_text[line_num - 1];
}

void TextQuery::store_file(std::ifstream& in)
{
    std::string line;
    while (std::getline(in, line)) {
        lines_of_text.push_back(line);
    }
}

void TextQuery::build_map()
{
    typedef std::map< std::string, std::set<line_no> >::iterator map_it;
    for (line_no i = 0; i != lines_of_text.size(); ++i) {
        std::string word;
        std::istringstream is(lines_of_text[i]);
        while (is >> word) {
            map_it it = word_map.find(word);
            if (it != word_map.end()) {
                (it->second).insert(i + 1);
            } else {
                std::set<line_no> line_set;
                line_set.insert(i + 1);
                word_map.insert(std::make_pair(word, line_set));
            }
        }
    }
}
```