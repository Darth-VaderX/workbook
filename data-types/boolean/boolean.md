# Boolean
____
__Boolean__ - это примитивное значение, который может содержать `true` или `false`.

#### Шпаргалка по “инстинным” и “ложным” значениям в JavaScript
```
Boolean(false);     // false
Boolean(undefined); // false
Boolean(null);      // false
Boolean('');        // false
Boolean(NaN);       // false
Boolean(0);         // false
Boolean(-0);        // false
Boolean(0n);        // false

Boolean(true);      // true
Boolean('hi');      // true
Boolean(1);         // true
Boolean([]);        // true
Boolean([0]);       // true
Boolean([1]);       // true
Boolean({});        // true
Boolean({ a: 1 });  // true
```

### Методы преобразования к типу Boolean

* __Скрытое приведение__ инициируется движком JavaScript и происходит автоматически
* __Явное приведение__ происходит в “ручном режиме” с использованием встроенных способов JavaScript - оператора `"!!"` и функции `Boolean()`.

#### Оператор "!!"
Знак `!` приводит значение к логическому и инвертирует его. `!!` - второй знак снова инвертирует полученное значение.
```
const value = 'true';

!value  // false
!!value // true
```
### Функция Boolean()
`Boolean()` - это глобальная функция, которая конвертирует значение, переданное в него, в логическое.
```
const value = 'true';
Boolean(value) //true
```

[Примитивы](../primitive.md)<br>
[Типы данных](../data-types.md)<br>
[Главное меню](../../README.md)<br>