# **Array.map() Methodu**

***map() yöntemi, Yürütülen işlev  üst dizide bulunan her öğe için çalıştırılacak şekilde yürütülür. Bunun sonucunda bize yeni bir dize değeri döndürür.Dize üzerinde hiçbir mutasyon oluşturmaz. Genellikle map() yöntemi, bir dizi üzerinde yineleme yapmak ve dizinin her öğesinde işlevi çağırmak için kullanılır***

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

*map, bir dizideki her öğe için sağlanan bir callbackFn işlevini sırayla çağırır ve sonuçlardan yeni bir dizi oluşturur. callbackFn, yalnızca atanmış değerlere sahip (tanımsızlar dahil) dizinin dizinleri için çağrılır*


``` Javascript
let data =[
 .
 ..
 ...
]
let dataMaping = data.map( item =>{
 return{
  name   : item.name,
  age    : item.age,
  email  : item.email,
  gender : item.gender
 }
})

console.log(dataMaping)

/*
(29) [{…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}, {…}]
0:
age: 37
email: "patehenry@medcom.com"
gender: "male"
name: "Pate Henry"
[[Prototype]]: Object
.
..
...
*/
```
Map foksiyonu dize üzerinde değişik yapmadığı gibi işlev ile yürütülen dize öğelerinde yapılan değişikliklerle beraber bizim için yeni bir dize oluşturur.

``` Javascript
let filtred = data.filter( item => item.age > 30 && item.gender === "female")

let dataMaping = filtred.map( item =>{
 return{
  name   : item.name,
  age    : item.age,
  email  : item.email,
  gender : item.gender
 }
})

console.log(dataMaping)
/*
(5) [{…}, {…}, {…}, {…}, {…}]
0: {name: 'Sharron Hendricks', age: 32, email: 'sharronhendricks@endipin.com', gender: 'female'}
1: {name: 'Hillary Cote', age: 36, email: 'hillarycote@daisu.com', gender: 'female'}
2: {name: 'Maribel Bartlett', age: 40, email: 'maribelbartlett@pyramax.com', gender: 'female'}
3: {name: 'Dina Winters', age: 36, email: 'dinawinters@circum.com', gender: 'female'}
4: {name: 'Sonya Barron', age: 35, email: 'sonyabarron@exoblue.com', gender: 'female'}
length: 5
[[Prototype]]: Array(0)
*/
```

Zincirleme olarak bu örneği yapabiliriz.
```Javascript 
let dataMaping = data.filter( item => item.age > 30 && item.gender === "female").map( item =>{
 return{
  name   : item.name,
  age    : item.age,
  email  : item.email,
  gender : item.gender
 }
})

console.log(dataMaping)
/*
(5) [{…}, {…}, {…}, {…}, {…}]
*/
```
Bizim için yine aynı sonucu üretecektir javascripte metodları zincirleme olarak kullanabilirsiniz.

# **Array.forEach() Methodu**

*forEach() yöntemi, her dizi öğesi için sağlanan işlevi bir kez yürütür. Ancak map methodundan farklı olarak bir sonuç dizesi döndürmez.forEach yapılan işlemler bir döngü bir for gibi davranır aslında for ile yapılan işlemleri daha kolay hale getirmeyi amaçlamıştır.*

#### Syntax
```Javascript
// Arrow function
forEach((element) => { /* ... */ })
forEach((element, index) => { /* ... */ })
forEach((element, index, array) => { /* ... */ })

// Callback function
forEach(callbackFn)
forEach(callbackFn, thisArg)

// Inline callback function
forEach(function(element) { /* ... */ })
forEach(function(element, index) { /* ... */ })
forEach(function(element, index, array){ /* ... */ })
forEach(function(element, index, array) { /* ... */ }, thisArg)
```

* **CallbackFn: Dizenin her değeri için yürütülecek işlevdir.Bu işlev aşağıdaki argümanlara sahiptir.**
  1. *Element: Dizede bulunan geçerli öğedir. CallbackFn yürütüldüğünde bu değerler üzerinde işlemler yapar.*
  2. *Mevcut elemanın indeksini tutan isteğe bağlı bir parametredir.*
  3. *Geçerli öğenin ait olduğu dizi nesnesini tutan isteğe bağlı bir parametredir*


```Javascript
const items = ['item1', 'item2', 'item3'];

const copyItems = [];

for (let i = 0; i < items.length; i++) {
  copyItems.push(items[i]);
}
```
Biz döngüler oluşturarak array itemlerini başka dizeye aktarabiliriz.Ancak forEach bizim için bu işlemleri daha basite indirgeyecektir.

```Javascript
const items = ['item1', 'item2', 'item3'];
const copyItems = [];


items.forEach((item) => {
  copyItems.push(item);
});
```


### Example
```Javascript
let newArr = []

const filtered = 
data
.filter( item => item.age > 30 && item.gender === "female")
.forEach(async(item )=>{
  await newArr.push({
   name:item.name,
   age:item.age
  })
})

console.log(newArr)
```

Gördüğünüz gibi newArr dizesini mutasyona uğrattı işte map ile aralarındaki en büyük farklardan birisidir.

# **Array.Reduce() Methodu**


**Reduce() yöntemi, dizinin her bir öğesinde bir redüktör işlevi yürütür ve tek bir çıktı değeri döndürür.**

#### Syntax
```
arr.reduce(callback(accumulator, currentValue), initialValue)
```
* **callback:** Bir redüktör işlevidir.
  * **accumulator:** Önceki cağrıdan kaynaklanan değerdir. ilk aramada initialValue değerine bakar yoksa eğer birr array[1] değerini alır.
  * **currentValue:** Geçerli öğenin değerleridir.
  * **currentIndex:** Dizedeki dizinlerinlerin konumudur.
  * **array:** Sağlanan dize değerlerini içerir.

* **initialValue** isteğe bağlıdır.Geri arama başlatıldığında accumulator başlatılma değerine bakar ardından redüktör işlevi doğrultusunda değerleri bir yapı içerisinde depolar.

```Javascript
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
  (previousValue, currentValue) => previousValue + currentValue,
  initialValue
);
console.log(sumWithInitial);
// expected output: 10

```

#### Example
```Javascript
let data =[
 ...
 ....
 .....
]
const totalAge = data.reduce((total,item)=>{
 return total + item.age
},0)

console.log(totalAge)
```
Ancak bu işlemi forEach ile yapıcak olursak nolurdu.

```
total = 0
data.forEach( item => total += item.age )

console.log(total)
```

bir değişken tanımlamamız gerekir işte reduce bizi bazı yüklerden kurtarır.

```Javascript

let group = "gender"

let employeeList = data.reduce((acc,employee)=>{
  let key = employee[group]
  if(!acc[key]){
    acc[key] = []
    }
  acc[key].push(employee)
   return acc
},{})

console.log(employeeList)

```
