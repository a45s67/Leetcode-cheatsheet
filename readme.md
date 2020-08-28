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

- [518. Coin Change 2](https://leetcode.com/problems/coin-change-2/discuss/176706/Beginner-Mistake%3A-Why-an-inner-loop-for-coins-doensn't-work-Java-Soln)
  The difference between iterating coins at inner loop and outer loop:  
  Let's observe the value in dp ( dp[i] represents number of the ways to amount i)  
  Ex: amount=3, coins = [1,2]

  iterate coins first:

      [1,0,0,0] - start
      [1,1,0,0] - coin = 1
      [1,1,1,1] - coin = 2

  iterate amounts first:

      [1,0,0,0] - start
      [1,1,0,0] - amount=1 ( coin=1 meets the condition)
      [1,1,2,0] - 2 ( amount 0 + coin 2 , amount 1 + coin 1)
      [1,1,2,3] - 3 ( amount 1 + coin 2 , amount 2 + coin 1) --> This considers all combination of 3  ((1+2),((1+1+1,2+1))), which causes double count in this question.


# Mind blowing solutions

- [1493. Longest Subarray of 1's After Deleting One Element](https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/discuss/708112/JavaC%2B%2BPython-Sliding-Window-at-most-one-0) 
we don't need to mantain the last pos of 0 and do max() in each loop. Shrinking the size of j-i is not necessary.
