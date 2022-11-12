---
title: Object.getPrototypeOf()
slug: Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf
tags:
  - ECMAScript5
  - JavaScript
  - Method
  - Object
  - Reference
translation_of: Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf
---

{{JSRef("Global_Objects", "Object")}}

## Сводка

Метод **`Object.getPrototypeOf()`** возвращает прототип (то есть, внутреннее свойство `[[Prototype]]`) указанного объекта.

## Синтаксис

```
Object.getPrototypeOf(obj)
```

### Параметры

- `obj`
  - : Объект, чей прототип будет возвращён.

## Примеры

```js
var proto = {};
var obj = Object.create(proto);
Object.getPrototypeOf(obj) === proto; // true
```

```js
> Object.getPrototypeOf('foo')
TypeError: "foo" is not an object  // код ES5
> Object.getPrototypeOf('foo')
String.prototype                   // код ES6
```

## Примечания

В ES5, если параметр `obj` не является объектом, будет выброшено исключение {{jsxref("Global_Objects/TypeError", "TypeError")}}. В ES6, параметр будет приведён к объекту {{jsxref("Global_Objects/Object", "Object")}}.

```js
> Object.getPrototypeOf('foo')
TypeError: "foo" is not an object  // код ES5
> Object.getPrototypeOf('foo')
String.prototype                   // код ES6
```

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

### Примечания по Opera

Хотя старые версии Opera и не поддерживают метод `Object.getPrototypeOf()`, Opera поддерживает нестандартное свойство {{jsxref("Object.proto", "__proto__")}}, начиная с версии Opera 10.50.

## Смотрите также

- {{jsxref("Object.prototype.isPrototypeOf()")}}
- {{jsxref("Object.setPrototypeOf()")}} {{experimental_inline}}
- {{jsxref("Object.prototype.__proto__")}}
- Запись в блоге Джона Резига о [getPrototypeOf()](http://ejohn.org/blog/objectgetprototypeof/)
