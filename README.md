# Vector (made in China)
Tai std::vektorius, tik savadarbis :)

## Spartos tyrimas
laikai, per kuriuos konteineriai užpildomi elementais
|  konteineris/elementų skaičius| 10000   | 100000  | 1000000 | 10000000 | 100000000 |
|:----:                        | :-----:  |:------: |:-------:|:--------:|:--------:|
| **std::vector**  | 0.0001932 | 0.0016448 | 0.0134005 | 0.133456 | 1.3494 |
| **mVector** | 0.0001738 | 0.0015229 | 0.0143257 | 0.153184  | 1.5362 |

atminties perkėlimų skaičius
| std::vector | mVector |
|:----: |:------: |
|  28 | 28 |

2.0 pažymių skaičiuoklės sparta su 100000 studentų
|            | nuskaitymas  | surūšiavimas  | išskaidymas | išvedimas | TOTAL |
|:----:                        | :-----:  |:------: |:-------:|:--------:|:--------:|
| **std::vector**  | 0.172281 | 0.028221 | 0.021136 | 0.1129765 | 0.334615 |
| **mVector**   | 0.170411 | 0.0292966 | 0.022966  | 0.109292 | 0.331965|

## Funkcijų aprašymai
* [mVector::at()](#mVector::at)

* [mVector::begin()](#mVector::begin)

* [mVector::size()](#mVector::size)

* [mVector::insert()](#mVector::insert)

* [mVector::operator==](#mVector::equal)


## <a name="mVector::at"></a>mVector::at()

## <a name="mVector::begin"></a>mVector::begin()

## <a name="mVector::size"></a>mVector::size()

## <a name="mVector::insert"></a>mVector::insert()

## <a name="mVector::equal"></a>mVector:: palyginimo operatorius '=='





