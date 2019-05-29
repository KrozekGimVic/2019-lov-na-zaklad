# Rešitve

* A1: 38
* A2: odgovor je rezultat tisoc dvesto stiriintrideset krat pet tisoc sesto oseminsedemdeset --> 7006652
* A3: 2498, pazi na prvo vrstico
* A4: 13, pazi na attribute pri div značkah
* A5: pojdi do učilnice 11

* B1: 45510056 Hashas vse besede, za n besed znotraj bucketa je `n*(n-1)/2` collisionov. Pazi na prazen string in overflow.
* B2: zamiki so 1, 4, 13, 22, 5. Dobiš program:

```
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n = 100;

    vector<int> b(n, 123);
    vector<int*> a(1 << (sizeof(char)*8));
    cout << a.size() << endl;
    for (int i = 1; i < n; ++i) {
        b[i] = (b[i-1] << 1) ^ i;
        a[i] = &b[i];
    }

    for (int i = n-1; i >= 0; --i) {
        cout << *a[i] << endl;
        a[i] -= i;
    }

    for (int* i : a) cout << i << endl;

    return 0;
}
```

* B3: 18. vrstica na zadnji iteraciji dereferencira null pointer.
* B4: 42
* B5: 16634, pošlji npr. post request z `curl` in podatki `{"guess": 14}`
* B6: pojdi do učilnice 44
