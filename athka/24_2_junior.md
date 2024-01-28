---
title: 'حلول اختبار المرحلة الأولى (المرحلة المتوسطة)'
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
   <td>حركة الروبوت</td>
   <td>2</td>
   <td>16</td>
   </tr>
   <tr>
   <td>ترتيب سري</td>
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

## حركة الروبوت
```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n = 500, x, v=0, h=0;
    while (n--) {
        cin >> x;
        if (x == 1) h++;
        if (x == 2) v++;
        if (x == 3) h--;
        if (x == 4) v--;
    }
    cout << "Up: " << v << endl;
    cout << "Right: " << h << endl; 
}
```


## ترتيب سري
```cpp
#include <bits/stdc++.h>
using namespace std;

int n = 10, q[100], p[100];
int main()
{
    for (int i = 0; i < n; i++) {
        cin >> q[i];
        p[q[i]] = i;
    }
    for (int i = 0; i < n; i++) {
        cout << p[i] << ' ';
    }
}
```

{% include /athka/biggest-product.md %}

{% include /athka/keyboard.md %}