
# Interview questions

## 1
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




## 2.
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

getSquirrelNames(); // ["Имя белки1", "Имя белки2", "Имя белки3"]

```







## 3.
https://leetcode.com/problems/group-by/description/

Реализовать полифил groupBy

``` javascript
function groupBy(items, callbackFn) {

}

groupBy([6.1], [4.2], [6.3], Math.floor); // { 6: [6.1, 6.3], 4: [4.2] }
groupBy(["one", "two", "three"], "length"); // { 3: ['one', 'two'], 5: ['three'] }

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

```
