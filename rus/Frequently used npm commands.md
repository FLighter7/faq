## Часто используемые команды npm

| Команда | Описание
| --- | ---
| `npm init` | Создаёт файл `package.json`. Используйте `npm init -y` для создания этого файла без ответов на вопросы
| `npm install` <br>`npm install <package-name> ...` <br>`npm i` <br>`npm i <package-name> ...` | Устанавливает все зависимости или необходимый(е) пакет(ы) <br><br>Флаги: <br>`-g` - установка пакета в глобальную область (пакет будет доступен между всеми проектами) <br>`-D` - установка пакета в `devDependencies` <br>`-d` или `-P` - установка пакета в `dependencies` <br>`-O` - установка пакета в `optionalDependencies`
| `npm ci` | Установка пакетов в "чистом" режиме
| `npm uninstall <package-name> ...` <br>`npm r <package-name> ...` | Удаляет установленный(е) пакет(ы) <br><br>`-g` - флаг для удаления пакета из глобальной области
| `npm update` | Обновляет все пакеты до последних версий
| `npm start` | Запускает команду `start` из `scripts`
| `npm stop` | Запускает команду `stop` из `scripts`
| `npm test` | Запускает команду `test` из `scripts`
| `npm run` | Отображает все команды из `scripts`
| `npm run <command>` | Запускает любую команду из `scripts`
| `npx <package> <command>` | Запускает команду для локального или удалённого пакета
| `npm repo` | Открывает в браузере репозиторий пакета
| `npm docs` | Открывает в браузере документацию по пакету
| `npm publish` | Публикует пакет в `npm`. Используйте `npx npm-packlist`, чтобы увидеть, что именно будет включено в пакет. Используйте `npm publish --access public` для публикации scoped package (@user/package-name).
| `npm version <new-version>` | Задаёт новую версию текущему пакету
| `npm ls` | Отображает все установленные пакеты. Используйте `-g` для просмотра глобальных пакетов

### Разница между `npm i` and `npm ci`
- `npm i` - устанавливает все зависимости, может изменять `package.json` или `package-lock.json`, может не установить точную версию, которая была указана;
- `npm ci` - устанавливает все зависимости с указанными версиями, удаляет `node_modules` для обеспечения чистой установки, никогда не изменяет `package.json` или `package-lock.json`.

### Ссылки

- [List of all commands](https://docs.npmjs.com/cli/v7/commands)
- [npm ci vs. npm install - Which Should You Use in Your Node.js Projects?](https://betterprogramming.pub/npm-ci-vs-npm-install-which-should-you-use-in-your-node-js-projects-51e07cb71e26)
- [What is the difference between “npm install” and “npm ci”?](https://stackoverflow.com/questions/52499617/what-is-the-difference-between-npm-install-and-npm-ci)
