# Lesson: Prefix Sum

Source: Trương Phước Hải


## I. What is Prefix Sum ?

A **prefix sum array** is a data structure that stores the cumulative sum of elements in a set, starting from the first element.  
It allows **efficient computation of the sum of a consecutive group of elements**.


## II. Prefix Sum Array on a Sequence

Consider a sequence of values `a0, a1, ..., an`.  
The sequence of values `s0, s1, ..., sn` is defined as:  

```text
    s0 = 0
    si = a0 + a1 + ... + ai
```
Then `s0, s1, ..., sn` is called the one-dimensional prefix sum array of `a1, a2, ..., an`.
Constructing a prefix sum array

```text
    si = a1 + a2 + ... + ai-1 + ai
    si = (a1 + a2 + ... + ai-1) + ai
    si = (si-1) + ai
```

Coding a prefix sum array on a sequence:
```cpp
    int s[0] = 0;
    for(int i = 1; i <= n; ++i)
        s[i] = s[i - 1] + a[i];
```
Complexity: O(n)


## III. Prefix Sum Array on a Matrix

Consider a rectangular matrix 𝐴 with n rows and m columns. The element at row i, column j has the value `aij`, where `1 <= i <= n` and `1 <= j <= m`.
The matrix 𝑆 is called the two-dimensional prefix sum array of the matrix 𝐴
Formula for calculating a two-dimensional prefix sum array
```text
    s[i][j] = s[i][j - 1] + s[i - 1][j] - s[i - 1][j - 1] + a[i][j]
```

Constructing a two-dimensional prefix sum array
```cpp
    s[i][j] = 0;
    for (int i = 1; i <= n; ++i)
        for (int j = 1; j <= m; ++j)
            s[i][j] = s[i][j-1] + s[i-1][j] - s[i-1][j-1] + a[i][j];
```
Complexity: O(m x n)

