
# Interview questions

## 1 [tech]
https://leetcode.com/problems/promise-time-limit/description/


Написать функцию timeLimited, декорирующую основную асинхронную функцию.

Полученная функция должна возвращать ошибку Time Exceeded если переданная
функция испольнилась дольше заданного времени, в противном случае возвращаем
результат переданной функнции.

Параметры функции timeLimited - асинхронная функция, число

``` javascript
function timeLimited(asyncFunction, timeLimit) {

}
```




## 2. [tech]
Найти имена белок в древовидной структуре

Дана древовидная структура, представляющая собой множество гнезд (узлов), где
каждое гнездо может содержать информацию о его типе и имени.
Вам необходимо написать функцию, которая будет возвращать имена всех белок
из этой структуры в массиве.

Каждый узел может иметь следующие свойства:
- `nest` (объект): содержит свойства `name` (строка) и `type` (строка).
- `branches`: массив дочерних узлов, который может содержать такие же узлы.

``` javascript
const tree = {
    nest: { name: "Имя белки1", type: "белка" },
    branches: [
        {
            nest: { name: "Имя белки2", type: "белка" },
            branches: [
                {
                    nest: { name: "Имя белки3", type: "белка" }
                },
                {
                    nest: { name: "Ворон2", type: "ворон" }
                }
            ]
        },
        {
            nest: { name: "Ворон1", type: "ворон" }
        }
    ]
};

function getSquirrelNames(tree) {

}

getSquirrelNames(tree); // ["Имя белки1", "Имя белки2", "Имя белки3"]

```







## 3. [tech]
https://leetcode.com/problems/group-by/description/

Реализовать полифил groupBy

``` javascript
function groupBy(items, callbackFn) {

}

groupBy([[6.1], [4.2], [6.3]], Math.floor); // { 6: [6.1, 6.3], 4: [4.2] }

const inventory = [
  { name: "asparagus", type: "vegetables", quantity: 5 },
  { name: "bananas", type: "fruit", quantity: 0 },
  { name: "goat", type: "meat", quantity: 23 },
  { name: "cherries", type: "fruit", quantity: 5 },
  { name: "fish", type: "meat", quantity: 22 },
];
groupBy(inventory, ({ type }) => type);

/* Result is:
{
  vegetables: [
    { name: 'asparagus', type: 'vegetables', quantity: 5 },
  ],
  fruit: [
    { name: "bananas", type: "fruit", quantity: 0 },
    { name: "cherries", type: "fruit", quantity: 5 }
  ],
  meat: [
    { name: "goat", type: "meat", quantity: 23 },
    { name: "fish", type: "meat", quantity: 22 }
  ]
}
*/

```

## 4. [AA] 
https://leetcode.com/problems/string-compression/description/

Дана строка "AAAAABBBBBZZZOOOOPPP". Нужно ее преобразовать к виду "A5B5Z3O4P3"

## 5. [AA]
(Premium)-> https://leetcode.com/problems/promise-pool/description/

https://leetcode.ca/2023-06-12-2636-Promise-Pool/

Условие задачи
Дан массив асинхронных функций functions и максимальный размер пула n. Необходимо написать асинхронную функцию promisePool. Она должна возвращать Promise, который завершится, когда завершатся все функции из массива functions.

Размер пула определяет максимальное число Promise, которые могут одновременно выполняться. Функция promisePool должна начать выполнение максимально возможного количества функций из массива functions и брать новые функции на выполнение, когда какие-то из выполняющихся Promise завершаются. Функции необходимо выполнять в порядке их следования в массиве functions. Когда последний Promise перейдет в состояние resolved, promisePool также должен перейти в состояние resolved.

Например, если n = 1, promisePool должен выполнять по одной функции последовательно. Однако если n = 2, то сначала должны выполниться две первые функции. Когда любая из этих двух функций завершится, должна начать выполняться третья функция (если она есть в массиве) и так далее, пока не останется больше функций для выполнения.

По условию задачи, все функции из массива всегда успешно переходят в состояние resolved. Функция promisePool должна вернуть Promise, который завершается любым значением.

``` javascript
/*
Входные данные:
functions = [
  () => new Promise(res => setTimeout(res, 300)),
  () => new Promise(res => setTimeout(res, 400)),
  () => new Promise(res => setTimeout(res, 200))
]
n = 2
Результат: [[300,400,500],500]
Объяснение:
Во входном массиве 3 функции. В них вызывается setTimeout на 300мс, 400мс, и 200mмс соответственно.
Они переходят в resolved в 300мс, 400мс, и 500мс соответственно. Результирующий promise завершается в 500мс.
В t=0, первые 2 функции начинают выполнение. Размер пула 2.
В t=300, 1-я функция завершает выполнение, а 3-я функция начинает. Размер пула 2.
В t=400, 2-я функция завершает выполнение. Больше функций в массиве functions не осталось. Размер пула 1.
В t=500, 3-я функция завершает выполнение. Размер пула 0, и результирующий promise также завершается.
*/
```

