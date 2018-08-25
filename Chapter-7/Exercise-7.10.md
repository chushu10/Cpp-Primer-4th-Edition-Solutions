# Exercise 7.10

The following program, although legal, is less useful than it might be. Identify and correct the limitation on this program:

`bool test(string& s) { return s.empty(); }`

**Answer**:

You can't call `test("")` because the non`const` reference parameter `s` cannot be initialized by literals. We might get error:

```bash
error: invalid initialization of non-const reference of type 'std::string& {aka std::basic_string&}' from an rvalue of type 'std::string {aka std::basic_string}'
cout << (test("123") ? "empty" : "not empty") << endl;
                   ^
```

Instead, use:

`bool test(const string& s) { return s.empty(); }`