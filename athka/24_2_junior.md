---
title: 'حلول اختبار المرحلة الأولى (المرحلة الثانوية)'
description: 'أذكى 2024 باللغتين: C++ وبايثون'
lang: ar
layout: athka
usemathjax: true
---
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


## حديقة
مجموع كل عدد بعد تربيعه، رياضيًا:
$$\sum{ (a_i^2) }$$

الحل باستعمال بايثون:
```py
a = list(map(int, input().strip().split()))
sum = 0
for i in a:
    sum += i*i
print(sum)
```
