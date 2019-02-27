---
title: 'Algorithm 1: Find max interval'
date: 2019-02-27 11:40:24
tags: enumerate answer
categories: Algorithm
---
## Problem Description:
Given an array a, you need to find maximum j - i that a[i] < a[j].

## Solutions:

### Naive
For each pointer r from end to start, find the target pointer l. Update the max interval during the process.
**Time**: O(n^2) | **Space**: O(1)

### Better:
* step 1: Create an array p, p[i] means the minum between a[0, i]
* step 2: Enumerate the answer *interval* from 0; First find the max interval end with end of a (a[r], r = n-1，l = r - curent_interval -1). Then try to find the greater interval by moving r and l to left.




``` cpp
int find_max_interval(const vector<int>& a){
	int n = a.size();
	int interval = 0;
	int p[n];
	for(int i=0; i<n; ++i){// p[i] means the minimum element in pre i elements.
		p[i] = (i==0 || a[i] < p[i-1]) ? a[i] : p[i-1];
	}
	for(int j=n-1; j>interval; --j){
		while(j>interval && a[j] >= p[j-interval-1])
			++interval;
	}
	return interval;
}
```


