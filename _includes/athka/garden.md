## حديقة

**الفكرة:** مجموع كل عدد بعد تربيعه، رياضيًا:
$$\sum{ (a_i^2) }$$


<details>
  <summary>الحل باستعمال بايثون</summary>

```py
a = list(map(int, input().strip().split()))
sum = 0
for i in a:
    sum += i*i
print(sum)
```

</details>

<details>
  <summary>الحل باستعمال <span dir="ltr">C++</span></summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string input;
    getline(cin, input);
    stringstream ss(input);

    int sol = 0, i;
    while (ss >> i) {
        sol += i*i;
    }
    cout << sol;
}
```

</details>