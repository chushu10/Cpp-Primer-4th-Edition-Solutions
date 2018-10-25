# Exercise 10.20

List at least three possible applications in which the `map` type might be of use. Write the definition of each `map` and indicate how the elements are likely to be inserted and retrieved.

**Answer**:

1. Word transformation: `map<string, string> trans;`, `trans.insert(make_pair(s1, s2));`, `trans.find(key);`
2. Item price list: `map<string, double> list;`, `list.insert(make_pair(s, d));`, `list.find(item);`
3. Fahrenheit to Celsius: `map<int, int> temp;`, `temp.insert(make_pair(fah, cel));`, `temp.find(fah);`, in this case, we can manually set all mappings from Fahrenheit to Celsius, which seems silly, but will save CPU time at the cost of RAM space.