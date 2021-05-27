# Калькулятор на Vue.js
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)

:ru: by [Timeweb.com](https://timeweb.com/ru/)

Приложение написано для [Нетологии](https://netology.ru/)
в рамках открытого урока по [Vue.js](https://vuejs.org/)
и представляет собой простейший калькулятор, демонстрируя концепцию
[SPA](https://ru.wikipedia.org/wiki/%D0%9E%D0%B4%D0%BD%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%BD%D0%BE%D0%B5_%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5).

:tada: [Демо](https://calc-netology-demo-app.hostman.site/)

:wrench: [Локальный запуск проекта](#dev)

## <a name="dev"></a>Локальный запуск проекта

1. **Загрузка проекта на локальную машину**

    ```
    git clone https://github.com/TimewebAccount/calc-netology-demo.git
    ```

2. **Установка зависимостей**

    ```
    npm ci
    ```

   Использование `npm ci` вместо `npm i` позволит гарантировать корректные версии устанавливаемых `npm` пакетов,
   так как они будут взяты из `package-lock.json`.

3. **Запуск сервера для разработки**

   В качестве сервера для разработки используется
   [Webpack Dev Server](https://github.com/webpack/webpack-dev-server).

   Для его запуска выполните из корневой директории проекта:

    ```
    npm run serve
   ```

   После этого приложение будет доступно по адресу `localhost:8080`.

   Во время разработки изменения в файлах будут отслеживаться автоматически,
   при этом будет вызываться линтер и сервер будет перезапускаться.

   Также доступны следующие команды:

    ```
    npm run build // сборка приложения Vue для развёртывания на production
    npm run lint // ручной запуск линтера
    ```