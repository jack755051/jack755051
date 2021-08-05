# JS觀念釐清

## 物件
###### tags: <font color="#ff0">物件中資料是以key：value的形式儲存。</font>
###### tags: <font color="#ff0">JavaScript是一種基於物件的語言</font>


所有基本型別以外的均稱為物件

    基本型別
    string、number、boolean、null、undefined
    
    物件型別
    object、array、function
    
    判別型別null
    - worng - typeof null => object
    - right - typeof null => function
    
>一個物件可以是個零至多種屬性的集合，
>屬性是鍵 (key) 與值 (value) 之間的關聯。
>一個屬性的「值」可以是基本型別 / 另一個物件 / 一個函數
>物件可以是瀏覽器預先定義好的，也可以是由自己定義物件的屬性與內容。



---
### 物件及屬性

早期物件新增使用：

````javascript
    var person = new Object();
    person.name = 'Kuro';
    person.job = 'Front-end developer';
    person.sayName = function() {
      alert( this.name );
    };
````

現在物件使用方法
 ````javascript
    var person = {
      name: 'Kuro',
      job: 'Front-end developer',
      sayName: function() {
        alert( this.name );
      }
    };
````

以{ }建立物件的方法->物件實字 (Object literal)

---
### 屬性存取

物件的屬性可以透過` . `來進行存取：
````javascript
var person = {
  name: 'Kuro',
  job: 'Front-end developer',
  sayName: function() {
    alert( this.name );
  }
};

person.name;         // 'Kuro'
person.sayName();    // 'Kuro'
````
或是可以透過 `[ ]` 來進行存取，如：
````javascript
var person = {
  name: 'Kuro',
  job: 'Front-end developer',
  sayName: function() {
    alert( this.name );
  }
};

person["name"];         // 'Kuro'
person["sayName"]();    // 'Kuro'
````
屬性新增與刪除與判斷存在
- 新增屬性：`=`
- 刪除屬性：`delete`
- 判斷存在：` undefined`、`in`與`hasOwnProperty()`方法

## 陣列 Array

>JavaScript 的陣列可以看作是一種特別的「物件」
>同樣是零至多個元素的集合
>陣列是個有順序性的集合，且只能透過`[]`來存取

建立陣列同樣也可以透過 new 關鍵字來建立：
 ````javascript
var a = new Array();

a[0] = "apple";
a[1] = "boy";
a[2] = "cat";

a.length;     // 3
````
但現在實務上更常見的是陣列實字 (Array literal)：
 ````javascript
var a = [];

a[0] = "apple";
a[1] = "boy";
a[2] = "cat";

a.length;     // 3
````
或是：
 ````javascript
var a = ["apple", "boy", "cat"];
a.length;     // 3
````

