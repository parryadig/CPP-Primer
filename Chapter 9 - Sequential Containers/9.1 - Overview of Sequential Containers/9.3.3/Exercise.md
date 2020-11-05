## Exercises Section 9.3.3

**Exercise 9.25:** In the program on page 349 that erased a range of
elements, what happens if elem1 and elem2 are equal? What if elem2 or
both elem1 and elem2 are the off-the-end iterator?
**If elem1 and elem2 are equal, then no element will be removed from the container. 
If elem2 or both elem1 and elem2 are the off-the-end iterator,then all elements from 
elem1 to the last element in the container will be removed and an iterator pointing to 
the off-the-end iterator will be returned.**

**Exercise 9.26:** Using the following definition of ia, copy ia into a vector
and into a list. Use the single-iterator form of erase to remove the
elements

''''
#include <iostream>
#include <list>
#include <vector>

int main()
{
    int ia[] = { 0, 1, 1, 2, 3, 5, 8, 13, 21, 55, 89 };
    std::vector v(std::begin(ia), std::end(ia));
    std::list l(std::begin(ia), std::end(ia));
    
    for (auto itr = begin(v) ; itr != end(v) ;) {
        if (*itr % 2 == 0) { itr = v.erase(itr); }
        else { itr++; }
    }
    
    for (auto itr = begin(l) ; itr != end(l) ;) {
        if (*itr % 2 != 0) { itr = l.erase(itr); }
        else { itr++; }
    }
    
    for (auto elem: v) {
        std::cout << elem << " ";
    }
    std::cout << "\n";
    
    for (auto elem: l) {
        std::cout << elem << " ";
    }
    std::cout << "\n";
    
    return 0;
}
''''

