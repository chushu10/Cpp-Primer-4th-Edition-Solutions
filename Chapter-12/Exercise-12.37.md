# Exercise 13.37

Write your own version of the `Account` class.

**Answer**:

Consider a simple class intended to represent a bank account. Each account has a balance and an owner. Each account earns interest monthly, but the interest rate applied to each account is always the same.

```cpp
class Account {
public:
    double get_rate() { return rate; }
    double earn_interest() { balance_ += balance_ * rate_; }
    static void set_rate(double rate) { rate_ = rate; }
private:
    std::string owner_;
    double balance_;
    static double rate_;
};
```