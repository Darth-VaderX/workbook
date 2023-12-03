# Фреймворк Express
____
Установки + импорт библиотеки + объект с приложением:
```
npm install express =>
import express from 'express' =>
const app = express();
```
Метод __app.get()__ - обработка запрашиваемого адреса
Mетод __app.use()__ - перехватывает необработанные адерса
Метод __res.send()__ - вывод текста в браузер
Mетод __res.sendFile()__ - вывод документа в браузер(абсолютный путь)
Метод __res.status()__ - изменить код ответа(по умолчанию 200)
Mетод __res.redirect()__  - перенаправление. По умолчанию код 302 (найдено). Можно изменить этот код первым параметром
Mетод __res.type()__ - изменить тип ответа

```
app.use(express.static(__dirname + '/app/')) - в этой папке будут автоматически искаться файлы, запрошенные браузером

app.get('/', (req, res) => {
    res.send('Server started!');
    res.redirect(301, '/');
    res.status(404).send('page not found')
    res.type('text/plain');
})

app.use((req, res) => {
    res.status(404)
})

app.listen(3000, ()=>{
    console.log('server: 3000')
});

```

Cвойствo __req.path__ - получить запрошенный адрес без протокола, хоста, порта и строки запроса
Cвойствo __req.url__ - получить запрошенный адрес с путем и строкой запроса
Cвойство __req.originalUrl__ - содержит оригинльный url
Cвойствo __req.query__ - получить строку запроса в виде объекта с ключами и значениями
Cвойствo __req.protocol__ - содержит протокол
Свойство __req.secure__ - содержит true для `HTTPS` протокола, и false - для обычного `HTTP`
Cвойствo __req.headers__ - получить заголовки запроса
Cвойствo __req.acceptsLanguages__ - получить предпочитаемые пользователем языки
свойства __req.ip__ - получить IP адрес пользователя
```
app.get('/dir/page.html', function(req, res) {
	console.log(req.path);        // выведет '/dir/page.html'
    console.log(req.url);         // выведет '/dir/page.html?get1=1&get2=2'
    console.log(req.originalUrl); // выведет '/dir/page.html?get1=1&get2=2'
    console.log(req.query);       // содержит объект {get1: '1', get2: '2'}
	console.log(req.protocol);    // выведет 'http'
    console.log(req.secure);      // выведет false
    console.log(req.headers);
    console.log(req.acceptsLanguages);
    console.log(req.ip);
});
```
