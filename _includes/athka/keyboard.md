## لوحة المفاتيح
هذه مسألة اختصار، أي كلما وجدت حل أفضل كانت درجتك أعلى.

**بعض الأفكار المستعملة في:**
- الترتيب بناءً على تكرار الحرف (تكلفة 37567)
- ترتيب كتابة النص دون تكرار (تكلفة 36814)
- الترتيب الهرمي بناءً على تكرار الحرف (تكلفة 30530)
- الترتيب العشوائي (تكلفة 32421)
- التبديل العشوائي إذا كان يعطي نتيجة أفضل (تكلفة 27000~)

<details>
  <summary>الحل باستعمال بايثون</summary>

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

</details>

<details>
  <summary>الحل باستعمال <span dir="ltr">C++</span></summary>

```cpp
#include <bits/stdc++.h>

using namespace std;

const string TEXT = "pUrehIC9ea2ttheJE7ovenMTVE9WYtoEGXEOoneFhXuEnd5redeightyZdINID7egFreeVsRT9MCPaFnWSd68ligFht8lyGI5gRROrJePLHS6REIQaBAseY1OanKinC3eW83K9OhGundRreQdVg3CIZ7EZPTXrQR3aQmZsloKFafNtFY7i77nOINSf0DortDZQhEe4AshawarmaGm3TZiExtUXCRoJg9etZherLXthJe2cPFL8ornGflO9oJuXUZDOX4rW0sSa7AltAcumJiVnZ5D5T5coriHZandZerFUpaVOpCQ4OXNJ8rika46BELturmOeriC7cFcl5KNEoveMscaIyYenneAaSndJcMi8nnaHWLmoHnO8pXuXtF614thBWeoZilYinNCUtHoaRY3bKowYlthe7nad5F4CdHIthechZickeZQnKaOnd9stir5Ji9tIarounO8d6adBd8Kth7eO4A1JGdry5Jspi0ce3QmixB4a1ndTstWiOrto3cAo3aAtGDallJ0thPV9echZiScZMkeQnPp4iLNece0swe33lOl2JlaZyerSEFW4XtVhVDSeOBVA2KpDViecesOSCQ99N9OPof5RR8LchiM1ck6enViBQUWU9nHthJeMlRF25oa9RZBftiYGZ0ZnDa9nDdDpNrAe5s1EsSYMQ95dowVULnCXth4ZenbLaP8kGeGinZtZ7Kh0e56I71I0oveUn7WfoErN4fVELSOoPrtyK1mJin4FutesEUPISme3a5HnBQG99Q0whileQ62m4ake8DthGeML7NPGCsMlawL0pu2tRtPheRXb3OTrEAoccoliW6VLint0o5U6DaOlarg03Ye5LbowEl8SNBHY3FM05pUuBAtt4IQWhWAeXCyo5NghuYRrtXHint6Zoa4s0ec5VWonZEdNI3bXIowl22aKnSdCMDQJhFeaNKtWBLTE0VXtheMSoilMi9QnFaAsEmZallpanVaAssRWoonQYaD30YKsth5eJSW6CIoEEiHl1HisDWhotZ4adCPdQtheLmuJ8sVYtaTr93dpDVX2oWFwTderIRMa3nDdAW2sCNOeQedsR6whenthAe7G7seXeEKdHsZbegiM5NZnYTtopo1pGDBHPLUUPp8XoLurPth5eBX3NNoKMiHlN0W9QLV0aROndVsTSDee8dNsovHerV7Bt2B7h7J72eDyogh40urt0595addthe3WsaUltG8AanMdAst4FLDiYrH1po8urEtIhi8sdr4essLinIQgCH1U7oCverOZ5MPQtheS1b9K7rJoc3FANcoli09tU5hZenSF56mRi7xQUin0C83JL0th4MeLEKUSpParsleyEw52ZSheU3nYtheKs6hawaUrm4QIUaM04is7Urea8dy9PlKTeaW1JvXUeSi5YtVKiM7POVHnXZNE3NYtShetiMJnGYWJfYoCrPMteLC1nA0mNinR4ARut64CDMHMNesWWAsDoHtha3JtITBYaFlMlEthEe3YX0Q3SjuO5XPiYWcAMesTFPcaEn32gFJo6GbNacQkCinTtD2oRUt8hLYPe2NOPWch2LiMcHMkenLM7PLK5FEQt07ipOi5JVtoutAWo7fNMtAhe6tNina0nd7KUsVW1XliceRN2FVyRBour6LXsYIDWhaKPwarmHa07iGlLi7kY4eTtULD9oSGHVGeaXYt8t5hiDspiIlIRed3TiXXSnto2MWflMH5HPaETZVtFYEVRb4BrGNGQeaRMds8MwiPtUhF6THtZ8heslaw6ZN89aNHLXnEyleRSf6ZtYZU4WoveMrXs4cD5EaDnXbekepGYtGiSnEthefriOdLgeE9O9ZGUoZrMfCrBozeDnM6foDrT6tVXhJe28CnJI5exGt2tHVLWiBmPeyou3ne3Ied9IySoXuE6rXsFZWQ66haJwBRa2JUEUG3rmaDW1C";
const string CHARS = "bcdeShawrmfgijklnopqtuvxyzABCDEFGHIJKLMNOPQRsTUVWXYZ2476350189";

int cost(const string& kbd) {
    unordered_map<char, int> pos;
    int cc = 0;
    for (char i : kbd) {
        pos[i] = cc;
        cc++;
    }

    int cost = 0;
    int idx = pos[TEXT[0]];
    for (char c : TEXT) {
        cost += abs(idx - pos[c]);
        idx = pos[c];
    }
    return cost;
}

double score(int D, int A = 26886, int B = 26986, int M = 21) {
    return M / (1 + max(0, D - A) / static_cast<double>(B - A));
}

void test(string kbd) {
    for (char c : CHARS) {
        if (kbd.find(c) == string::npos) {
            kbd += c;
        }
    }
    cout << kbd << endl;
    int cc = cost(kbd);
    cout << "Cost: " << cc << endl;
    cout << "Score: " << score(cc) << endl;
}

string sameInput() {
    unordered_map<char, int> freq;
    string kbd = "";
    for (char c : TEXT) {
        if (freq.find(c) == freq.end()) {
            kbd += c;
            freq[c] = 1;
        }
        else {
            freq[c] += 1;
        }
    }
    return kbd;
}

string sortByFreq() {
    unordered_map<char, int> freq;
    for (char c : TEXT) {
        if (freq.find(c) == freq.end()) {
            freq[c] = 1;
        }
        else {
            freq[c] += 1;
        }
    }
    vector<pair<char, int>> sortedFreq(freq.begin(), freq.end());
    sort(sortedFreq.begin(), sortedFreq.end(), [](const auto& a, const auto& b) {
        return a.second < b.second;
        });

    string kbd = "";
    for (const auto& pair : sortedFreq) {
        kbd += pair.first;
    }
    reverse(kbd.begin(), kbd.end());
    return kbd;
}

string freqPal() {
    unordered_map<char, int> freq;
    for (char c : TEXT) {
        if (freq.find(c) == freq.end()) {
            freq[c] = 1;
        }
        else {
            freq[c] += 1;
        }
    }
    vector<pair<char, int>> sortedFreq(freq.begin(), freq.end());
    sort(sortedFreq.begin(), sortedFreq.end(), [](const auto& a, const auto& b) {
        return a.second < b.second;
        });

    string srt = "";
    for (const auto& pair : sortedFreq) {
        srt += pair.first;
    }
    reverse(srt.begin(), srt.end());

    int lsum = 0;
    int rsum = 0;
    string kbd = "";
    for (char s : srt) {
        if (lsum <= rsum || rand() % 2 == 0) {
            lsum += freq[s];
            kbd = s + kbd;
        }
        else {
            rsum += freq[s];
            kbd = kbd + s;
        }
    }
    return kbd;
}

string edges() {
    map<pair<char, char>, int> freq;
    for (int i = 1; i < TEXT.length(); i++) {
        pair<char, char> ss = { TEXT[i - 1], TEXT[i] };
        if (freq.find(ss) == freq.end()) {
            freq[ss] = 1;
        }
        else {
            freq[ss] += 1;
        }
    }
    vector<pair<pair<char, char>, int>> sortedFreq(freq.begin(), freq.end());
    sort(sortedFreq.begin(), sortedFreq.end(), [](const auto& a, const auto& b) {
        return a.second < b.second;
        });
    reverse(sortedFreq.begin(), sortedFreq.end());

    string kbd = "";
    for (const auto& pair : sortedFreq) {
        if (kbd.find(pair.first.first) == string::npos) {
            kbd += pair.first.first;
        }
        if (kbd.find(pair.first.second) == string::npos) {
            kbd += pair.first.second;
        }
    }
    return kbd;
}

string randomSwapping()
{
    string kbd = CHARS;
    int cur = cost(kbd);
    for (int _ = 0; _ < 2e4; _++) // As this gets larger, as optimal the solution become
    {
        int i = rand()%62;
        int j = rand()%62;
        swap(kbd[i], kbd[j]);
        int newcost = cost(kbd);
        if (newcost < cur)
            cur = newcost;
        else
            swap(kbd[i], kbd[j]);
    }
    return kbd;
}

int main()
{
    //test(edges());
    //test(freqPal());
    //test(sortByFreq());
    //test(sameInput());
    test(randomSwapping());
}
```

</details>


**أفضل حل:** `jgfwmuB26TF4RAW0LVsXYEUthZr5aecoJlMiHn7DSdPO38NQ9IGCKp1ybkvxzq`

**التكلفة:** $26886$