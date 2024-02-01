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
**فهم المسألة:** المطلوب منك مدخل بحيث أن الخوارزمية المعطاة لا تعمل

**الفكرة:** إذا كانت جميع الأرقام متساوية باستثناء رقم واحد، كل أماكن البداية ستعطي إجابة خاطئة باستثناء 3 أماكن بحد أقصى
<details>
  <summary>الحل باستعمال بايثون</summary>

```py
print("Subtask 1:")
print("1 2 2 2 2 2 2 2 2 2 1")

arr = [2]*99
arr.append(1)
print("Subtask 2:")
for i in arr:
    print(i, end=' ')
```

</details>

<details>
  <summary>الحل باستعمال С++</summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    cout << "Subtask 1:" << endl;
    cout << "1 2 2 2 2 2 2 2 2 2 1" << endl;

    cout << "Subtask 2:" << endl;
    for (int i = 0; i < 99; i++)
        cout << "2 ";
    cout << "1";
}
```

</details>


## تلوين الحاويات
**الفكرة:** قارن كل عمود بالأعمدة التي بجواره من الاتجاهات الأربعة، الإجابة هي مجموع الفرق بين كل عمودين إذا كان موجبًا، بالإضافة إلى السقف
<details>
  <summary>الحل باستعمال بايثون</summary>

```py
n = int(input())
g = []
for _ in range(n):
    row = list(map(int, input().split()))
    g.append(row)

sol = 0
for i in range(n):
    for j in range(n):
        if g[i][j]:
            sol += 1  # top
        sol += max(g[i][j] - g[i+1][j], 0)
        sol += max(g[i][j] - g[i-1][j], 0)
        sol += max(g[i][j] - g[i][j+1], 0)
        sol += max(g[i][j] - g[i][j-1], 0)

print(sol)
```

</details>

<details>
  <summary>الحل باستعمال C++</summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

int n, g[35][35];
int main()
{
    cin >> n;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= n; j++)
        {
            cin >> g[i][j];
        }
    }
    int sol = 0;
    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= n; j++)
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

</details>

{% include /athka/biggest-product.md %}

{% include /athka/keyboard.md %}