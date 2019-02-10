# Exercise 15.9

Given the classes in the previous exercise and the following objects, determine which function is called at run time:

```cpp
base bobj;    base *bp1 = &base;  base &br1 = bobj; 
derived dobj; base *bp2 = &doboj; base &br2 = dobj;
```

(a) `bobj.print();` (b) `dobj.print();` (c) `bp1->name();` (d) `bp2->name();` (e) `br1.print();` (f) `br2.print();`

**Answer**:

(a) compile time;
(b) run time;
(c) compile time;
(d) compile time;
(e) run time;
(f) run time;