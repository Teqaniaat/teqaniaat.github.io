## أكبر محصلة ضرب
### الاستنتاج الأول
إذا وجدنا العددين: $x$, $y$, فإن الأفضل دائمًا ترتيب خاناتيهما

**الفكرة:**

1- نرتب الخانات تنازليًّا
2- نضع الخانة في العدد الأصغر حاليًا
3- عندما ننتهي من وضع الخانات، نضرب العددين باستعمال أي موقع يتحمل هذا العدد الكبير من الخانات
4- نحسب باقي القسمة من $998244353$

<details>
  <summary>الحل باستعمال بايثون</summary>

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
print((x*y)%MOD)
```

</details>

<details>
  <summary>الحل باستعمال С++</summary>

```cpp
#include <bits/stdc++.h>
using namespace std;

const int MOD = 998244353;

long long strMod(string& s)
{
    long long sum = 0;
    for (int i = 0; i < s.size(); i++)
    {
        sum *= 10;
        sum += s[i] - '0';
        sum %= MOD;
    }
    return sum;
}

int main() {
    vector<int> a;
    string input;
    getline(cin, input);
    stringstream ss(input);
    int num;
    while (ss >> num) {
        a.push_back(num);
    }

    sort(a.begin(), a.end(), greater<int>());

    string x = "", y = "";
    for (int i : a) {
        if (x.size() < y.size() || (x.size() == y.size() && x < y)) {
            x = x + to_string(i);
        }
        else {
            y = y + to_string(i);
        }
    }
    cout << x << endl;
    cout << y << endl;
    long long xx = strMod(x), yy = strMod(y);
    cout << (xx * yy) % MOD;
}
```

</details>