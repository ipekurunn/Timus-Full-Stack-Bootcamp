```javascript
function count() {
  if (something) count()
}
```

kendini içerde tekrar çağıran fonksiyon (recursive)

## Switch - Case
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
`Note: ` Tek bir değişkene bakmamız gerekiyorsa Switch-case, daha komplex yapılar için ise if-else kullanırız.
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

`Class Inheritence`: Bir sınıfın başka bir sınıftan özellikleri ve davranışları miras alması anlamına gelir. 
```javascript
class subClass extends employees {
  constructor() {
    super(): //1- Bir öncekinden gelenleri aldım ve,
    this.area = area //2- area yı yanına eklemiş oldum.
  }
title = () => '${(this.name)} ${(this.surname)} ${(this.age)} ${(this.area)}
}
```
```javascript
const sub1 = new subClass('marmara')  //undefined
```

## Getters and Setters
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
`Obje ve Class farkı`: Objeleri değişken oluşturmak için kullanırız. Class ise nesne oluşturmak için sadece başlangıç keylerini verdiğimiz yapıdır. (içinde subclasslar olabilir.)

Bir objeden 1'den fazla obje oluşturamayız Oluşturabiliz ama her seferinde değişkeni tanımlamamız gerekir. Bu da effective deği. Ya da daha komplex yapılarda zorlayıcıdır.








