# Оператор typeof
____
__typeof__ возвращает строку, которая содержит тип. Существует два синтаксиса использования:
* typeof параметр;
* typeof(параметр);

__Исключения__ 
 ```
   typeof null // "object"
 ```           
 Это официально признанная ошибка, которая сохраняется для совместимости. На самом деле [null](../data-types/null/null.md) – это не объект, а примитивное значение.

 ```
   typeof function(){} // "function"
 ```
 Функции не являются отдельным базовым типом, но typeof выделяет функции отдельно, возвращая для них `function`. На практике это весьма удобно, так как позволяет легко определить функцию

[Операторы](operators.md)<br>
[Главное меню](../README.md)<br>