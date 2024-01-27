---
title: 'حلول اختبار المرحلة الأولى (المرحلة الثانوية)'
description: 'أذكى 2024 باللغتين: C++ وبايثون'
lang: ar
layout: athka
usemathjax: true
---
## Exam
<table>
  <thead>
   <th>اسم المسألة</th>
   <th>عدد المسائل الفرعية</th>
   <th>الدرجة الكلية</th>
  </thead>
  <tbody>
   <tr>
   <td>حديقة</td>
   <td>1</td>
   <td>12</td>
   </tr>
   <tr>
   <td>كسر الهبوط</td>
   <td>2</td>
   <td>16</td>
   </tr>
   <tr>
   <td>تلوين الحاويات</td>
   <td>2</td>
   <td>23</td>
   </tr>
   <tr>
   <td>أكبر محصلة ضرب</td>
   <td>3</td>
   <td>28</td>
   </tr>
   <tr>
   <td>لوحة المفاتيح</td>
   <td>1</td>
   <td>21</td>
   </tr>
  </tbody>
</table>


## A
Sum of every element squared
$$\sum{ (a_i^2) }$$

## B
```py
arr = [2]*99
arr.append(1)
for i in arr:
    print(i, end=' ')
```

## C
C++ Code
```cpp
#include <bits/stdc++.h>
using namespace std;

int n, m, g[35][35];
int main()
{
    cin >> n >> m;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
        {
            cin >> g[i][j];
        }
    }
    int sol = 0;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= m; j++)
        {
            if (g[i][j]) sol++; // top
            sol += max(g[i][j] - g[i+1][j], 0);
            sol += max(g[i][j] - g[i-1][j], 0);
            sol += max(g[i][j] - g[i][j+1], 0);
            sol += max(g[i][j] - g[i][j-1], 0);
        }
    }
    cout << sol;
}
```

## D
### Observation 1
If we had two numbers: $x$, $y$, always it's optimal to sort their digits

## Observation 2
Maximum sum will happen when $x$, $y$ are as near as possible to each other

Python code:
```py
MOD = 998244353

a = list(map(int, input().strip().split()))
a.sort()
a.reverse()
x=0
y=0
for i in a:
    if x < y:
        x *= 10
        x += i
    else:
        y *= 10
        y += i
print(x)
print(y)
print((x*y)%MOD)
```

## E
Approuches:
- Sort by frequency ~36k
- Keyboard order same as text ~35
- Sort by frequency as a pyramid ~30k
- Randomization ~32.5k