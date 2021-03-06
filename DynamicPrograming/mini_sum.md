#### 题目描述
给定一长度为N的整数序列(a1,a2,…,aN)，将其划分成多个子序列（此问题中子序列是连续的一段整数）  
满足每个子序列中整数的和不大于一个数B，设计一种划分方法，最小化所有子序列中最大值的和  
说明其具有优化子结构及子问题重叠性质  
例如：序列长度为8的整数序列(2,2,2,8,1,8,2,1)，B=17  
可将其划分成三个子序列(2,2,2)，(8,1,8)以及(2,1)  
则可满足每个子序列中整数和不大于17，所有子序列中最大值的和12为最终结果

#### 解题思路
设`A[i,j] = (ai,a[i+1],...,aj)`，`sum(i,j)`表示`A[i,j]`在某种划分下所有子序列最大值的最小和  
在`k(i<=k<j)`处划分出一个子序列，得到`A[i,k]`，则  
`sum(i,j) = min(max(A[i,k]) + sum(k+1,j), sum(i,j)) ,    max(A[i,k]) < B, 1 <= i <= j <= n, i <= k < j`  
`sum(1,n) = min(max(A[1,k]) + sum(k+1,n), sum(1,n)) ,    max(A[1,k]) < B, 1 <= k < n, n >= 1`  
`sum(1,n)`的最优解包含`sum(k+1,n)`的最优解，  
问题的最优解包含子问题的最优解，且划分的子问题具有重叠性

#### 代码实现
[code](DynamicPrograming/mini_sum.cpp)
```

```