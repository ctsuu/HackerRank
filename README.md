# HackerRank
Hacker Challenge
## Abstract Classes - Polymorphism

This is a cache problem. One of the popular cache replacement policies is: "least recently used" (LRU). It discards the least recently used items first if the cache reaches it's capicity. 

Based on the problem design, https://www.hackerrank.com/challenges/abstract-classes-polymorphism/problem, we need set value into given key position, therefore, I choose "deque" over "vector" for the cache. Because of deque is easlier to insert value into any position. Vector will need breakdown to two parts at insert point, then join the two parts and new insert value all together. 

Since there is constraints for command lines, cache capacity, key range and value range. I did some housekeep to ensure the value input within the constraints. 

See attached .cpp file for your review. 
