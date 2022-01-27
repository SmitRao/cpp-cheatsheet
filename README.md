# cpp-cheatsheet
```
Remember: 
    read-only -> pass by reference
    premature optimization is bad
    opt for references over pointers, unless using classes

Stdin/stdout:
#include <iostream>

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

Dictionaries:
#include <map>                     // O(log n) -> BST
#include <unordered_map>           // O(1) avg case...            O(n) wst case
    > s.insert(x)
    > s.erase(x)
    > s.find(x) == s.end() ? ...
    > s.count(x)                   // useful for checking if something is in map

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
    > std::find_if (myvector.begin(), myvector.end(), IsOdd) // get index where predicate first true
    > std::binary_search(v.begin(), v.end(), item) // returns true if item in sorted vector v
    > std::is_sorted(foo.begin(),foo.end())
    > std::is_permutation (foo.begin(), foo.end(), bar.begin())
    > std::min_element(foo.begin(), foo.end())
    > do {
        perms.push_back(arr);
      } while (std::next_permutation(arr.begin(), arr.end()));

Graphs (simple): vector<vector<int>> g;

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

#undef: Un-defines a text macro
#ifdef: Same as #if defined(...)
#ifndef: Same as #if !defined(...)
#endif: Used to end an #if, #ifdef, or #ifndef
```
