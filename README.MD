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