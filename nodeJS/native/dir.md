# Константа dirname
____
Если Node.JS работает на [Common.js](../ecmaScript/commonjs.md), то в файлах с скриптами будет доступна константа `__dirname`. В [ES](../ecmaScript/ecmaScript.md) модулях, эта константа была убрана но ее можно получить самому. Для этого нужен файл `__dirname.js`, экспортирующий нужный нам путь к папке со скриптом:
```
__dirname.js
import { dirname } from 'path';
import { fileURLToPath } from 'url';

const __dirname = dirname(fileURLToPath(import.meta.url));
export default __dirname;

index.js
import __dirname from './__dirname.js';
```
[Модуль FS](native/filesystem.md)<br>
[Константы FS](native/constFs.md)<br>
[Stream](native/stream.md)<br>
[MIME-type](native/mime.md)<br>
[Create Server](native/server.md)<br>
