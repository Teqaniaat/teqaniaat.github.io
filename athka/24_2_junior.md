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
**الفكرة:** تنفيذ معطيات المسألة بالضبط، تحريك الروبوت كل مرة
<details>
  <summary>الحل باستعمال بايثون</summary>

```py
q = list(map(int, input().split()))
h = 0
v = 0
for x in q:
    if x == 1:
        h+=1
    if x == 2:
        v+=1
    if x == 3:
        h-=1
    if x == 4:
        v-=1
print("Up:" << v)
print("Right:" << h)
```

</details>

<details>
  <summary>الحل باستعمال <span dir="ltr">C++</span></summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x, v=0, h=0;
    string input;
    getline(cin, input);
    stringstream ss(input);
    while (ss >> x) {
        if (x == 1) h++;
        if (x == 2) v++;
        if (x == 3) h--;
        if (x == 4) v--;
    }
    cout << "Up: " << v << endl;
    cout << "Right: " << h << endl; 
}
```

</details>



## ترتيب سري
**الفكرة:** فيما نلاحظ أن التغيير سيحدث بالطريقة التالية: كل رقم سيؤثر على الخانة التي تحمل نفس الرقم، رقم 3 سيغير المكان الثالث. وقيمة التغيير تكون بالمكان الحالي 

<details>
  <summary>الحل باستعمال بايثون</summary>

```py
q = list(map(int, input().split()))
p = [0] * len(q)

for i in range(n):
    p[q[i]] = i

for i in range(n):
    print(p[i], end=' ')
```

</details>

<details>
  <summary>الحل باستعمال <span dir="ltr">C++</span></summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

int n = 0, q[100], p[100];
int main()
{
    string input;
    getline(cin, input);
    stringstream ss(input);
    while (ss >> q[i]) {
        n++;
        cin >> q[i];
        p[q[i]] = i;
    }
    for (int i = 0; i < n; i++) {
        cout << p[i] << ' ';
    }
}
```

</details>

{% include /athka/biggest-product.md %}

{% include /athka/keyboard.md %}