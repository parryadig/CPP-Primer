**Exercise 9.18:** Write a program to read a sequence of strings from the
standard input into a deque. Use iterators to write a loop to print the
elements in the deque.
````
#include <iostream>
#include <deque>

int main()
{
    std::deque<std::string> words;
    
    for (std::string str; std::cin >> str; words.push_back(str));
    for (auto iter = words.cbegin(); iter != words.cend(); iter++) {
        std::cout << *iter << std::endl;
    }
    
    return 0;
}
````

**Exercise 9.19:** Rewrite the program from the previous exercise to use a
list. List the changes you needed to make.
````
#include <iostream>
#include <list>   // include header for list

int main()
{
    std::list<std::string> words;       // initialise words as a list
    
    for (std::string str; std::cin >> str; words.push_back(str));
    for (auto iter = words.cbegin(); iter != words.cend(); iter++) {    // no change required to iterator type due to auto
        std::cout << *iter << std::endl;
    }
    
    return 0;
}
````
Exercise 9.20:** Write a program to copy elements from a list<int> into
two deques. The even-valued elements should go into one deque and the
odd ones into the other.
````
#include <iostream>
#include <list>
#include <deque>

using std::list, std::deque, std::cout, std::endl;

int main()
{
    list<int> nums {1, 2, 3, 4, 5, 6, 7, 8, 9};
    deque<int> evens;
    deque<int> odds;
    
    for (auto iter = begin(nums); iter != end(nums); iter++) {
        if (*iter % 2 == 0) { evens.push_back(*iter); }
        else { odds.push_back(*iter); }
    }
    
    return 0;
}
````
**Exercise 9.21:** Explain how the loop from page 345 that used the return
from insert to add elements to a list would work if we inserted into a
vector instead.
**The code would work, however the operation is far more costly. All elements in the vector would have to be 
shifted one index to the right before pushing the value to the front, meaning a new vector will be created, & 
the contents of the previous one copied over, with every iteration of the while.
**Exercise 9.22:** Assuming iv is a vector of ints, what is wrong with the
following program? How might you correct the problem(s)?
**Currently the program loops infinitely as iter is not incremented. We must increment twice. Once in the inner
loop so that after a value is inserted iter points to the same element as before, and a second time in the outer 
while loop so that iter gradually moves to the middle.
````
while (iter != mid) {
  if (*iter == some_val) {
    iv.insert(iter, 2 * some_val);
    iter = iv.insert(iter, 2 * some_val);
    ++iter;
  }
  ++iter;
}
````

