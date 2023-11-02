# Week2 Lecture
## Recursive Fonksiyon
```javascript
function count() {
  if (something) count()
}
```
Eğer bir fonksiyonda belirli bir koşul sağlanıyorsa ve içerde tekrar aynı fonksiyon çağırılıyorsa buna recursive fonksiyon denir. Yani kendini içerde tekrar çağıran fonksiyon diyebiliriz.

## Switch - Case
Switch-case, Bir değeri birden çok cas'e göre kontrol etmek için kullanılır.
```javascript
let condition = 4
switch (condition) { // condition değişkeni kontrol ediyor ve ilgili alana işlem yapıyor.
  case 1:

    break:
  case 2:

    break:
  default: //caseler dışında, if-else'deki else gibi.
    break:
```
`Note: ` Koşullar bir değişkene bağlıysa switch-case kullanılır. Daha komplex koşulları kontrol etmek için if-else kullanılır.
```javascript
let method = 'GET'
  switch (method) {
    case 'GET':
      break:
    case 'POST':
      break:
    case 'DELETE':
      break 
```
Örneğin bir form verisini göndermek istiyoruz. bu durumda post methodunu kullanırız.

Bunu aynı zamanda if-else olarak da kullanabiliriz:
```javascript
if (method === 'GET') {
} else if (method === 'POST') {
//..
} else if (method === 'DELETE') {
//..
} else {
//..
}
```
## Objects
Objelerin temel veri kaydetme sistemi key ve valuelardan oluşur.
```javascript
let object = {
    boss: 'Ali'
    sales: 'Veli'
    area: 'Marmara'
```
In here, boss, sales, and area are keys. Ali, Veli, and Marmara are values.

`Keyleri arraya dönüştürme:`
```javascript
const keys = object.keys( 0: obje) //[boss, sales, area]
```
`Valueleri arraya dönüştürme:`
```javascript
const values = object.values(obje) //[Ali, Veli, Marmara]
```
`Objeyi arraya dönüştürme:`
```javascript
let objectContet = object.entries(object) //[['boss', 'Ali'], ['sales', 'Veli'], ['area', 'Marmara']]

for (let i = 0; i < objectContent.length; i++) {
  console.log(data[0]: 'iş tanımı ${objectContent[i][0]} ${objectContent[i][1]} ${objectContent[i][2}')
```
`Objeleri kopyalamak için`

Assign ve spread operatörlerini kullanabiliriz.
```javascript
const object2 = Object.assign(target : object)
```

`freeze`: Tamamen dondurur. Değişiklik ve parametre ekleme gibi işlemler yapılamaz.

`seal`: Parametre eklenemez ancak var olan parametreler üzerinde değişiklik yapılabilir.

## Classes
```javascript
class employee {
  constructor(name, surname, age) {
    this.name = name
    this.surname = surname
    this.age = age
    this.firm = 'abc ltd. şti.' //Sabit de verebiliriz.
  }
  fullName = function(){
    return '${this.name} ${this.surname} ${this.age}'
  } 
}
const employee1 = new employees(name:'Ali', surname:'Veli', age: 34)

employee1.fullName // fullname'e ulaşmak için
```
JavaScript sınıflarında constructor, sınıfın bir nesnesi oluşturulduğunda çağrılan özel bir metoddur. constructor, sınıfın yapılandırılmasını ve başlatılmasını sağlar. Bu metot, sınıfın özelliklerine başlangıç değerleri atamak veya diğer başlangıç ayarlarını yapmak için kullanılır. 

`Class Inheritence`: Bir üst sınıfın özelliklerini ve yöntemlerini başka bir sınıfa (alt sınıfa) aktarmak.
```javascript
class subClass extends employees {
  constructor() {
    super(): //1- Bir öncekinden gelenleri aldım ve,
    this.area = area //2- area yı yanına eklemiş oldum.
  }
title = () => '${(this.name)} ${(this.surname)} ${(this.age)} ${(this.area)}
}
```
Super() fonksiyonu, alt class oluştururken üst classtan değişkenleri miras almak için kullandığımız fonksiyondur.
`Subclass tanımlamak için:`
```javascript
const sub1 = new subClass('marmara')  //undefined
```

`Obje ve Class farkı`: Objeleri değişken oluşturmak için kullanırız. Class ise nesne oluşturmak için sadece başlangıç keylerini verdiğimiz yapıdır. (içinde subclasslar olabilir.)

Bir objeden 1'den fazla obje oluşturamayız Oluşturabiliz ama her seferinde değişkeni tanımlamamız gerekir. Bu da effective deği. Ya da daha komplex yapılarda zorlayıcıdır.

## Getters and Setters
Bir sınıfın verilerine erişimi kontrol etmek ve yönetmek için kullanılır.

Get: Bize görünen kısmı değiştirmek için kullanılır.

Set: Değeri değiştirmek için kullanılır.
```javascript
class employees {
  constructor(name, surname, age) {
    this.name = name
    this.surname = surname
    this.age = age
    this.firm = 'abc ltd. şti.' //Sabit de verebiliriz.
  }
  get name() {
    return this.name // ile içerdekine ulaşabiliyorum.
  }
  fullName = function(){
    return '${this.name} ${this.surname} ${this.age}'
  } 
}
const employee1 = new employees(name:'Ali', surname:'Veli', age: 34)

employee1.fullName // fullname'e ulaşmak için
```
## Senkron ve Asenkron Programlama
Senkron: İşlerin sırasıyla yapıldığı ve işlerin her birinin birbirini beklediği durumdur.

