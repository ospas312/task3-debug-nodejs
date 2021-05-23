++ task3 debug nodejs


1 var router = Router(); ReferenceError: Router is not defined
var router = Router();//var router = require('express').Router();

2 internal/modules/cjs/loader.js:888
  throw err;
  ^
Error: Cannot find module 'bcrypt'
Require stack:
var bcrypt = require('bcrypt');//var bcrypt = require('bcryptjs');

3 var User = require('../db').import('../models/user');
TypeError: require(...).import is not a function
var User = require('../db').import('../models/user');//var User = require('../models/user');

4 var Game = require('../db').import('../models/game');
TypeError: require(...).import is not a function
var Game = require('../db').import('../models/game');//var Game = require('../models/game');

5 function(sequelize, DataTypes) {
^^^^^^^^
SyntaxError: Function statements require a function name
function(sequelize, DataTypes) {//module.exports = function(sequelize, DataTypes) {

6 module.exports = routers;
                 ^
ReferenceError: routers is not defined
module.exports = routers;//module.exports = router;

7 db.sync();
   ^
TypeError: db.sync is not a function
db.sync();// module.exports = sequelize

8 var User = require('sequelize').import('../models/user');
                                      ^
TypeError: require(...).import is not a function
var User = require('sequelize').import('../models/user');//var User = require('../models/user');

9 не было порта 4000 

10 не конектилось с базой без указания порта в    port: "5433" и переустановки pg до версии 8

11 //app.use(require('body-parser'));//??? 

12 разные имена переменных  passwordhash: в моделе  passwordHash:

13 jwt.verify(sessionToken.split(' ')[1], 'lets_play_sum_games_man', (err, decoded) => { не знаю ошибка это или нет если запрос делать то надо убирать из строки Bearer 

14    в gamecontroller   games: games  //    games: data,

15   router.put('/update/:id', (req, res) => {   не был указан id           owner_id: req.user.id

16 router.post('/create', (req, res) => {
    Game.create({
        title: req.body.game.title,
        owner_id: req.body.user.id,  надо req.user.id
можно в body передавать айди любого юзера и оно создаст игру для любого юзера --- логич


3 пункт 
Найденные ошибки компиляции:

<не правильно импортирован Router>.<импортирован Router>.Исправлена(ы) строка(и) <1> в файле <./controllers/usercontroller.js>

<ошибка в названии импортированой зависимости  bcrypt>.<исправлена на bcryptjs>.Исправлена(ы) строка(и) <2> в файле <./controllers/usercontroller.js>

<в db отсутствует экспорт sequelize>.<добавил экспорт sequelize>. Исправлена(ы) строка(и) <19>
в файле <./db.js>

<неправильный импорт модели User из db>.<исправлен импорт модели User>.Исправлена(ы) строка(и) <5-6> в файле <./controllers/usercontroller.js>

<неправильный импорт модели Game из db>.<исправлен импорт модели User>.Исправлена(ы) строка(и) <2-3> в файле <./controllers/gamecontroller.js>

<нет экспорта модели game>.<добавлен module.exports к функции>.Исправлена(ы) строка(и) <1>в файле <./models/game.js>

<ошибка в названии эекспорта routers>.<исправлен на router>.Исправлена(ы) строка(и) <116> в файле <./controllers/gamecontroller.js>

<неправильный импорт модели User из db>.<Испроавлен импорт модели User>.Исправлена(ы) строка(и) <2-3>в файле <./middleware/validate-session.js>

<не указан порт в app.listen>.<указал порт 4000>.Исправлена(ы) строка(и) <13>в файле <./app.js>

не уверен ошибка нет <не подключаеться к базе из за версии модуля pg при обновлении до последней работает.>.<обновление версии pg до последней>.
Исправлена(ы) строка(и) <13> в файле <./package.json>

Найденные ошибки логики приложения

<не подключен bodyParser>.<правильно использован bodyParser для пробросса в body параметров>.Исправлена(ы) строка(и) <7,10,11>в файле <./app.js>

<ошибка в переменной написанно passwordhash вместо passwordHash>.<переименовал passwordhash в passwordHash>.Исправлена(ы) строка(и) <12>в файле <./controllers/usercontroller.js>

<не уверен ошибка или нет что секретная строка не вынесена>.<оставил как есть но в идеале надло вынести>. строка(и) <17,35>в файле <./controllers/usercontroller.js> 

<если запрос делать то надо убирать из строки Bearer  jwt.verify(sessionToken>.<исправил на jwt.verify(sessionToken.split(' ')[1],>. строка(и) <13>в файле <./middleware/validate-session.js>

<в .then получаем data а присваиваем  games>.<измененно с games на data>. Исправлена(ы) строка(и) <10> в файле <./controllers/gamecontroller.js>

<ошибка в опциях в присвоении вместо req.user.id было req.user>. <исправленно с req.user на req.user.id>.Исправлена(ы) строка(и) <75>в файле <./controllers/gamecontroller.js>

<неправильное обращение к user.id в Game.create>.<исправленно обращение с неправильного req.body.user.id на правильное req.user.id>.Исправлена(ы) строка(и) <45>в файле <./controllers/gamecontroller.js>

<можно в body передавать айди любого юзера и оно создаст игру для любого юзера>.
<исправленно обращение с неправильного req.body.user.id на правильное req.user.id>.
Исправлена(ы) строка(и) <44> в файле <./controllers/gamecontroller.js>

Рефактор кода:
Проведен рефактор кода, var заменены на const, убраны лишние отступы, добавлены запятые и др.