# Exercise 11.27

The library defines the following algorithms:

```cpp
replace(beg, end, old_val, new_val);
replace_if(beg, end, pred, new_val);
replace_copy(beg, end, dest, old_val, new_val);
replace_copy_if(beg, end, dest, pred, new_val);
```

Based only on the names and parameters to these functions, describe the operation that these algorithms perform.

**Answer**:

1. Replace the elements in the container enclosed by `beg` and `end` which are of value `old_val` to value `new_val`;
2. Replace the elements in the container enclosed by `beg` and `end` which satisfy the predicate `pred` to value `new_val`;
3. Make a copy of the container enclosed by `beg` and `end`, and replace the elements in the new container which are of value `old_val` to value `new_val`;
4. Make a copy of the container enclosed by `beg` and `end`, and replace the elements in the new container which satisfy the predicate `pred` to value `new_val`;