# Exercise 15.40

For the expression built in Figure 15.4 (p. 612)
a. List the constructors executed in processing this expression.

```cpp
Query q = Query("fiery") & Query("bird") | Query("wind");
```

b. List the calls to `display` and to the overloaded `<<` operator that are made in executing `cout << q`.
c. List the calls to `eval` made when evaluating `q.eval`.

**Answer**:

a. 
1. Three calls to `WordQuery` constructor, the parameters are "fiery", "bird" and "wind".
2. Two calls to `BinaryQuery` constructor, the parameters are `Query("fiery")` with `Query("bird")` and `Query("wind")` with `Query(AndQuery(Query("fiery"), Query("bird")))`.
3. One call to `AndQuery` constructor, the parameters are `Query("fiery")` and `Query("bird")`.
4. One call to `OrQuery` constructor, the parameters are `Query("wind")` and `Query(AndQuery(Query("fiery"), Query("bird")))`
b. 