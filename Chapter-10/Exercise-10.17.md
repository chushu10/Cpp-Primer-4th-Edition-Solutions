# Exercise 10.17

Our transformation program uses find to look for each word: `map<string, string>::const_iterator map_it = trans_map.find(word);` Why do you suppose the program uses `find`? What would happen if it used the subscript operator instead?

**Answer**:

Because we don't want to accidentally insert a key-value pair into the `map` if the key doest not exist in the `map`. What would happen has been explained ahead.