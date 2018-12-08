# Exercise 13.20

Given the original version of the `HasPtr` class that relies on the default definitions for copy-control, describe what happens in the following code:

```cpp
int i = 42;
HasPtr p1(&i, 42);
HasPtr p2 = p1;
cout << p2.get_ptr_val() << endl; p1.set_ptr_val(0);
cout << p2.get_ptr_val() << endl;
```

**Answer**:

```cpp
int i = 42;
HasPtr p1(&i, 42); // p1's pointer member initialized to point to 42, and its int member is 42
HasPtr p2 = p1; // p2 is copied from p1 using the default copy constructor, p2's pointer member points to the same object ad p1's, and its int member is independent
cout << p2.get_ptr_val() << endl; // prints 42
p1.set_ptr_val(0);
cout << p2.get_ptr_val() << endl; // prints 0
```