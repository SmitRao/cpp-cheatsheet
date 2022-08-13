```
Ideas: 
    read-only -> pass by reference
    premature optimization is bad
    opt for references over pointers, unless using classes

Stdin/stdout:
#include <iostream>

Keywords:
    > constexpr (compile-time sub func val)
    > int GetX() const {}
    > mutable int var;                                  // can be modified even in const func.
    > void PerformOperation(const Entity& e) {}         // param is read-only

Templates: dynamic typing -> T can be string, float, etc. (generic)
// only creates template when called
// not advisable since it makes code hard to interpret when compiled...
    > template<typename T>
      void PerformOps(T value) {
          ...
      }

Macros:
#define REMOVE_ALL(v, item) v.erase(std::remove(v.begin(), v.end(), item), v.end()) // include algorithm
#define FULL_RANGE(x) x.begin(), x.end()

All Containers:
    > size()
    > empty()

Arrays:
#include <vector>
    > void push_back(x)
    > void pop_back()
    > T back()
    > T front()

Sets:
#include <set>                     // O(log n) -> BST
#include <unordered_set>           // O(1) avg case...            O(n) wst case
    > s.insert(x)
    > s.erase(x)
    > s.find(x) == s.end() ? ...
    > s.count(x)                   // useful for checking if something is in set
    > set<int> s;
      unsigned size = vec.size();
      for( unsigned i = 0; i < size; ++i ) s.insert( vec[i] );
      vec.assign( s.begin(), s.end() ); // remove duplicates from vector

Dictionaries:
#include <map>                     // O(log n) -> BST
#include <unordered_map>           // O(1) avg case...            O(n) wst case
    > s.insert(x)
    > s.erase(x)
    > s.find(x) == s.end() ? ...
    > s.count(x)                   // useful for checking if something is in map
    > for (auto it = freq.begin(); it != freq.end(); ++it) {
        auto key = it->first;
        auto val = it->second;
      }
#include <unordered_multimap>
    > auto range = myumm.equal_range("strawberry");
      for_each (
        range.first,
        range.second,
        [](unordered_multimap<string, string>::value_type& x){std::cout << " " << x.second;}
      );

Stack:
#include <stack>
    > push(x)
    > pop()
    > top()

Queue:
#include <queue>
    > push(x)
    > pop()
    > front()
    > back()

Max Binary Heap:
#include <priority_queue>
    > push(x)                      // O(log n)
    > pop()                        // O(log n)
    > top()

Min Binary Heap --> std::priority_queue<int, std::vector<int>, std::greater<int>>()
#include <priority_queue>
#include <vector>
#include <functional>
    > push(x)                      // O(log n)
    > pop()                        // O(log n)
    > top()

Pairs: pair<T1, T2> pairName(T1_arg, T2_arg)
#include <utility>
    > pairName.first
    > pairName.second

Algorithms:
#include <algorithm>
    > std::sort(vec.begin(), vec.end(), [](int x, int y){return x < y;})
    > std::copy_if(foo.begin(), foo.end(), bar.begin(), [](int i){return !(i<0);}) // like filter
    > std::find_if (myvector.begin(), myvector.end(), IsOdd) // get iterator where predicate first true
    > std::binary_search(v.begin(), v.end(), item) // returns true if item in sorted vector v
    > std::is_sorted(foo.begin(),foo.end())
    > std::is_permutation (foo.begin(), foo.end(), bar.begin())
    > std::min_element(foo.begin(), foo.end())
    > do {
        perms.push_back(arr);
      } while (std::next_permutation(arr.begin(), arr.end()));

#include <iterator>     // std::advance
    > std::advance (it,5);


Graphs (simple): vector<vector<int>> g; // -> adj. matrix
    > path-finding / shortest path stuff: use BFS
    > just visiting ALL nodes: use DFS
    > topological sort: maybe DFS?

Statistics (distributions, generators): #include <random>

Smart pointers:
#include <memory>
    > std::unique_ptr<T> uniquePtr = std::make_unique<T>()
    > std::shared_ptr<T> sharedPtr = ... " " " ...
    > std::weak_ptr<T> weakPtr = sharedPtr

Function pointer --> int (*funcPtr)()

Read-only params --> func(const T & param1)

Include whole std lib (increases compile time!):
#include <bits/stdc++.h>
using namespace std;

Enums:
    > enum Suit { Diamonds, Hearts, Clubs, Spades };

Classes:
    > virtual keyword makes interface
    > explicit keyword helpful for constructors callable with 1 arg:
        explicit Foo(const int v) : data(v) {}
    > use destructors for polymorphic classes:
        ~Shape() { delete ... }

Two dimensional array:
    > int two_d[10][20];

#undef: Un-defines a text macro
#ifdef: Same as #if defined(...)
#ifndef: Same as #if !defined(...)
#endif: Used to end an #if, #ifdef, or #ifndef

#include <locale>
isspace
Check if character is a white-space (function )
isprint
Check if character is printable (function )
iscntrl
Check if character is a control character (function )
isupper
Check if character is uppercase letter (function )
islower
Check if character is lowercase letter (function )
isalpha
Check if character is alphabetic (function )
isdigit
Check if character is decimal digit (function )
ispunct
Check if character is a punctuation character (function )
isxdigit
Check if character is hexadecimal digit (function )
isalnum
Check if character is alphanumeric (function )
isgraph
Check if character has graphical representation (function )
isblank 
Check if character is blank (function )

For set, multiset, map, multimap the time complexity for insertion, deletion 
and retrieving information is O(logn) as they follow the balance binary tree
```
