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