# Exercise 5.19

Assuming that `iter` is a `vector<string>::iterator`, indicate which, if any, of the following expressions is legal. Explain the behavior of the legal expressions.

(a) `*iter++;`
(b) `(*iter)++;`
(c) `*iter.empty();`
(d) `iter->empty();`
(e) `++*iter;`
(f) `iter++->empty();`

**Answer**:

(a) `*iter++;` is legal, it is the same as `*(iter++)`, it returns the original `iter` then dereference it. After that, the `iter` is incremented by 1.
(b) `(*iter)++;` is legal, but the meaning is different from (a). It dereference `iter` first, then apply increment on the dereferenced value.
(c) `*iter.empty();` is **illegal**, because the precedence of dot is higher than dereference. `iter` has no member function named `empty()`, so we got a compile error.
(d) `iter->empty();` is legal.
(e) `++*iter;` is **illegal**, because the precedence of dereference is higher than increment. So we get a `string` type from `*iter` first, then apply increment on a `string` type which is illegal.
(f) `iter++->empty();` is legal, because the precedence of increment is higher than arrow, so we get the original version of `iter` first, then apply arrow operator on the original `iter`. We don't need to worry about visiting inexistent element, because we use postfix increment.