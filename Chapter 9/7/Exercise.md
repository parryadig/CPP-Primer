**Exercise 9.15:** Write a program to determine whether two vector<int>s
are equal.
````
#include <iostream>
#include <vector>
#include <list>
#include <array>

bool isEqual(std::vector<int> v1, std::vector<int> v2) {
    return v1 == v2;
}

int main() {
    std::vector<int> v1{1, 2, 3, 4};
    std::vector<int> v2{1, 2, 3, 4};
    
    std::cout << isEqual(v1, v2) << "\n";
    
    return 0;
}
````
**Exercise 9.16:** Repeat the previous program, but compare elements in a
list<int> to a vector<int>.
````
bool isEqual(std::vector<int> v, std::list<int> l) {
    if (v.size() != l.size()) { return 0; }
    
    return std::vector<int>(l.begin(), l.end()) == v;
}
````

**Exercise 9.17:** Assuming c1 and c2 are containers, what (if any)
constraints does the following usage place on the types of c1 and c2?
if (c1 < c2)   
**c1 & c2 must be containers of the same type & their elements must also be of 
the same type.**
