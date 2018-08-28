# Exercise 7.13

Write a program to calculate the sum of the elements in an array. Write the function three times, each one using a different approach to managing the array bounds.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

// C-style character string approach
void printArray(const int ia[]) {
    int i = 0;
    while (ia[i] != 9999) { // 9999 is the sentinel
        cout << ia[i++] << " ";
    }
    cout << endl;
}

// Standard library approach
void printArray(const int *beg, const int *end) {
    while (beg != end) {
        cout << *beg++ << " ";
    }
    cout << endl;
}

// Size parameter appoach
void printArray(const int ia[], size_t size) {
    for (size_t i = 0; i != size; ++i) {
        cout << ia[i] << " ";
    }
    cout << endl;
}

int main(int argc, char const *argv[])
{
    int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int arr2[11] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 9999};
    printArray(arr2);
    printArray(arr, 10);
    printArray(arr, arr + 10);
    return 0;
}

```