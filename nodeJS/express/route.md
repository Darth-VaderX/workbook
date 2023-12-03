# Маршруты в Express
____
Сливание маршрутов в один:
```
const app = express();

app.get('/users/:num/', async (req, res) => {
    const path = __dirname + '/app/users/' + req.params.num + '.html';
    try {
        await fs.access(path, constants.F_OK);
        res.sendFile(path);
    } catch (error) {
        res.status(404).send('file not found');
    }
})
```
Параметры позволяют положить часть адреса в переменную. Переданные параметры содержатся в свойстве params объекта запроса. Чтобы сделать параметр необязательным после него нужно добавить знак `?`;
```
app.get('/test/:num?/', function(req, res) {
	
});
```
Создание роутера для похожих адресов:
```
let userRouter = express.Router(); 
=>
userRouter.get('/show/:id', function(req, res) {
	
});
userRouter.get('/edit/:id', function(req, res) {
	
});
=> 
app.use('/user/', userRouter);
```
