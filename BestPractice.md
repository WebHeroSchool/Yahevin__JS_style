
# Лучшие практики написания JS кода

## Избегайте глобальных переменных.  
- Минимилизируйте использование глобальных переменных. Это касается данных всех типов, объектов, функций.  
Глобальные переменные и функции могут быть перезаписаны другим скриптом.  
- Используйте вместо них локальные переменные,и учитесь использовать замыкания.


## Объявление вначале  

Объявление переменных вначале скрипта, функции:

- Делает код чище.
- Позволяет избежать нежелательных глоальных переменных.
- Снижает вероятность нежелательных переобъявлений.    

__Пример:__  
```
// Declare at the beginning  
var firstName, lastName, price, discount, fullPrice;  
// Use later  
firstName = "John";  
lastName = "Doe";  
price = 19.90;  
discount = 0.10;  
fullPrice = price * 100 / discount;  
```


## Инициализация переменных
Инициализация переменных в момент их объявления:  
- Делает код чище.
- Позволяет избежать неприсвоенных переменных.    

__Пример:__  
```
// Declare and initiate at the beginning  
var firstName = "",  
    lastName = "",  
    price = 0,  
    discount = 0,  
    fullPrice = 0,  
    myArray = [],  
    myObject = {};  
```


## Никогда не объявляйте числа, строки, или булевые значения как объекты  
Объявлять их следует только как примитивы.  
Объявление этих типов как объектов, снижает скоростьвыполнения и приводит к неприятностям.  

__Пример:__
```
var x = "John";             
var y = new String("John");
(x === y) // is false because x is a string and y is an object
```


## Используйте строгое сравнение  
Оператор == всегда конвертирует перед сравнением.  

__Пример сравнения значений различных типов:__  
```
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```

## Используйте значание по умолчанию  
Если функция вызвана с пропущенным аргументом, значение это аргумента = undefined. Это может сломать ваш код.  

__Пример:__  
```
function myFunction(x, y) {  
    if (y === undefined) {  
        y = 0;  
    }  
}  
```


## Используйте hasOwnProperties  
Этот метод используется чтобы отфильтровать свойства, не относящиеся к текущему объекту.   
При использвоании цикла for-in браузеры будут включать свойства и методы, идущие выше в цепочке прототипов. В большинстве случаев у вас не будет нужды видеть их все при перечислении свойств. 

__Пример:__    
```
Function Dog (name) {  
    this.name = name;  
}  
Dog.prototype.legs = 4;  
Dog.prototype.speak = function () {  
    return "Гав!";  
};  
var d = new Dog("Шарик");  
for (var prop in d) {  
  if (d.hasOwnProperty(prop)) {  
    console.log( prop + ": " + d[prop] );  
  }  
}  
// Результаты:  
// name: Шарик  
// legs: 4  
// speak: function () {  
        return "Гав!";
```  



## Объявляйте переменные снаружи цикла for    
Не надо нагружать процесс большим количеством задач, чем это требуется, особенно если выполняется длинный код внутри цикла.  

__Пример:__    
```
//Плохо  
for(var i = 0; i < someArray.length; i++) {    
   var container = document.getElementById('container');    
   container.innerHtml += 'my number: ' + i;  
   console.log(i);  
}  
```  
При каждой итерации цикла идет обращение к DOM объекту.    
```
//Хорошо  
var container = document.getElementById('container');  
for(var i = 0, len = someArray.length; i < len;  i++) {  
   container.innerHtml += 'my number: ' + i;  
   console.log(i);  
}
```



## Оставляйте комментарии  
Это может показаться необязательным, но в дальнейшим, комментарии повысят читаемость кода.   

__Пример:__      
```  
// Cycle through array and echo out each name.     
for(var i = 0, len = array.length; i < len; i++) {    
   console.log(array[i]);    
}
```  


## Не вставляйте строку в "SetInterval" или "SetTimeOut"

__Пример:__      
```
setInterval(    
"document.getElementById('container').innerHTML += 'My new number: ' + i", 3000    
);  
```
Этот код не только не эффективен, он еще функционирует, как при использовании "eval". Лучше использовать имя функции.  
```
setInterval(someFunction, 3000);
```




























































