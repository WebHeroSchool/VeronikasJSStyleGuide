### VeronikasJSStyleGuide   :wink:
 ---
 # *10 правил стиля  JavaScript*
 ---
 ##### [1. Oбъявлениe массивов](#1)
 ##### [2. Объявление функций](#2)
 ##### [3. Объявление переменных](#3)
 ##### [4. Интерполяция](#4)
 ##### [5. Строки](#5)
 ##### [6. Создавать объекты с помощью{}](#6)
 ##### [7. Классы и конструкторы](#7)
 ##### [8. CamelCase](#8)
 ##### [9. Стрелочные функции](#9)
 ##### [10. Запятые](#10)

 
 ### <a name="1"> Объявлениe массивов</a>
 ---
 Используй квадратные скобки [ ] для объявления массивов.
 
 ``` js
 // Bad
const items = new Array();

// Good
const items = [];
```

 ### <a name="2">Объявление функций</a>
 ---
 JavaScript позволяет не ставить точку с запятой, но иногда бывают случаи, когда перенос строки не интерпретируется, как точка с запятой, что может привести к ошибкам.Когда JavaScript встречает перенос строки без точки с запятой, он использует правило под названием Автоматическая Вставка Точки с запятой (Automatic Semicolon Insertion), чтобы определить, стоит ли считать этот перенос строки как конец выражения и поместить точку с запятой в вашем коде до переноса строки. 

 ``` js
 // Bad
 const cat = {}
 const dog = {}
 [cat, dog].forEach((animal) => animal.kind = 'mammal')

 // Good
 const cat = {};
 const dog = {};
 [cat, dog].forEach((jedi) => {
   animal.kind = 'mammal'';
 });
 ```

 ### <a name="3">Объявление переменных</a>
 ---
 Рекомендуется использовать const и let, ключевое слово var устарело и не рекомендуется его использовать. Всегда используйте const, но если планируете перезаписывать значение создаваемой переменной то используйте let.

 ``` js
 // Bad
 var name = 'Alex';
 var age = 20;
 
 // Good
 const name = 'Alex';
 let age = 20;
 ```
 Помните, что у let и const блочная область видимости.

 ### <a name="4">Интерполяция</a>
 ---
 Использовать интерполяцию вместо конкатенации.

  ``` js
 // Bad
 function sayHi(name) {
   return 'How are you, ' + name + '?';
 }

 // Good
 function sayHi(name) {
   return `How are you, ${name}?`;
 }
 ```

 ### <a name="5">Строки</a>
 ---
 Используйте одинарные кавычки '' для строк.

 ``` js
 // Bad
const name = "Mary";
 
 // Good
const name = 'Mary';
 ```

 Строки, у которых в строчке содержится более 100 символов, не пишутся на нескольких строчках с использованием конкатенации.

 ``` js
 // Bad
const errorMessage = 'This is a super long error that was thrown because \
 of Batman. When you stop to think about how Batman had anything to do \
 with this, you would get nowhere \
 fast.';
 
// Good
const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';
```

 ### <a name="6">Создавать объекты с помощью {}</a>
 ---
 Для создания объектов лучше использовать фигурные скобки, а не конструктор new Object.

 ``` js
 // Bad 
 let obj = new Object();

 // Good
 let obj = {};
 ```
 
 ### <a name="7">Классы</a>
 ---
 Всегда используйте `class`. Избегайте прямых манипуляций с `prototype`, синтаксис `class` является кратким и понятным.

 ``` js
 // Bad

 function Queue(contents = []) {
  this.queue = [...contents];
 }
 Queue.prototype.pop = function () {
   const value = this.queue[0];
   this.queue.splice(0, 1);
   return value;
 };

// Good
class Queue {
  constructor(contents = []) {
    this.queue = [...contents];
  }
  pop() {
     const value = this.queue[0];
     this.queue.splice(0, 1);
     return value;
   }
 }
 ```

 ### <a name="8">CamelCase </a>
 ---
 Использовать camelCase для именования функций и переменных.

  ``` js
 // Bad
 let OBJEcttsssss = {};
 let this_is_my_object = {};
 function c() {};
 let u = new user({
   name: 'Bob Parr'
 });

 // Good
 let thisIsMyObject = {};
 function thisIsMyFunction() {};
 let user = new User({
   name: 'Bob Parr'
 });
 ```
  
 ### <a name="9">Cтрелочные функции</a>
 ---
 Там где это возможно, лучше пользоваться стрелочными функциями, они делают синтаксис более лаконичным и приятным.

 ``` js
 // Bad
 [1, 2, 3].map(function (x) {
   const y = x + 1;
   return x * y;
 });

 // Good
 [1, 2, 3].map((x) => {
   const y = x + 1;
   return x * y;
 });
 ```

 ### <a name="10">Запятые</a>
 ---
 Не начинайте строку с запятой.

``` js
// Bad
 const story = [
     once
   , upon
   , aTime
 ];

// Good
 const story = [
   once,
   upon,
   aTime,
 ];
 ```
 
 ## May the JS be with you
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
