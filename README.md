# Vector (made in China)
Tai std::vektorius, tik savadarbis :)

## Spartos tyrimas

palyginimas su `std::vector`
|  konteineris/elementų skaičius| 10000   | 100000  | 1000000 | 10000000 | 100000000 |
|:----:                        | :-----:  |:------: |:-------:|:--------:|:--------:|
| **std::vector**  | 0.0001932 | 0.0016448 | 0.0134005 | 0.133456 | 1.3494 |
| **mVector** | 0.0001738 | 0.0015229 | 0.0143257 | 0.153184  | 1.5362 |

atminties perkėlimų skaičius
| std::vector | mVector |
|:----: |:------: |
|  28 | 28 |

2.0 pažymių skaičiuoklės sparta su (100000) studentų
|            | nuskaitymas  | surūšiavimas  | išskaidymas | išvedimas | TOTAL |
|:----:                        | :-----:  |:------: |:-------:|:--------:|:--------:|
| **std::vector**  | 0.172281 | 0.028221 | 0.021136 | 0.1129765 | 0.334615 |
| **mVector**   | 0.170411 | 0.0292966 | 0.022966  | 0.109292 | 0.331965|

## Funkcijų aprašymai  

* [mVector::at()](#at)

* [mVector::rbegin()](#rbegin)

* [mVector::size()](#size)

* [mVector::insert()](#insert)

* [mVector::operator==](#equal)


## <a name="at"></a>mVector::at()
```c++
reference at(size_type position);
const_reference at(size_type position) const;
```
* Grąžina elementą tam tikroje vietoje. Jei paduotas argumentas yra už ribų, yra iškviečiamas `std::out_of_range` error.
```c++
// naudojimo pavyzdys
mVector<int> v {1,2,3};

cout<< v.at(0) <<endl; // 1
cout<< v.at(2) <<endl; // 3
cout<< v.at(1000) <<endl; // (mVector::at) out of range!!!
```

## <a name="rbegin"></a>mVector::rbegin()
```c++
reverse_iterator rbegin();
const_reverse_iterator rbegin() const;
```
* Grąžina iteratorių į pirmą elementą apverstame masyve, tai ekvivalentu end() iteratriuj paprastam vektoriuje.
```c++
// naudojimo pavyzdys
mVector<int> v {1,2,3};

std::reverse_iterator<int*> rbegin = v.rbegin();
int size = v.size();
for(int i = 0; i<size; i++) {
    cout<< *(rbegin + i)<<" "; // 3 2 1
}
```

## <a name="size"></a>mVector::size()
```c++
size_type size() const;
```
* Grąžina elementų skaičių vektoriuje
```c++
// naudojimo pavyzdys
mVector<int> v {1,2,3}; 
mVector<int> g; 
cout<<v.size()<<endl; // 3
cout<<g.size()<<endl; // 0
```

## <a name="insert"></a>mVector::insert()
```c++
iterator insert(iterator pos, const T& value);
iterator insert(iterator pos, size_type count, const T& value);
iterator insert(iterator pos, InputIterator first, InputIterator last);
iterator insert(iterator pos, std::initializer_list<T> initializer);
```
* Įdeda elementą prieš nurodytą vietą:  
  1.) Įdeda vieną elementą  
  2.) Įdeda `count` kopijų elemento  
  3.) Įdeda elementus iš iteratorių srauto  
  4.) Įdeda elementus iš `std::initializer_list`  
  
```c++
 mVector<int> v {1,2,3};
 mVector<int> g {9, 8, 7};

v.insert(v.begin() + 2, 77); // 1 2 (77) 3
v.insert(v.begin() + 2, 3, 77); // 1 2 (77 77 77) 3
v.insert(v.begin() + 2, g.begin(), g.end()); // 1 2 (9 8 7) 3
v.insert(v.begin() + 2, {4,4,4}); // 1 2 (4 4 4) 3
```

## <a name="equal"></a>mVector:: palyginimo operatorius '=='
```c++
bool operator==(mVector<T>& other);
```
* Patikrina ar du mVecktor klasės objektai yra lygūs (turi vienodus elementus)
```c++
mVector<int> v {1,2,3};
mVector<int> g {1,2,3};
mVector<int> c {3,4,5};

cout<< (v == g) << endl; // 1
cout<< (v == c) << endl; // 0
```




