# **Array.find() Methodu**

***find() yöntemi, sağlanan dizideki sağlanan test işlevini karşılayan ilk öğeyi döndürür. Test işlevini karşılayan hiçbir değer yoksa, tanımsız döndürülür***

#### Syntax

``` Javascript
// Arrow function
find((element) => { /* ... */ } )
find((element, index) => { /* ... */ } )
find((element, index, array) => { /* ... */ } )

// Callback function
find(callbackFn)
find(callbackFn, thisArg)

// Inline callback function
find(function(element) { /* ... */ })
find(function(element, index) { /* ... */ })
find(function(element, index, array){ /* ... */ })
find(function(element, index, array) { /* ... */ }, thisArg)

```
* **CallbackFn: Dizenin her değeri için yürütülecek işlevdir.Bu işlev aşağıdaki argümanlara sahiptir.**
  1. *Element: Dizede bulunan geçerli öğedir. CallbackFn yürütüldüğünde bu değerler üzerinde işlemler yapar.*
  2. *Mevcut elemanın indeksini tutan isteğe bağlı bir parametredir.*
  3. *Geçerli öğenin ait olduğu dizi nesnesini tutan isteğe bağlı bir parametredir*

```Javascript
let data =[
 ......
]
const founded = data.find(item => item._id === "5e652aa69cb94a55a21dbd24")

console.log(founded)

/*
about: "Eiusmod do qui veniam cupidatat velit est sit tempor nostrud nostrud tempor magna. Et officia velit excepteur dolor adipisicing adipisicing cupidatat voluptate et exercitation. Sint magna sit nisi laborum sunt dolore velit irure in proident. Veniam dolore amet amet dolor ullamco cupidatat Lorem.\r\n"
address: "646 Montague Street, Cutter, Hawaii, 1870"
age: 30
balance: "$3,929.51"
company: "EARTHPLEX"
email: "caroledaniels@earthplex.com"
eyeColor: "brown"
friends: (3) [{…}, {…}, {…}]
gender: "female"
guid: "7fbd5a0a-5d8b-4cdd-97b7-f7715183ea60"
index: 1
isActive: true
latitude: 59.036927
longitude: 91.043976
name: "Carole Daniels"
phone: "+1 (863) 523-3588"
picture: "http://placehold.it/32x32"
registered: "2016-10-22T04:13:14 -03:00"
tags: (7) ['consectetur', 'ut', 'laboris', 'officia', 'velit', 'in', 'in']
_id: "5e652aa69cb94a55a21dbd24"
*/
```

Find sonuç olarak bir koşul döndürmelidir yani bir test işlemi sağlamalı.Böylece bizim için koşulu sağladığı ilk değeri alabiliriz.Aslında biz bu fonksiyonu kullanırken uniq değerler ararız yani sonuç olarak birden fazla değer döndürmediğinden bizim için önemli olan benzersiz bir değeri yakalamaktır. Yukardaki örnekte gördüğünüz üzere biz sadece benzersiz id değerlerinden oluşan array elemanlarından belirtiğimiz id değerine sahip array elemanına ulaştık.

```
....(item => item._id === "5e652aa69cb94a55a21dbd24")
```

# **Array.findIndex() Methodu**

**findIndex() yöntemi, sağlanan test işlevini karşılayan dizideki ilk öğenin dizinini döndürür. Aksi takdirde, hiçbir öğenin testi geçmediğini belirten -1 döndürür.**

### Syntax
```Javascript
findIndex((element) => { /* ... */ } )
findIndex((element, index) => { /* ... */ } )
findIndex((element, index, array) => { /* ... */ } )

// Callback function
findIndex(callbackFn)
findIndex(callbackFn, thisArg)

// Inline callback function
findIndex(function(element) { /* ... */ })
findIndex(function(element, index) { /* ... */ })
findIndex(function(element, index, array){ /* ... */ })
findIndex(function(element, index, array) { /* ... */ }, thisArg)
```
* **callbackFn: Sağlanan test işlevi true değeri döndürene kadar belirtilen dize üzereindeki her eleman için bu test işlevini döndürür.**

  1. *element: Bu parametre, geçerli öğeyi tutar.Bu dize üzerindeki her elemanı temsil eder.*
  2. *index: Dize içerisindeki mevcut elemanların index'ini tutan isteğe bağlı bir parametredir.*
  3. *array: Geçerli öğenin ait olduğu dizi nesnesini tutan isteğe bağlı bir parametredir.*

* **thisArg : Bu parametre isteğe bağlıdır, eğer fonksiyona geçirilecek bir değer “this” değeri olarak kullanılacaksa, "undefined" değeri “this” değeri olarak geçecektir.**

***Dönüş değeri: Dizideki öğelerden herhangi biri testi geçerse öğenin index'ini döndürür, aksi takdirde -1 döndürür***

``` Javascript
let data =[
 .....
 ...
]
const founded = data.findIndex(item => item._id === "5e652aa69cb94a55a21dbd24")

console.log(founded)
```
#### Example 

```Javascript
const ages = [23,49,32,20];

function checkAge(age){
 return age > 24;
}
ages.findIndex(checkAge)
// 1
```

#### Example
```Javascript
const ages = [23,49,32,20];

function checkAge(age){
 return age < 12;
}
ages.findIndex(checkAge)
// -1
```
# **Array.indexOf() Methodu**

***indexOf() yöntemi, belirli bir öğenin dizide bulunabileceği ilk dizini veya mevcut değilse -1  döndürür.***

#### Syntax

```Javascript
indexOf(searchElement)
indexOf(searchElement, fromIndex)
```

#### Example
```Javascript
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1

```
# **Array.filter() Methodu**

***filter yöntemi , yürütülen işlev doğrultusunda testi geçen her öğeden oluşan bir dize oluşturur.find metodundan farklı olarak testi geçen her öğeyi bir dizeye***

#### Syntax
``` Javascript
filter((element) => { /* ... */ } )
filter((element, index) => { /* ... */ } )
filter((element, index, array) => { /* ... */ } )

// Callback function
filter(callbackFn)
filter(callbackFn, thisArg)

// Inline callback function
filter(function(element) { /* ... */ })
filter(function(element, index) { /* ... */ })
filter(function(element, index, array){ /* ... */ })
filter(function(element, index, array) { /* ... */ }, thisArg)
```
* **callbackFn** : *Her öğe için bir test işlevi sağlar.Öğeyi tutmak için true veya aksi takdirde false olarak zorlayan bir değer döndürür. İşlev, aşağıdaki argümanlarla çağrılır:*
 1. **element**: *Dizinin işlenmekte olan öğelerine karşılık gelir.*
 2. **index :** *Dizi öğelerinin index'ini veri bu parametre isteğe bağlıdır.*
 3. **array :** *Testi geçen öğeleri içeren yeni bir dizidir. Hiçbir öğe testi geçmezse, boş bir dizi döndürülür.*

 #### Example

 ```javascript
 let data = [
  .
  ..
  ...
 ]
 let filteredItems = data.filter( item => item.age > 30)

 console.log(filteredItems)
 ```

 #### Example
 ```javascript
 let filteredItems = data.filter( item => item.age > 30)

 console.log(filteredItems)

 filteredItems = data.filter(item => item.age > 30 &&  item.gender === "female")
 
 console.log(filteredItems)
 ```