Asenkron: Yine işlerin sırasıyla yapıldığı ancak işlerin birbirini beklemediği durumdur.

Javascript'de yapısı itibariyle asenkrondur.
```javascript
function yaz() {
  console.log('başla')
  setTimeout(() => console.log('orta', 2000)
  console.log('bitir')
```
SetTimeout 2 parametre alır;

1- Fonksiyon

2- Fonksiyonun ne kadar süre sonra çalıştıralacağı

Output:
```
başla
bitir
orta 
```
Senkron olmadığı için 'orta' bitmeden 'bitir' e geçiyor. Bu yüzden önce bitir çıktısını alıyoruz. 

`Senkron olmasını istiyorsak: async ya da await kullanabiliriz.`
```javascript
function yaz() {
console.log('başla')
await.setTimeout(() => console.log('orta', 2000)
console.log('bitir')
```
## Callback Function
Callback fonksiyonları, başka bir fonksiyonun parametre olarak alındığı veya başka bir fonksiyon içinde çağrıldığı fonksiyonlardır. Sıralı işlemler için kullanılır.
 ```javascript
function printOrder(param) {
  console.log(param)
  }
function printAll() {
  printOrder("1", () => {
    printOrder("2", () => {
      printOrder("3", () => {
      })
    })
  })
}
```
Yazım olarak daha kolayı(iç içe yazmaktan kurtarır:
 ```javascript
function printAll2 = () => {
  printOrder("1") 
    .then(() => printOrder ("2"))
    .then(() => printOrder ("3"))
    .catch((err) => console.log(err)) //Herhangi bir hata olması durumunda bu hatayı burda yakalayabiliriz.
```
ÖRNEK1:
 ```javascript
function printAll3 = () => {
  printOrder("Gelen veriyi oku") // 100ms
    .then(() => printOrder ("veriyi update et")) //3000ms
    .then(() => printOrder ("yeni veriyi döndür")) //300ms
    .catch((err) => console.log(err))
```
Burda update etme işleminin süresi daha uzun olduğu için, update yapmadan yeni diğer veriyi geriye döndürür.

ÖRNEK2: Bir e-ticaret sitesinin ürünü ve parayı tuttuğu veritabanı farklı olsun. Müşteriden satın alma isteği geldi, isteği kontrol etti=>

1-müşterinin bakiyesi ürünü almaya yeterli mi 

2-Ürünün stoğu var mı

!Bunların birbirini beklemesi gerekiyor. 

Satın alma işlemini yaptıktan sonra ürün stoğunu düşürmen gerek. Ürünün stoktan düşmesi ise müşterinin bakiyesinin düşmesine bağlı.
 ```javascript
const  satinAl = (müşteri, ürün) => {
  bakiyeKontrol (müşteri) //geriye tru false değer döndürür.
    .then((uygunmu) => {
      if(uygunmu) {
        stokKontrol(ürün) // yine T-F döner.
          .then((stokUygunluk) => {
            if(stokUygunluk) {
              bakiyeDüş(
                .then(() => {
                  stokDüşür()   // then ile yapmadık çünkü stokDüşür ile başarıMesajı birbirini beklemek zorunda değil.
                  başarıMesajı()
                })
            }
            else {
              return 'stok bitti'
            }
          })
     }
      else {
      return 'yetersiz bakiye'
     }
    })
    .catch((err) => 'hata' + err)
}
      
```
## Promise
Bir işlemin sonucunu temsil eder. Resolve ve Reject adında 2 tane parametre alır ve olumlu durumlarda Resolve ile belirtilen işlemleri, olumsuz durumlarda Reject ile belirtilen işlkemlerin yapılacağına dair güvence verir.
 ```javascript
const yaz = (value) => {
  return new Promise((resolve, rejected) => {
    if(value.lenght >= 5) {
      setTimeout(() => {
        console.log(value)
        resolve()
 } 4000)
    } else {
        reject('koşul sağlanmadı yazı kısa:' + value)
    }
  })
}

const hepsiniYaz1 = () => {
  yaz('Serkan')
    .then(() => yaz('Yetkin'))
    .then(() => yaz('Mert'))
    .then(() => yaz('Sabri')) 
    .catch((e) => console.log(e))
}
```
## Promise All
Birden fazla promise varsa ve her birinin düzgün çalıştığına emin olmak istiyorsak kullanırız. Then ve catch bloğuna yönlendirmemize sağlar.
 ```javascript
const allP = Promise.all([hepsiniYaz1, hepsiniYaz2])
allP
  .then(() => {})
  .catch((e) => console.log(e))
 ```
## All Settled
Yine birden fazla promise olduğunda kullanılır. Ancak hem düzgün çalışanı hem de reject sonucunu gösterir.

const allSett = Promise. allSettled([hepsiniYaz1, hepsiniYaz2])

allSett
  .then((res) => { })

 ## async and await
  ```javascript
async function bekleH() {
  await hepsiniYaz()
  await hepsiniYaz()

}
 ```



