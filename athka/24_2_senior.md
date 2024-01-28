---
title: 'حلول اختبار المرحلة الأولى (المرحلة الثانوية)'
description: 'أذكى 2024 باللغتين: C++ وبايثون'
lang: ar
layout: athka
usemathjax: true
---

{% include /athka/authors.md %}

{% include athka-tgchannel.html %}

## جدول المسائل
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


{% include /athka/garden.md %}

## كسر الهبوط
الحل باستعمال بايثون:
```py
arr = [2]*99
arr.append(1)
for i in arr:
    print(i, end=' ')
```

## تلوين الحاويات
الحل باستعمال C++
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

{% include /athka/biggest-product.md %}

{% include /athka/keyboad.md %}