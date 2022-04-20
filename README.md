# Notes for Express

## Start any project

1. Создаем (инициализируем проект). 
 
  `npm i -y` - отвечаем на все вопросы утвердительно, создается автоматически.  
  
   `npm i` / `npm install` - позволяет выбрать желаемые параметры проекта на каждом шаге. 
   
 2. Устанавливаем eslint. 

  `npx eslint --init` - команда для установки.   
  

> ✔ How would you like to use ESLint? · style.   
> ✔ What type of modules does your project use? · commonjs.   
> ✔ Which framework does your project use? · none.  
> ✔ Does your project use TypeScript? · No / Yes.  
> ✔ Where does your code run? · browser, node.  
> ✔ How would you like to define a style for your project? · guide.  
> ✔ Which style guide do you want to follow? · airbnb.  
> ✔ What format do you want your config file to be in? · JavaScript.  

3. Создаем файл .gitignore. 

`npx create-gitignore node` - команда для создания


4. Создаем app.js. 

`touch app.js` - команда для создания файлов 

5. Прописываем в `package.json` стартовый скрипт. 
```
"start": "node app.js" 
```


## Start any project on Express

1. Установка Nodemon (Программа, которая автоматически перезагружает сервер после каких-то изменений). 

`npm i -D nodemon` - командра для установки (-D устанавливаем только для разработки, а не продакшена)

2. Прописываем `package.json` скрипт для запуска Nodemon. 
```
"dev": "nodemon app.js" 
```
3. Устанавливаем модули Express, Sequelize, HBS, Morgan, Postgres 

`npm i express sequelize hbs morgan pg pg-hsrore` - команда для установки (лишнее убираем). 

`npm i -D sequelize-cli` - команда для Sequelize-CLI. 

4. Поднимаем сервер. 
```Javascript
//В начале
const express = require('express');
const app = express();

//В конце
const PORT = 3000;
app.listen(PORT, () => {
console.log(`Server start on port ${PORT}`);
});
```

5. Запускаем сервер. 

`npm run dev` - запук сервера через скрипт

## Создание базы данных

1. Cоздаём файл `.sequelizerc`:

```Javascript
 const path = require('path');
 module.exports = {
 'config': path.resolve('config', 'config.json'),
 'models-path': path.resolve('db', 'models'),
 'seeders-path': path.resolve('db', 'seeders'),
 'migrations-path': path.resolve('db', 'migrations')
 };
```

2. Cоздаём структуру для работы с sequelize 
 
  `npx sequelize-cli init` 

3.  Создаем базу данных через Postgres 

#### Основные консольные команды для Postgres. 

`\l` - посмотреть все бд, которые есть.

`CREATE USER Beb WITH PASSWORD '123'` - создание пользователя.

`CREATE DATABASE "Films" OWNER beb` - создание БД !пользователь должен быть в lowerCase! 

`\c Films beb` - подключение к Базе Данных.

`\d` - показать все таблицы в БД. 

4. Создаем подключение к базе данных. 

4.1. В файле `config.json` изменить данные для БД (username, password, database, dialect) на свои. 

4.2. Для того, чтобы sequelize следил за сидерами (не накатывались те сидеры, которые уже были добавлены в БД, аналогично миграциям),в файл `config.json` добавили строчки

```
    "seederStorage": "sequelize",
    "seederStorageTableName": "SequelizeData"
```




