2022-08-16 00:01
Tags: #JavaScript #this

Это ссылка на контекст выполнения функции.
Значение `this` определяется тем, **как** функция была вызвана, а не тем, где она была объявлена.

Значение `this` зависит от контекста вызова функции:

1) [Глобальный контекс](#Глобальный%20контекст)
2) [Внутки функций](#Внутки%20функций)
3) [С явным указанием контекста (.call .apply .bind)](#.call%20.apply%20.bind)
---
## Глобальный контекст

В глобальной области видимости (вне функций) `this` ссылается на глобальный объект:

- В браузере — `window`
- В Node.js —  `global` (`module.exports`)

```js
console.log(this); // В браузере: window, в Node.js: global
```


---
## Внутки функций

- **Обычная функция** - в строгом режиме (`strict mode`) `this` =  `undefined`. в обычном режиме `this` = глобальный объект. Значение `this` динамическое. оно завичит от места вызова функции.
- **Метод объекта** - тут `this` будет ссылаться на сам объект.
- **Функция конструктор** - `this` ссылается на новый созданный объект.
- **Стрелочные функции** - **не имеют своего `this`**. Значение `this` берётся из ближайшей внешней функции. Если ближайшей внешней функции нет, то `this` будет глобальным объектом (`window` или `global`)

 В обычной функции, всегда ищем место вызова этой функции, смотрим какой объект слева от точки, значит он и будет `this`.
 Если объекта нету то `this` будет глобальным объектом (`window` или `global`)

Стрелочная функция всегда ищет `this` в ближайших внешних функциия, если таковых нету то `this` будет глобальным объектом (`window` или `global`)

---
## .call .apply .bind

- `call()` — вызывает функцию с указанным `this` и аргументами.
```js
foo.call({name: 'Vladimir'}, 1, 2, 3)
```

- `apply()` — аналогично `call()`, но аргументы передаются как массив.
```js
foo.apply({name: 'Vladimir'}, [1, 2, 3])
```

- `bind()` — создает новую функцию с привязанным `this`.
```js
const bindedF = foo2.bind({name: 'Vladimir'}, 1, 2, 3)  
bindedF()

//можно написать два вызов  
foo2.bind({name: 'Vladimir'}, 1, 2, 3)()
```

---
### Links
[[JavaScript]]
[Полный разбор THIS в JavaScript (YouTube)](https://www.youtube.com/watch?v=aFxQvCqrUC0)