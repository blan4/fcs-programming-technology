---
layout: page
title:  "Функциональные коллекции"
date:   2018-03-27 21:07:26 +0600
navigation: 44
---

# Функциональные коллекции

Реализация функциональных коллекций, как в java-stream, scala-collections. Например: `collection.map(modifier).filter(...).reduce(...)`.

Чтобы было [lazy](https://en.wikipedia.org/wiki/Lazy_evaluation) и оптимально: два последовательных фильтра схлапываются в один.

Проходные:  `map`, `filter`, `flatMap`, `zip`, `take`. Терминальные: `reduce`, `fold`, `forEach`.

TBDL

## Литература

1. [MIT 6.005 - Map Filter Reduce](http://web.mit.edu/6.005/www/fa15/classes/25-map-filter-reduce/) это конспект лекций из курса Массачусетского университета на тему функциоанльных комбинаторов.
2. [Cornell University CS31100 - Map and Fold](http://www.cs.cornell.edu/courses/cs3110/2014fa/lectures/6/lec06.html) это конспект лекции из курса университета Корнелл про map, filter, fold на языке hascell.
3. [Wiki: Ленивые вычисления](https://ru.wikipedia.org/wiki/Ленивые_вычисления)
4. [Java streams API](https://docs.oracle.com/javase/8/docs/api/java/util/stream/package-summary.html) - документация API ленивых коллекций в java. Есть объяснение типов операций - intermediate и terminal.
5. [Scala collections API](https://www.scala-lang.org/docu/files/collections-api/collections.html) - документация про устройство старых коллекций в scala. Они не lazy, но видов операций там очень много.

## Как должно работать

TBDL

```python
from func_collections import Seq

s = Seq(1,2,3,4) \
    .filter(lambda x: x % 2 == 0) \
    .map(lambda x: x ** 2) \
    .reduce(lambda acc, cur: acc+cur)

assert(s == 2**2 + 4**2)
```

## Базовый набор функций

### [Map](https://en.wikipedia.org/wiki/Map_%28higher-order_function%29)

Функция трансофрмации, применяемая над каждым элементом последовательнсти.

### [Filter](https://en.wikipedia.org/wiki/Filter_%28higher-order_function%29)

Функция фильтрации, то есть отсеивает элементы, если они не удовлетворяют условию предиката.

### [Fold](https://en.wikipedia.org/wiki/Fold_%28higher-order_function%29)

Функция свёртки последовательности в некоторое одно значение.

### [Foreach](https://en.wikipedia.org/wiki/Foreach_loop)

Функция обхода всего списка.

### ToList

Фактически это fold с подготовленной функцией свертки в лист.

## Дополнительные функции

### FlatMap

```python
Seq(1,2,3,4).flat_map(lambda x: [x,x*2]).to_list == [1,2, 3,6, 4,8]
```

### Take

Взять первые n элементов последовательности.

### Drop

Пропустить первые n элементов последовательности.

### TakeWhile

Брать элементы из последовательности до тех пор пока выполняется условие.

### DropWhile

Пропускать элементы до тех пор пока выполняется условие.

### Zip

```python
s1 = Seq(1,2,3,4)
s2 = Seq(10,20,30,40)
s1.zip(s2).to_list == [(1,10), (2,20), (3,30), (4,40)]
```

### Sliding

Скользящее окно размером n.

### Find

Найти первый удовлетворяющий условию элемент списка.

### Flatten

### IsAny

Удовлетворяет ли хоть один элемент списка условию.

### IsSome

### GroupBy

Основная идея группировки - это предоставить возможность для последующей агрегации результатов. Агрегации могут быть следующими:
- подсчет количества элементов в группе `count`
- суммирование всех элементов - `sum`
- превращение в словарь, где ключи это списки - `collect`
- считать статистики `mean`, `std`, `median` и так далее
- и.т.д.

```python
Seq(1,1,2,3,3,4,3,4).group_by(lambda x: x).agg(count).to_dict == {1: 2, 2: 1, 3: 3, 4: 2}
```
