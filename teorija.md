 kai jau susortinai ir nori i nauja vektoriu idet kad nesikartotu
```
    for(int i=0; i<a.size(); i++){
       if(b.empty() || b.back().pratimas != a[i].pratimas){
           b.push_back(a[i]);
       }
       else b.back().k+=a[i].k;
    }

```

bubble sort islaikantis eiliskuma (stable)

```
for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j].ats < a[j+1].ats) {
                std::swap(a[j], a[j+1]);
            }
        }
    }
```

rasti kiek porų yra
```

 std::sort(v.begin(), v.end()); // Sort the vector
    int pairs = 0;

    for(int i = 0; i < v.size() - 1; i++) {
        if(v[i] == v[i + 1]) { 
            pairs++;  
            i++; 
        }
    }
```
dazniausias elementas(-ai)
```
      // Bubble sort kad visi skaitmenys eitu is eiles, tada skaiciuoji streak
    for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j].skaitmuo < a[j + 1].skaitmuo) std::swap(a[j], a[j + 1]);
        }
    }

    int streak = 1;
    for (int i = 1; i < a.size(); i++) {
        if (a[i].skaitmuo == a[i - 1].skaitmuo) streak++;
        else streak = 1;
        
        if (streak > max) {
            max = streak;
            maxi = a[i].skaitmuo;
        }
}
//o jei reikia rasti visus dazniausius, nebenaudoji maxi, naudoji nauja masyva pvz maxm
//tada vel iteruoji ir jei max daznis sutampa su turimu streak'u, push_back
std::vector<skaiciai> maxm;
    streak = 1;
    for (int i = 1; i < a.size(); i++) {
        if (a[i].skaitmuo == a[i - 1].skaitmuo) streak++;
        else streak = 1;
        
        if (streak == max) maxm.push_back(a[i]);
    }

```
du didziausi elementai (be rikiavimo)
```
int d=INT_MIN, d1=INT_MIN;
for(int i=0; i<n; i++){
    if(a[i] > d) {
        d1 = d;
        d= a[i];
    }
    else if(a[i] >d1) d1 = a[i];
  }
  fr << d  << ' ' <<d1;
```

```
    for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j].skaitmuo < a[j + 1].skaitmuo) std::swap(a[j], a[j + 1]);
        }
    }
    
    int last = -1;
    for (int i = 0; i < a.size(); i++) {
        if (a[i].skaitmuo != last) {
            ats.push_back(a[i].skaitmuo);
            last = a[i].skaitmuo;
        }
    }
```
pasikartojimų dažnių skaičiavimas su vektoriais
```
std::vector<int> a(10, 0); //privalai zinoti imanomu skaiciu amplitude, esminis skirtumas nuo mapsu
for (int i = 0; i < n; i++) {
    int temp;
    fd >> temp;
    a[temp]++;
}

int max=0; //max radimas
    for(int i=0; i<a.size(); i++){
        if(a[i] > max) max = a[i];
    }

bool first = true; // isvedame su kableliais: "4,5,6"
for (int i = 0; i < 10; i++) {
    if (a[i] == max_count) {
        if (!first) fr << ',';
        fr << i;
        first = false;
    }
}

```
mediana (variacines eilutes vidurys)
```
    for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j] > a[j + 1]) std::swap(a[j], a[j + 1]);
        }
    }
    
    if (a.size() % 2 == 1) return a[a.size() / 2];
    else return (a[a.size() / 2] + a[(a.size() / 2) - 1]) / 2.0;
```
maziausias teigiamas skaicius kurio nera masyve
```
    int max = 0;
    // Bubble sort in ascending order
    for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j] > a[j + 1]) std::swap(a[j], a[j + 1]);
        }
        if (a[i] > max) max = a[i];
    }
    
    for (int i = 1; i <= max; i++) {
        bool found = false;
        for (int j = 0; j < a.size(); j++) {
            if (a[j] == i) {
                found = true;
                break;
            }
        }
        if (!found) return i;
    }
    return max + 1;
```
antras maziausias elementas
```
   for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j] > a[j + 1]) std::swap(a[j], a[j + 1]);
        }
    }
    
    for (int i = 1; i < a.size(); i++) {
        if (a[i] != a[0]) return a[i];
    }
    return -1;
```
trys didziausi skirtingi elementai
```
std::sort(a.begin(), a.end(), [](const skaicius &x, const skaicius &y) {
    return x.skaitmuo > y.skaitmuo;
});

std::vector<int> ats;
int last = -1, count = 0;

for (int i = 0; i < a.size() && count < 3; i++) {
    if (a[i].skaitmuo != last) {
        ats.push_back(a[i].skaitmuo);
        last = a[i].skaitmuo;
        count++;
    }
}
