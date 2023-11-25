# Методы объекта Number
___
* <a href="#isNan">isNan()</a>
* <a href="#isFinite">isFinite()</a>
* <a href="#isInteger">isInteger()</a>
* <a href="#isSafeInteger">isSafeInteger()</a>
* <a href="#toExponential">toExponential()</a>
* <a href="#toPrecision">toPrecision()</a>
* <a href="#number">Number()</a>
* <a href="#parseInt">parseInt()</a>
* <a href="#parseFloat">parseFloat()</a>

<span id="isNan">Метод</span> __Number.isNaN()__ — нативный способ проверить значение на NaN. В отличие от других возможных значенияхв JavaScript, при работе с значением данного типа невозможно полагаться на `==` и `===` для определения, является липеременная или литерал нечисловым значением (NaN) или нет, потому что NaN не равен ничему, даже самому себе.Следовательно, для проверки нужна функция isNaN.

```
const nanResult = 5 * undefined
console.log(nanResult == NaN)        // false
console.log(nanResult === NaN)       // false
console.log(Number.isNaN(nanResult)) // true
```

<span id="isFinite">Метод</span> __Number.isFinite()__ — для проверки параметра на то, что он является конечным числом. Конечное число — это число, которое не равно `NaN` или `±Infinity`. Есть исключения: пустая строка '' возвращает true, строка с пробелами '    ' также возвращает true, null возвращает true, для значений true и false также возвращается true. Это происходит потому, что эти значения преобразуются в числа, а не в NaN.
__Number.isFinite()__ - это более надежный способ проверить, является ли значение конечным числом, поскольку он возвращается falseдля любого нечислового ввода.

```
isFinite(Infinity);  // false
isFinite(NaN);       // false
isFinite(-Infinity); // false

isFinite(0);         // true
isFinite(2e64);      // true
isFinite(910);       // true
```

<span id="isInteger">Метод</span> __Number.isInteger()__ определяет, является ли переданное значение целым числом. Если целевое значение является целым числом, возвращает true. Если значение NaN или Infinity, то возвращает false.

```
Number.isInteger(25)       //true
Number.isInteger(-1)       //true
Number.isInteger(15-2)     //true
Number.isInteger(0)        //true
Number.isInteger(0.25)     //false
Number.isInteger('55')     //false
Number.isInteger(false)    //false
Number.isInteger(Infinity) //false
```

<span id="isSafeInteger">Метод</span> __Number.isSafeInteger()__ определяет, является ли переданное значение безопасным __целым__ числом(безопасные целые числа от `-(253 - 1)` до `253 - 1` включительно `(±9.007.199.254.740.991)`). Позволяет легко и надежно проверять, находится ли число в пределах диапазона безопасных целых чисел, и предотвращает возможные ошибки при работе с большими числами или индексами массива.

```
Number.isSafeInteger(NaN);      // false
Number.isSafeInteger(Infinity); // false
Number.isSafeInteger("3");      // false
Number.isSafeInteger(3.1);      // false
Number.isSafeInteger(3.0);      // true
```

<span id="toExponential">Метод</span> __Number.toExponential()__ используется для преобразования числа в экспоненциальную форму записи. Он возвращает строку, представляющую число в виде мантиссы и показателя степени.

```
const number = 123456789;
console.log(number.toExponential()); // 1.23456789e+8

В примере число 123456789 преобразуется в строку "1.23456789e+8", где "e+8" означает, что число умножается на 10 в степени 8. Это эквивалентно записи 1234567890.
```
__toExponential()__ принимает один необязательный аргумент - количество символов после десятичной точки. По умолчанию используется 6 символов. Пример, который указывает 2 символа после десятичной точки:
```
const number = 123.456;
console.log(number.toExponential(2)); // 1.23e+2

В примере число 123.456 преобразуется в строку "1.23e+2"
``` 
__toExponential()__ особенно полезен для работы с очень большими или очень маленькими числами, которые могут быть трудны для чтения в обычной десятичной форме. Когда число достигает или превышает 21 разряд, JavaScript автоматически переключается в использование экспоненциальной формы.

<span id="toPrecision">Метод</span> __Number.toPrecision()__ возвращает строку, представляющую объект Number с указанной точностью. Если параметр опущен, метод вернет все число (без форматирования).

```
let number = 15.3525;
let a = num.toPrecision();   // 15.3525
let b = num.toPrecision(2);  // 15
let c = num.toPrecision(4);  // 15.35
let d = num.toPrecision(10); // 15.35250000
let number = 0.002846591;
let a = num.toPrecision();   // 0.002846591
let b = num.toPrecision(2);  // 0.0028
let c = num.toPrecision(3);  // 0.00285
let d = num.toPrecision(10); // 0.002846591000
```

## Методы преобразования к числу

__Number__ <span id="number">преобразует</span> переданное значение в число. В случае строки пробельные символы по краям обрезаются, затем, если строку возможно преобразовать в число - то возвращается это число, а если нет - возвращается NaN. Значение true преобразуется к числу 1, значение false - к числу 0. Объекты при численных преобразованиях превращаются в NaN.

```
Number(true);  // 1
Number(false); // 0
Number('53');  // 53
Number(' 5 '); // 5
Number('a5');  // NaN
Number([]);    // 0
```

Метод __parseInt__ <span id="parseInt">преобразует</span> строку в целое число. Это нужно для значений типа '12px' - когда вначале стоит число, а потом единицы измерения. Если применить parseInt к '12px', то результатом получится число 12 (и это будет число, а не строка). Преобразование произойдет, если только целое число стоит в начале строки, иначе будет выведено NaN. Вторым параметром можно указать систему счисления числа, и функция вернет число, переведенное из указанной системы счисления в десятичную.
```
parseInt("15 * 3", 10);   // 15
parseInt("15e2", 10);     // 15
parseInt("15px", 10);     // 15
parseInt("12", 13);       // 15
parseInt("Hello", 8);     // NaN
```

Метод __Number.parseFloat()__ <span id="parseFloat">принимает</span> строку в качестве аргумента и возвращает десятичное число (число с плавающей точкой). Этот метод ведёт себя идентично глобальной функции parseFloat(). Если первый символ не может быть сконвертирован в число, то возвращается NaN. Все примеры ниже вернут 3.14.

```
Все операции вернут 3.14
parseFloat(3.14);
parseFloat('3.14');
parseFloat('314e-2');
parseFloat('0.0314E+2');
parseFloat('3.14какие-нибудь не цифровые знаки');
```


[Number](number.md)<br>
[Примитивы](../primitive.md)<br>
[Типы данных](../data-types.md)<br>
[Главное меню](../../README.md)<br>