## Что такое и в чём разница между IIFE, CJS, AMD, UMD, ESM, SystemJS?

#### Что это?

Это разные форматы модульных систем. Они показывают, как объединять или подключать js-файлы с помощью обёрток или операторов.

#### Короткое описание

- **IIFE** - *Immediately Invoked Function Expression* (немедленно вызываемое функциональное выражение) - Все зависимости включены в именованную (или не именованную) самовызывающуюся функцию, которая возвращает объект (наш модуль). Пример:
```js
// Имя модуля в глобальной области видимости
const ourModuleName = (() => {
  // Любой код
  return {
    getFoo: () => 'foo',
  }
})();
```

- **CJS** - *CommonJS*, *ServerJS* (old) - Формат модулей, который чаще используется в Node.js и экосистемах вне браузера. Ключевые сущности: `module.exports` или `exports` - для экспорта модуля, `require` - для импорта модуля. <br>- Поскольку `require` - это просто функция, мы можем использовать динамические импорты. <br>- В чистом виде CJS модуля не могут быть использованы в браузере и нуждаются в транспиляции. Пример:
```js
// Импорт каких-то модулей
const someModule1 = require('module-name-1');
const someModule2 = require('./path-to-module.js');

// Что-то делаем
const foo = someModule1.getSomething();
const bar = () => someModule2.doSomething();

// Экспорт модуля
exports.foo = foo;
exports.bar = bar;
// Или (эквивалентно)
module.exports = {
  foo,
  bar,
}
```

- **AMD** - *Asynchronous Module Definition* - Формат модулей, используемый библиотекой RequireJS и подходящий для браузера (в отличие от CJS). Главная идея в том, что RequireJS - это реализация AMD формата, но в то же время код очень похож на CJS. Ключевые сущности: `define` - для определения модуля, `require` - для использования модуля. Пример:
```js
// Создание какого-то модуля
define('someModuleName', () => {
  // Любой код
  return {
    getFoo: () => 'foo',
  }
});

// Использование созданного модуля
require(['someModuleName'], someModuleName => {
  someModuleName.getFoo();
});
```

- **UMD** - *UmdJS*, *Universal Module Definition* - UMD создан для работы везде - на сервере и в браузере. Он поддерживает форматы AMD, CJS, IIFE и часто используется как результат работы сборщика.
```js
// Определить текущую модульную систему
(function(global, factory) {
  typeof exports === 'object' && typeof module !== 'undefined'
    ? module.exports = factory()
    : typeof define === 'function' && define.amd
      ? define(factory)
      : (global = typeof globalThis !== 'undefined' ? globalThis : global || self, global.A1 = factory());
}(this, (function() {
  // Код модуля тут
  return {
    getFoo: () => 'foo',
  }
})));
```

- **ESM** - *ES Modules*, *ES2015 Modules*, *ES6 Modules*, etc. - С 2015 года это нативный формат модульной системы для js. Ключевые сущности: `import` - для импорта модуля, `export` - для экспорта модуля. Работает в современных браузерах, хорошо подвержен tree-shaking (в отличие от остальных форматов), асинхронный. Пример:
```js
// Импорт каких-то модулей
import someModule1 from 'module-name-1';
import someModule2 from './path-to-module.js';

// Что-то делаем
const foo = someModule1.getSomething();
const bar = () => someModule2.doSomething();

// Экспорт модуля
export default {
  foo,
  bar,
}
```

- **SystemJS** - *System Module* - SystemJS является универсальным загрузчиком модулей, который поддерживает CJS, AMD, ESM модули для их запуска на старых браузерах. Ключевая сущность - `System.register` - регистрирует модуль. Для запуска такого модуля необходима установка пакета SystemJS. Пример:
```js
System.register([], function(exports) {
  return {
    execute: function () {
      // Код модуля тут
      exports('getFoo', getFoo);
      const getFoo = () => 'foo';
    }
  };
});
```

### Ссылки

- [Понимание модульных форматов и инструментов JavaScript](https://habr.com/ru/post/501198/)
- [What are CJS, AMD, UMD, ESM, System, and IIFE?](https://betterprogramming.pub/what-are-cjs-amd-umd-esm-system-and-iife-3633a112db62)
- [What are CJS, AMD, UMD, and ESM in Javascript?](https://irian.to/blogs/what-are-cjs-amd-umd-and-esm-in-javascript/)
- [Relation between CommonJS, AMD and RequireJS?](https://stackoverflow.com/questions/16521471/relation-between-commonjs-amd-and-requirejs)
