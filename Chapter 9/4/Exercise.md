## Exercises Section 9.2.4
**Exercise 9.11:** Show an example of each of the six ways to create and
initialize a vector. Explain what values each vector contains.
````
    vector<int> v0;                   // empty
    vector<int> v1{1, 2, 3, 4, 5};     // 1,2,3,4,5
    vector<int> v2(1);                // 0
    vector<int> v3(20, 2);            // 2,2,2,2,....2 (size 20)
    vector<int> v4(v2);               // copied
    vector<int> v5(v1.begin(), v1.end());   // copied
````

**Exercise 9.12:** Explain the differences between the constructor that takes a
container to copy and the constructor that takes two iterators.
**The copy constructor requires that the type of the container & it's elements must match. However, the construct that 
takes in two iterators does not require either of these to match, as long as conversion between the two element types is 
possible. The code below highlights this.**

````
    list<int> l{1,2,3,4,5};
    vector<int> v(l);    // error
    vector<int> v(l.begin(), l.end());      // 1,2,3,4,5
````

**Exercise 9.13:** How would you initialize a vector<double> from a
list<int>? From a vector<int>? Write code to check your answers.
````
    list<int> l{1,2,3,4,5};
    
    vector<double> vecFromList(l.begin(), l.end());      // 1,2,3,4,5
    
    vector<int> v{1,2,3,4,5};
    
    vector<double> vecFromVec(v.begin(), v.end());      // 1,2,3,4,5
````
