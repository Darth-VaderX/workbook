# ECMAScript
____

JavaScript был выпущен в компании `NetScape Navigator` в 1995 году, но его изначальное название было другим — __LiveScript__. Через год, в попытках придать ему больший охват и популярность его переименовали в JavaScript, пытаясь сыграть на популярном в то время языке __Java__. в 1996 году NetScape попросил ECMA International стандартизировать JavaScript. Это привело к появлению официального стандарта ECMAScript. Таким образом __ECMAScript__ — это стандарт на котором базируется язык JavaScript, a __ES6__, __ES5__ и т.д. - версии стандарта.

## Использование ЕCMAScript-модулей в Node.JS
__ECMAScript-модули__ (кратко их называют ES-модулями) — это модули, формат которых описан в стандарте ECMAScript, при работе с которыми используются инструкции `import` и `export`:

```
import myFunc from './my-func';

export myOtherFunc(param) {
  const result = myFunc(param);
  // ....
  return otherResult;
}
```

На платформе Node.js по умолчанию используются модули формата CommonJS. Node.js сможет использовать ES-модули в следующих случаяx:

* Если файл модуля имеет расширение `.mjs`
* Eсли в package.json имеется конструкция { «type»: «module» }
* Eсли при запуске Node.js используется флаг `--input-type=module`, и при этом код модуля передаётся платформе в виде строки с использованием аргумента `--eval="<module-code>"`, или поступает из __STDIN__.

[CommonJS](commonjs.md)<br>
[Главное меню](../README.md)<br>