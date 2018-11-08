
# ������ �������� ��������� JS ����

## ��������� ���������� ����������.  
- ��������������� ������������� ���������� ����������. ��� �������� ������ ���� �����, ��������, �������.  
���������� ���������� � ������� ����� ���� ������������ ������ ��������.  
- ����������� ������ ��� ��������� ����������,� ������� ������������ ���������.


## ���������� �������  

���������� ���������� ������� �������, �������:

- ������ ��� ����.
- ��������� �������� ������������� ��������� ����������.
- ������� ����������� ������������� ��������������.    

__������:__  
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


## ������������� ����������
������������� ���������� � ������ �� ����������:  
- ������ ��� ����.
- ��������� �������� ������������� ����������.    

__������:__  
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


## ������� �� ���������� �����, ������, ��� ������� �������� ��� �������  
��������� �� ������� ������ ��� ���������.  
���������� ���� ����� ��� ��������, ������� ������������������ � �������� � �������������.  

__������:__
```
var x = "John";             
var y = new String("John");
(x === y) // is false because x is a string and y is an object
```


## ����������� ������� ���������  
�������� == ������ ������������ ����� ����������.  

__������ ��������� �������� ��������� �����:__  
```
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```

## ����������� �������� �� ���������  
���� ������� ������� � ����������� ����������, �������� ��� ��������� = undefined. ��� ����� ������� ��� ���.  

__������:__  
```
function myFunction(x, y) {  
    if (y === undefined) {  
        y = 0;  
    }  
}  
```


## ����������� hasOwnProperties  
���� ����� ������������ ����� ������������� ��������, �� ����������� � �������� �������.   
��� ������������� ����� for-in �������� ����� �������� �������� � ������, ������ ���� � ������� ����������. � ����������� ������� � ��� �� ����� ����� ������ �� ��� ��� ������������ �������. 

__������:__    
```
Function Dog (name) {  
    this.name = name;  
}  
Dog.prototype.legs = 4;  
Dog.prototype.speak = function () {  
    return "���!";  
};  
var d = new Dog("�����");  
for (var prop in d) {  
  if (d.hasOwnProperty(prop)) {  
    console.log( prop + ": " + d[prop] );  
  }  
}  
// ����������:  
// name: �����  
// legs: 4  
// speak: function () {  
        return "���!";
```  



## ���������� ���������� ������� ����� for    
�� ���� ��������� ������� ������� ����������� �����, ��� ��� ���������, �������� ���� ����������� ������� ��� ������ �����.  

__������:__    
```
//�����  
for(var i = 0; i < someArray.length; i++) {    
   var container = document.getElementById('container');    
   container.innerHtml += 'my number: ' + i;  
   console.log(i);  
}  
```  
��� ������ �������� ����� ���� ��������� � DOM �������.    
```
//������  
var container = document.getElementById('container');  
for(var i = 0, len = someArray.length; i < len;  i++) {  
   container.innerHtml += 'my number: ' + i;  
   console.log(i);  
}
```



## ���������� �����������  
��� ����� ���������� ��������������, �� � ����������, ����������� ������� ���������� ����.   

__������:__      
```  
// Cycle through array and echo out each name.     
for(var i = 0, len = array.length; i < len; i++) {    
   console.log(array[i]);    
}
```  


## �� ���������� ������ � "SetInterval" ��� "SetTimeOut"

__������:__      
```
setInterval(    
"document.getElementById('container').innerHTML += 'My new number: ' + i", 3000    
);  
```
���� ��� �� ������ �� ����������, �� ��� �������������, ��� ��� ������������� "eval". ����� ������������ ��� �������.  
```
setInterval(someFunction, 3000);
```




























































