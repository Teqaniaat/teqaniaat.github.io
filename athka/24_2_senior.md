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

## أكبر محصلة ضرب
### الاستنتاج الأول
إذا أوجدنا العددين: $x$, $y$, فإن الأفضل دائمًا ترتيب خاناتهما

### الاستنتاج الثاني
أكبر محصلة ضرب تكون عندما يكونان $x$, $y$ أقرب لبعضهما

الحل باستعمال بايثون:
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

## لوحة المفاتيح
هذه مسألة اختصار، أي كلما وجدت حل أفضل كانت درجتك أعلى.

**بعض الأفكار المستعملة في:**
- الترتيب بناءً على تكرار الحرف (تكلفة 37567)
- ترتيب كتابة النص دون تكرار (تكلفة 36814)
- الترتيب الهرمي بناءً على تكرار الحرف (تكلفة 30530)
- الترتيب العشوائي (تكلفة 32421)
- التبديل العشوائي إذا كان يعطي نتيجة أفضل (تكلفة 27000~)

```py
from random import *
TEXT = "pUrehIC9ea2ttheJE7ovenMTVE9WYtoEGXEOoneFhXuEnd5redeightyZdINID7egFreeVsRT9MCPaFnWSd68ligFht8lyGI5gRROrJePLHS6REIQaBAseY1OanKinC3eW83K9OhGundRreQdVg3CIZ7EZPTXrQR3aQmZsloKFafNtFY7i77nOINSf0DortDZQhEe4AshawarmaGm3TZiExtUXCRoJg9etZherLXthJe2cPFL8ornGflO9oJuXUZDOX4rW0sSa7AltAcumJiVnZ5D5T5coriHZandZerFUpaVOpCQ4OXNJ8rika46BELturmOeriC7cFcl5KNEoveMscaIyYenneAaSndJcMi8nnaHWLmoHnO8pXuXtF614thBWeoZilYinNCUtHoaRY3bKowYlthe7nad5F4CdHIthechZickeZQnKaOnd9stir5Ji9tIarounO8d6adBd8Kth7eO4A1JGdry5Jspi0ce3QmixB4a1ndTstWiOrto3cAo3aAtGDallJ0thPV9echZiScZMkeQnPp4iLNece0swe33lOl2JlaZyerSEFW4XtVhVDSeOBVA2KpDViecesOSCQ99N9OPof5RR8LchiM1ck6enViBQUWU9nHthJeMlRF25oa9RZBftiYGZ0ZnDa9nDdDpNrAe5s1EsSYMQ95dowVULnCXth4ZenbLaP8kGeGinZtZ7Kh0e56I71I0oveUn7WfoErN4fVELSOoPrtyK1mJin4FutesEUPISme3a5HnBQG99Q0whileQ62m4ake8DthGeML7NPGCsMlawL0pu2tRtPheRXb3OTrEAoccoliW6VLint0o5U6DaOlarg03Ye5LbowEl8SNBHY3FM05pUuBAtt4IQWhWAeXCyo5NghuYRrtXHint6Zoa4s0ec5VWonZEdNI3bXIowl22aKnSdCMDQJhFeaNKtWBLTE0VXtheMSoilMi9QnFaAsEmZallpanVaAssRWoonQYaD30YKsth5eJSW6CIoEEiHl1HisDWhotZ4adCPdQtheLmuJ8sVYtaTr93dpDVX2oWFwTderIRMa3nDdAW2sCNOeQedsR6whenthAe7G7seXeEKdHsZbegiM5NZnYTtopo1pGDBHPLUUPp8XoLurPth5eBX3NNoKMiHlN0W9QLV0aROndVsTSDee8dNsovHerV7Bt2B7h7J72eDyogh40urt0595addthe3WsaUltG8AanMdAst4FLDiYrH1po8urEtIhi8sdr4essLinIQgCH1U7oCverOZ5MPQtheS1b9K7rJoc3FANcoli09tU5hZenSF56mRi7xQUin0C83JL0th4MeLEKUSpParsleyEw52ZSheU3nYtheKs6hawaUrm4QIUaM04is7Urea8dy9PlKTeaW1JvXUeSi5YtVKiM7POVHnXZNE3NYtShetiMJnGYWJfYoCrPMteLC1nA0mNinR4ARut64CDMHMNesWWAsDoHtha3JtITBYaFlMlEthEe3YX0Q3SjuO5XPiYWcAMesTFPcaEn32gFJo6GbNacQkCinTtD2oRUt8hLYPe2NOPWch2LiMcHMkenLM7PLK5FEQt07ipOi5JVtoutAWo7fNMtAhe6tNina0nd7KUsVW1XliceRN2FVyRBour6LXsYIDWhaKPwarmHa07iGlLi7kY4eTtULD9oSGHVGeaXYt8t5hiDspiIlIRed3TiXXSnto2MWflMH5HPaETZVtFYEVRb4BrGNGQeaRMds8MwiPtUhF6THtZ8heslaw6ZN89aNHLXnEyleRSf6ZtYZU4WoveMrXs4cD5EaDnXbekepGYtGiSnEthefriOdLgeE9O9ZGUoZrMfCrBozeDnM6foDrT6tVXhJe28CnJI5exGt2tHVLWiBmPeyou3ne3Ied9IySoXuE6rXsFZWQ66haJwBRa2JUEUG3rmaDW1C"
CHARS = "bcdeShawrmfgijklnopqtuvxyzABCDEFGHIJKLMNOPQRsTUVWXYZ2476350189"

def cost(kbd):
    pos = {}
    cc = 0
    for i in kbd:
        pos[i] = cc
        cc += 1
    
    cost = 0
    idx = pos[TEXT[0]]
    for c in TEXT:
        cost += abs(idx-pos[c])
        idx = pos[c]
    return cost

# M = Max result = 21
# D = Your cost
# A = Optimal Solution
# B = Maximum points that will get score (guessed)
def score(D, A=26886, B=31000, M=21):
    return M / (1 + max(0, D-A)/(B-A))

def test(kbd):
    for c in CHARS:
        if c not in kbd:
            kbd += c
    print(kbd)
    cc = cost(kbd)
    print(f"Cost: {cc}")
    print(f"Score: {score(cc)}")

def sameInput():
    freq = {}
    kbd = ""
    for c in TEXT:
        if c not in freq:
            kbd += c
            freq[c] = 1
        else:
            freq[c] += 1
    return kbd
    
def sortByFreq():
    freq = {}
    for c in TEXT:
        if c not in freq:
            freq[c] = 1
        else:
            freq[c] += 1
    freq = dict(sorted(freq.items(), key=lambda item: item[1]))
    srt = "".join(list(freq.keys()))
    kbd = srt[::-1]
    return kbd
    
def freqPal():
    freq = {}
    for c in TEXT:
        if c not in freq:
            freq[c] = 1
        else:
            freq[c] += 1
    freq = dict(sorted(freq.items(), key=lambda item: item[1]))
    srt = "".join(list(freq.keys()))
    srt = srt[::-1]
    lsum = 0
    rsum = 0
    kbd = ""
    for s in srt:
        if lsum <= rsum or random()%2 == 0:
            lsum += freq[s]
            kbd = s + kbd
        else:
            rsum += freq[s]
            kbd = kbd + s
    return kbd

def edges():
    freq = {}
    for i in range(1, len(TEXT)):
        ss = TEXT[i-1] + TEXT[i]
        sorted(ss)
        if ss not in freq:
            freq[ss] = 1
        else:
            freq[ss] += 1
    freq = dict(sorted(freq.items(), key=lambda item: item[1]))
    reversed(freq)
    print(freq)
    kbd = ""
    for i in freq:
        if i[0] not in kbd:
            kbd = kbd + i[0]
        if i[1] not in kbd:
            kbd = i[1] + kbd
    return kbd

def swap(c, i, j):
    c = list(c)
    c[i], c[j] = c[j], c[i]
    return ''.join(c)

def randomSwapping():
    kbd = CHARS
    cur = cost(kbd)
    for _ in range(int(2e4)): # As this gets larger, as optimal the solution become
        i = randint(0,61)
        j = randint(0,61)
        kbd = swap(kbd, i, j)
        newcost = cost(kbd)
        if newcost < cur:
            cur = newcost
        else:
            kbd = swap(kbd, i, j)
    return kbd



#test(freqPal())
#test(sameInput())
#test(sortByFreq())
test(randomSwapping())
```

**أفضل حل مكتشف:** `26890`, `jgfwmuB26TF4ARW0LVsXYEthUZr5aecoJ7ilMHnDSdPON389QIGCKp1ybkvxzq`