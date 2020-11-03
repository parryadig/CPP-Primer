**Exercise 9.14**: Write a program to assign the elements from a list of
char* pointers to C-style character strings to a vector of strings.
````
#include <iostream>
#include <vector>
#include <list>
#include <array>

int main() {
    std::list<const char*> oldStyle = {"Snare", "Hihat", "Kick", "Perc"};
    std::vector<std::string> newStyle;
    
    newStyle.assign(oldStyle.begin(), oldStyle.end());
    
    for (auto elem: newStyle) {
        std::cout << elem << "\n";
    }
    
    return 0;
}
````
