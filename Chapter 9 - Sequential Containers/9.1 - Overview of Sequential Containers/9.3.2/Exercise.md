## Exercises Section 9.3.2
**Exercise 9.23:** In the first program in this section on page 346, what would
the values of val, val2, val3, and val4 be if c.size() is 1?
**All 4 will be equal to eachother.**

**Exercise 9.24:** Write a program that fetches the first element in a vector
using at, the subscript operator, front, and begin. Test your program on
an empty vector.
````
#include <iostream>
#include <vector>

int main()
{
    std::vector<int> v;
    std::cout << v.at(0);       // std::out_of_range
    std::cout << v[0];          // Segmentation fault: 11
    std::cout << v.front();     // Segmentation fault: 11
    std::cout << *v.begin();    // Segmentation fault: 11
    return 0;
}
````
