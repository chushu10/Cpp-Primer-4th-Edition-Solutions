# Exercise 14.27

Discuss the pros and cons of allowing an empty array argument to the `CheckedPtr` constructor.

**Answer**:

- Pros: Don't need to check whether the array is empty or not. The code deals with general situations.
- Cons: We must check that `curr` not equals `end` when we dereference `curr`. It seems that we delay the check from when we initialize the array to when we use the elements of the array.