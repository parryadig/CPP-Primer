**Exercises Section 9.3.4**

**Exercise 9.27:** Write a program to find and remove the odd-valued
elements in a forward_list<int>.

````
#include <iostream>
#include <forward_list>

int main() 
{
    std::forward_list<int> flist = {0,1,2,3,4,5,6,7,8,9};
    auto prev = flist.before_begin();
    auto curr = begin(flist);
    
    while (curr != end(flist)) {
        if (*curr % 2 != 0) {
            curr++;
            prev = flist.erase_after(prev);
        }
        
        else {
            prev = curr;
            curr++;
        }
    }
    
    for (auto elem: flist) {
        std::cout << elem << " ";
    }
    std::cout << "\n";
    
    return 0;
}

````

**Exercise 9.28:** Write a function that takes a forward_list<string> and
two additional string arguments. The function should find the first string
and insert the second immediately following the first. If the first string is
not found, then insert the second string at the end of the list.
````
#include <iostream>
#include <forward_list>

using std::forward_list, std::string;

void strFunc(forward_list<string> &fl, string s1, string s2) {
    auto prev = fl.before_begin();
    auto curr = begin(fl);
    
    while (curr != end(fl) && *curr != s1) { 
        prev = curr;
        curr++; 
    }
    // the quick brown fox
    fl.insert_after(prev, s2);
}

int main() 
{
    forward_list<string> strFlist = {"the", "quick", "brown", "fox"};
    
    strFunc(strFlist, "brown", "wild");
    
    strFunc(strFlist, "gorilla", "jumped.");
    
    for (auto elem: strFlist) {
        std::cout << elem << " ";
    }
    std::cout << "\n";    // the quick brown wild fox jumped.
    
    return 0;
}

