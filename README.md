# HackerRank
Hacker Challenge
## Abstract Classes - Polymorphism

This is a cache problem. One of the popular cache replacement policies is: "least recently used" (LRU). It discards the least recently used items first if the cache reaches it's capicity. 

Based on the problem design, https://www.hackerrank.com/challenges/abstract-classes-polymorphism/problem, we need set value into given key position, therefore, I choose "deque" over "vector" for the cache. Because of deque is easlier to insert value into any position. Vector will need breakdown to two parts at insert point, then join the two parts and new insert value all together. 

Since there is constraints for command lines, cache capacity, key range and value range. I did some housekeep to ensure the value input within the constraints. 

See attached .cpp file for your review. 
```
class LRUCache{
public:
	deque<pair<int,int> >value;
	int cp;
	LRUCache(const int &x){cp=x;}
	int get(int x){
		for(int i=0;i<value.size();i++)if(value[i].first==x)return value[i].second;
		return -1;
	}
	void set(int x,int y){
		int i=0;
		for(;i<value.size();i++)
		    if(value[i].first==x){
		        value.erase(value.begin()+i);
		        break;
		    }
		if(i==cp)value.pop_back();
		value.push_front(make_pair(x,y));
	}
};
```

I like another approach too:
```
class LRUCache {
public:
	map<int, int> mp;
	LRUCache(int x) {}
	int get(int key) {
		if (mp.count(key)) return mp[key];
		return -1;
	}
	void set(int key, int val) {
		mp[key] = val;
	}
};
```
