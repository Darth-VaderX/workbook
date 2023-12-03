# Создание сервера
____
Для начала работы необходимо импортировать модуль `http`:
```
import http from 'http';
```

Метод __createServer()__ - запуск сервера. Метод принимает коллбэк функцию, а та принимает два параметра. В первый параметр попадет объект с данными запроса пользователя, а во второй параметр - объект, с помощью которого мы сфомируем наш ответ, отправляемый в браузер.
Метод __write()__ - формируем текст для ответа в браузер.
Метод __end()__ - завершение ответа и отправка его в браузер.

Свойство __statusCode__ - указывание кода HTTP ответа.
Mетод __setHeader()__ - отправляeт HTTP заголовки
Mетод __writeHead()__ - первым параметром этот метод принимает код ответа, а вторым - объект с заголовками.
```
http.createServer(async (request, response) => {
    let path = 'app' + request.url;
    let status, text;
    try {
        if ((await fs.promises.stat(path)).isDirectory()) path += '/index.html';
        status = 200;
        text = await fs.promises.readFile(path);

    } catch (error) {
        status = 404;
    }
    response.writeHead(status, {'Content-Type': `${getMimeType(path)}`});
    response.write(text);
    response.end();
}).listen(3000);
```
Объект запроса __request__ содержит данные запроса браузера к серверу. В этом объекте свойство `url` содержит адрес запрошенной страницы, свойство `method` содержит HTTP метод запроса, а свойство `headers` содержит массив отправленных заголовков.

[Модуль FS](native/filesystem.md)<br>
[Константы FS](native/constFs.md)<br>
[Dirname](native/dir.md)<br>
[Stream](native/stream.md)<br>
[MIME-type](native/mime.md)<br>