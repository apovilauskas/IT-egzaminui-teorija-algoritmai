```cpp
 kai jau susortinai ir nori i nauja vektoriu idet kad nesikartotu

    for(int i=0; i<a.size(); i++){
       if(b.empty() || b.back().pratimas != a[i].pratimas){
           b.push_back(a[i]);
       }
       else b.back().k+=a[i].k;
    }

---

bubble sort islaikantis eiliskuma

for (int i = 0; i < a.size(); i++) {
        for (int j = 0; j < a.size() - 1; j++) {
            if (a[j].ats < a[j+1].ats) {
                std::swap(a[j], a[j+1]);
            }
        }
    }

rasti kiek porų yra

 std::sort(v.begin(), v.end()); // Sort the vector
    int pairs = 0;

    for(int i = 0; i < v.size() - 1; i++) {
        if(v[i] == v[i + 1]) { 
            pairs++;  // Found a pair
            i++; // Skip the next element since it's already counted in a pair
        }
    }

ilgiausias streak (iš eilės)

    int streak = 0;
    int max=0;
for(int i = 0; i < n; i++){
    if(a[i] > requirement) {
        streak++;
        if (streak > max) max = streak;
    } 
else {
        streak = 0;
    }
}
