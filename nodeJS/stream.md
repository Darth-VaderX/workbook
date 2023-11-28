# Потоки
____

Потоки позволяют работать с большими файлами по кусками с целью ибежания перегрузки сервера. 
Mетод __createReadStream__ - создаёт поток для чтения файла.
```
let readStream = fs.createReadStream('readme.txt', 'utf8');
readStream.on('data', function(chunk) { 
	console.log(chunk);
});
```

Mетод __createWriteStream__ - создаёт поток для записи файла.

```
let writeStream = fs.createWriteStream('writeme.txt');
writeStream.write('text1');
writeableStream.end();
```

Частая ситуация, когда нужно прочитать данные из одного потока и записать их в другой. Для упрощения такой операции придуманы каналы (_pipes_).
```
const readStream = fs.createReadStream('file.txt', 'utf-8');
const writeStream = fs.createWriteStream('clone.txt');
readStream.pipe(writeStream)
```

Методы __pipe__ можно вызывать цепочкой друг за другом. При этом каждый вызов метода в цепочке позволяет выполнять над данными некоторые операции: _readableStream.pipe(операция).pipe(операция).pipe(операция)_;

[Модуль FS](filesystem.md)<br>
[Константы FS](constFs.md)<br>
[dirname](dir.md)<br>
[NodeJS](nodeJS.md)<br>