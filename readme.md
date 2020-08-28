Cheatsheet
==========

## Motivation
This is writen to help me recoginize some syntax and concept when I brush leetcode.


# C++





# python

## Important libraries :
- [re](https://docs.python.org/3/library/re.html#module-re)
  - split():  
    The differences w/wo parenthesis:  
    ```python
    print(re.split(r'(\(.*\))', 'abc(>_<)')) #['abc', '(>_<)', '']
    print(re.split(r'\(.*\)', 'abc(>_<)')) #['abc', '']
    ```
  
- [collections](https://docs.python.org/zh-tw/3/library/collections.html#module-collections)
  - [defaultdict](https://docs.python.org/zh-tw/3/library/collections.html#collections.defaultdict) : `d = defaultdict(list)`




# Some logic mistakes I may make

- [Coin Change 2](https://leetcode.com/problems/coin-change-2/discuss/176706/Beginner-Mistake%3A-Why-an-inner-loop-for-coins-doensn't-work-Java-Soln)
The difference between iterating coins at inner loop and outer loop: 
let's observe the value in dp ( dp[i] represents number of the ways to amount i)
Ex: amount=3, coins = [1,2]

outer loop:
  ```
  [1,0,0,0] - no coin
  [1,1,0,0] - 1
  [1,1,1,1] - 2
  ```
inner loop:
  ```
  [1,0,0,0] - amount=0
  [1,1,0,0] - amount=1 ( coin=1 meets the condition)
  [1,1,2,0] - 2 ( 0+2,1+1)
  [1,1,2,3] - 3 ( 1+2,2+1) --> This considers all combination of 3  ((1+2),((1+1+1,2+1))) (double count)
  ```


# Mind blowing solutions

- [1493. Longest Subarray of 1's After Deleting One Element](https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/discuss/708112/JavaC%2B%2BPython-Sliding-Window-at-most-one-0) 
we don't need to mantain the last pos of 0 and do max() in each loop. Shrinking the size of j-i is not necessary.
