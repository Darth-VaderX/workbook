# Константы FS модуля
____
Импорт констант из модуля:

```
import { constants } from 'fs';
```

После этого в переменной __constants__ будет специальный объект с константами, содержащими специальные флаги, которые можно передавать параметром в метод __access__, изменяя его поведение. Mетод access своим резульатом возвращает промис. Если файл существует, но промис зарезолвится, а если нет - то зареджектится.

* Флаг __constants.F_OK__ - проверка существование файла или папки
* Флаг __constants.R_OK__ - проверка возможности чтения файла
* Флаг __constants.W_OK__ - проверка возможности записи файла

Пример:
```
try {
	await fs.access('test.txt', constants.F_OK);
	console.log('file exists');
} catch {
	console.error('file does not exists');
}
```
[Модуль FS](native/filesystem.md)<br>
[Dirname](native/dir.md)<br>
[Stream](native/stream.md)<br>
[MIME-type](native/mime.md)<br>
[Create Server](native/server.md)<br>