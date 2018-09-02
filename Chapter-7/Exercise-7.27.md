# Exercise 7.27

Explain the difference between a parameter, a local variable and a static variable. Give an example of a program in which each might be useful.

**Answer**:

- Parameter: Special local variable that are called **automatic object**(Ok, it's confusing). The memory of a parameter is created when the function is called and is freed when the function terminates.
- Local variable: The variable that is defined in the function body without the `static` keyword. The memory of a local variable is created when the function is called and is freed when the function terminates.
- Static variable: The variable that is defined in the function body with the `static` keyword. The memory of a static variable is created before the function is called and is freed when the program terminates.

Example:

```cpp
// switch_light function explanation:
// 1. Check if the user is valid
// 2. Then switch the light on when the light is off
// 2.1 Switch off when it's on
// user is the parameter
// pwd is the local variable;
// light_on is the static variable
void switch_light(User user) {
    static bool light_on = false; // light is off before the call
    string pwd = get_pwd_from_db(user->id);
    if (user->password == pwd) {
        light_on = !light_on; // switch
    }
}
```