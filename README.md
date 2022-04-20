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










