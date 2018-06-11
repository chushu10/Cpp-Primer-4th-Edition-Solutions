# Exercise 2.30

Define the data members of classes to represent the following types:

(a) a phone number
(b) an address
(c) an employee or a company
(d) a student at a university

**Answer**:

(a) a phone number

```cpp
// Chinese style
class Phone_num {
private:
    int country_code;
    int area_code;
    int prefix;
    std::string line_number;
}
```

(b) an address

```cpp
// Chinese style
class Address {
private:
    std::string country;
    std::string province;
    std::string city;
    std::string district;
    std::string road;
    int house_number;
}
```

(c) an employee or a company

```cpp
class Employee {
private:
    std::string name;
    long id_number; // in case of big company
    std::string office;
    std::string rank;
    double salary;
    Phone_num phone_num;
    int kpi; // ok, key performance index
}
```

```cpp
class Company {
private:
    std::string name;
    Address addr;
    int population;
    std::string industry;
}
```

(d) a student at a university

```cpp
class Student {
private:
    std::string name;
    long id_number;
    int grade;
}
```