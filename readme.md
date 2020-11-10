Cheatsheet
==========

## Motivation
This is writen to help me recoginize some syntax and concept when I brush leetcode.


# C++

- [lambda function](https://en.cppreference.com/w/cpp/language/lambda)




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
  - [defaultdict](https://docs.python.org/zh-tw/3/library/collections.html#collections.defaultdict) :  
  ```python
  d = defaultdict(list)
  ```
  - [Counter](https://docs.python.org/zh-tw/3/library/collections.html#collections.Counter) :  
  ```python
  collections.Counter((a, b) for a in A for b in B)
  ```

## Some impressive syntatic trick example
``` python
return ans or [0]  # avoid None
```


# Some logical mistakes I may make

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
- [835. Image Overlap](https://leetcode.com/problems/image-overlap/discuss/130623/C%2B%2BJavaPython-Straight-Forward)  
Instead of brute force solutions, we can make the use of sparsity to reduce complexity.


- [1493. Longest Subarray of 1's After Deleting One Element](https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/discuss/708112/JavaC%2B%2BPython-Sliding-Window-at-most-one-0) 
we don't need to mantain the last pos of 0 and do max() in each loop. Shrinking the size of j-i is not necessary.

- [1029. Two City Scheduling](https://leetcode.com/problems/two-city-scheduling/)  
  We can solve this question in two different perspective. 
  - 1. Sort by cost diff first, then set users. It's because the less cost diff means less influence to the sum cost.
  - 2. Or we can arrange all people to the city A first and compute the sum cost. Then pick half of the people which have more refund and return ` sum - refund of half of the people`
