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
