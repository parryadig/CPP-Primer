## Exercises Section 9.2.1
**Exercise 9.3:** What are the constraints on the iterators that form iterator
ranges?

**They may only point to elements of, or one past the end of, the container.**

**Exercise 9.4:** Write a function that takes a pair of iterators to a
vector<int> and an int value. Look for that value in the range and return
a bool indicating whether it was found.
````
#include <list> 
#include <deque>
#include <vector>

using namespace std;

bool isInVec(vector<int>::iterator begin, vector<int>::iterator end, int val) {
    for (auto it = begin; it != end; it++) {
        if (*it == val) { return 1; }
    }
    return 0;
};
````

**Exercise 9.5:** Rewrite the previous program to return an iterator to the
requested element. Note that the program must handle the case where the
element is not found.
````
#include <list> 
#include <deque>
#include <vector>

using namespace std;

vector<int>::iterator isInVec(vector<int>::iterator begin, vector<int>::iterator end, int val) {
    for (auto it = begin ; it != end ; it++) {
        if (*it == val) { return it; }
    }
    return end;
};
````

**Exercise 9.6:** What is wrong with the following program? How might you
correct it?
````
list<int> lst1;
list<int>::iterator iter1 = lst1.begin(),
iter2 = lst1.end();
while (iter1 < iter2) /* ... */
````
**A list does not support random access and thus its iterators are not relationally comparable.
This can be fixed by using !=, as all iterators are equality comparable.**