## 6. [tech]

Нужно чтобы при вызове функций, в консолье ответы выводились в том порядке в которым были вызваны функции, функций foo, bar, baz трогать нельзя.

``` javascript
function foo(cb) {
   setTimeout(() => {
      cb('A')
   }, Math.random() * 100);
}

function bar(cb) {
   setTimeout(() => {
      cb('B')
   }, Math.random() * 100);
}

function baz(cb) {
   setTimeout(() => {
      cb('C')
   }, Math.random() * 100);
}

const callback = (res) => {
   console.log(res)
}

foo(callback); // A
bar(callback); // B
baz(callback); // C

```

## 7. [AA]

Дана строка с диапазонами чисел. Вам необходимо создать функцию, которая объединит все числа из заданных диапазонов, а затем вернет отсортированный массив без дубликатов.

``` javascript

const ranges = ['1-3', '7-9', '11-12', '15'];

function mergeAndSort(ranges) {

}

mergeAndSort(['7-9', '15', '11-12', '1-3']); // [1, 2, 3, 7, 8, 9, 11, 12, 15]
mergeAndSort(['1-5']); // [1, 2, 3, 4, 5]
```

## 8. [AA]

Дан массив объектов, каждый из которых представляет собой маршрут с начальной и конечной точки. Ваша задача — отсортировать маршруты так, чтобы они следовали непрерывной последовательности, начиная с самой начальной точки, и заканчивая конечной точкой маршрута.

``` javascript
function sortPaths(paths) {

}

sortPaths([
    { from: "A", to: "C" },
    { from: "B", to: "K" },
    { from: "C", to: "B" }
]);
/* result: (A-K) [
   { from: "A", to: "C" },
   { from: "C", to: "B" },
   { from: "B", to: "K" }
]*/

sortPaths([
    { from: "M", to: "N" },
    { from: "N", to: "O" },
    { from: "A", to: "M" }
]);
/* result: [
    { from: "A", to: "M" },
    { from: "M", to: "N" },
    { from: "N", to: "O" }
]*/
```

##  9. [AA]
Дан массив ссылок: ['url1', 'url2', ...] и лимит одновременных запросов (limit)
Необходимо реализовать функцию, которыя опросит урлы в том порядку, в котором они
идут в массиве, и вызовет callback с массивом ответов ['url1_answer', 'url2_anser', ...] так, чтобы в любой момент времени выполнялось не более limit 
запросов (как только любой из них завершился, сразу же отправится следующий)
Т.е. нужно реализовать шину с шириной равной limit.

Требования:
- Порядок в массиве ответов должен совпадать с порядком в массиве ссылк

Для опроса можно использовать fetch
Ошибки обрабатывать не нужно

### Пример

Предположим, у нас есть следующий массив URL-адресов:

```javascript
const urls = ['url1', 'url2', 'url3', 'url4'];
const limit = 2;
```

### Что происходит:

- Начинаем с выполнения первых двух запросов: `url1` и `url2`.
- Когда `url1` завершает выполнение, мы запускаем `url3`, и теперь у нас выполняются `url2` и `url3`.
- Когда `url2` завершает выполнение, запускаем `url4`.
- Когда все запросы завершены, мы передаем массив ответов в callback.

### Обработка ошибок:

В задаче упоминается, что ошибки обрабатывать не нужно. Это значит, что наш код просто должен продолжать выполнение, даже если какой-то из запросов завершится с ошибкой. Мы будем просто игнорировать эти случаи.

На выходе у нас будет массив ответов в том же порядке, что и массив входных URL-адресов.

``` javascript
//declare function fetch(url: string): Promise<string>;

function parallelLimit(urls, limit, callback) {

}
```

### 10. [AA]


Дан массив ссылок: ['url1', 'url2', ...] и лимит одновременных запросов (limit)
Необходимо реализовать функцию, которая опросит урлы в том порядке, в котором
они идут в массиве, и вызовет callback с массивом ответов
['url1_answer', 'url2_answer', ...] так, чтобы в любой момент времени
выполнялось не более limit запросов (как только любой из них завершился, сразу же
отправлялся следующий).
То есть нужно реализовать шину с шириной равной limit.

Требования:
- Порядок в массиве ответов должен совпадать с порядком в массиве ссылок
- Для опроса можно использовать fetch
- Ошибки обрабатывать не нужно
- declare function fetch (url: string): Promise<string>;

```javascript
function parallelLimit(urls, limit, callback) {
    
}

const urls = [
    "https://jsonplaceholder.typicode.com/todos/1",
    "https://jsonplaceholder.typicode.com/todos/2",
    "https://jsonplaceholder.typicode.com/todos/3",
    "https://jsonplaceholder.typicode.com/todos/4",
    "https://jsonplaceholder.typicode.com/todos/5",
    "https://jsonplaceholder.typicode.com/todos/6",
    "https://jsonplaceholder.typicode.com/todos/7",
];
const limit = 2;

parallelLimit(urls, limit, (results) => {
    console.log(results);
});
```
