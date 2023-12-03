# MIME-types
____
__Изображения__
* image/gif
* image/jpeg
* image/jpeg
* image/png
* image/svg+xml
* image/webp

__Текст__
* text/css
* text/html
* text/javascript
* text/plain
* text/php
* text/markdown

Функция по расширению файла отдаёт его `MIME-type`:
```
function getMimeType(path) {
	let mimes = {
		html: 'text/html',
		jpeg: 'image/jpeg',
		jpg: 'image/jpg',
		png: 'image/png',
		svg: 'image/svg+xml',
		json: 'application/json',
		js: 'text/javascript',
		css: 'text/css',
		ico: 'image/x-icon',
	};

	let exts = Object.keys(mimes);
	let extReg = new RegExp('\\.(' + exts.join('|') + ')$');
	let ext = path.match(extReg)[1];

	return ext ? mimes[ext] : 'text/plain';
}
```

[Модуль FS](native/filesystem.md)<br>
[Константы FS](native/constFs.md)<br>
[Dirname](native/dir.md)<br>
[Stream](native/stream.md)<br>
[Create Server](native/server.md)<br>