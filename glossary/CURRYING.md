# Currying

Currying (рус. *каррирование*, *карринг*) — это техника преобразования функции с N аргументами в цепочку из N функций, каждая из которых принимает по одному аргументу.

Это достигается при помощи создания функции с одним аргументом, возвращающей новую функцию, связанную с контекстом внешней через [замыкание](CLOSURE.md).

```js
// К примеру мы имеем функцию add, которая принимает два аргумента:
add(3, 5);

// После каррирования функции add, сигнатура функции будет другая:
curryAdd(3)(5);
```

Данная техника позволяет в частности создавать так называемые [частичные применения](PARTIAL_APPLICATION.md). В частности, для нашей функции:

```js
// Создали частичное применение для функции add

var add3 = curryAdd(3);
var add10 = curryAdd(10);

// И теперь мы можем переиспользовать функцию
add3(5); // => 8
add3(7); // => 10
add3(17); // => 20
add10(5); // => 15
```

Стоит отметить, что каррирование функции можно как описать самому, так и использовать библиотеки, в частности [Lodash](https://lodash.com/docs#curry), [Wu](https://fitzgen.github.io/wu.js/#curryable), [Ramda](http://ramdajs.com/docs/#curry).