---
layout: page
title:  "Hard projects"
date:   2018-03-27 21:07:26 +0600
navigation: 42
---

# Hard projects

Список этих здач будет дополняться, так чтобы больше людей нашли проект по вкусу.

Если вы хотите делать один проект в течение месяца, вместо многих мелких, то вы можете выбрать проект из этого списка, сказать вашему преподавателю и мы подготовим детальное описание проекта, критериев приемки и количество баллов которое оно даст. Типичный расчет баллов - это сумма балов, которую вы могли бы получить решая мелкие задачи в классе и дома плюс бонусная наценка.

Беритесь за эти проекты если вы более менее уверены в себе. Но мы обещаем, это будет очень интересно и полезно.

1. Нечёткий поиск \([https://habrahabr.ru/post/114997/](https://habrahabr.ru/post/114997/)\)
2. Визуализация данных в matplotlib\(можно в jupyter делать\)
   * word count, биграммы, и что-то еще, тематика
   * матзадача???
3. Машинное обучение
	- написать нейросеть \(обычный перцептрон потом трехслойную и решить ею задачу распознавания рукописных цифр MNIST\)
	- Решающие деревья. [Детальное описание](decision_tree)
	- `K` ближайших соседей (kNN)
	- `K` средних (kMeans)
4. реализация in-memmory БД \(b-tree, hash-tree\)
5. стейт машина \(чего?\) _АСИНХРОННАЯ_\(зачем?\) - эмуляция физического процесса
6. Написать свои простые регэкспы
7. Написать интерпретатор FORTH\(стековая машина\)
8. Реализация реактивного вычисления, как в excel ячейки.
9. [Детальное описание.](functional_collections) Реализация функциональных коллекций \(как java-stream, scala-collections\). Например: `collection.map(modifier).filter(...).reduce(...)`. Чтобы было [lazy](https://en.wikipedia.org/wiki/Lazy_evaluation) и оптимально: два последовательных фильтра схлапываются в один. Проходные:  `map`, `filter`, `flatMap`, `zip`, `take`. Терминальные: `reduce`, `fold`, `forEach`.
10. Написать декоратор над функцией для хвостовой рекурсии в питоне - [http://www.datchley.name/recursion-tail-calls-and-trampolines/](http://www.datchley.name/recursion-tail-calls-and-trampolines/) [http://code.activestate.com/recipes/474088-tail-call-optimization-decorator/](http://code.activestate.com/recipes/474088-tail-call-optimization-decorator/)
11. свой маленький блокчейн \(благо есть описание как это сделать\)
12. выводить все последние новости с набора сайтов по rss\(или не только\) с фильтрами по ключевым словам.
13. загрузить граф друзей из вк\(рекурсия!\), сохранить его и визулизировать в matplotlib. \([https://habrahabr.ru/post/243229/](https://habrahabr.ru/post/243229/) [https://habrahabr.ru/company/hh/blog/263313/](https://habrahabr.ru/company/hh/blog/263313/) [https://habrahabr.ru/post/258713/](https://habrahabr.ru/post/258713/) \) - тут даже очереди можно наворотить! Потом париться с тем как всё затолкать в память и быстро нарисовать.
14. Интерпретатор Lisp на питоне. [http://pythonpracticeprojects.com/lisp.html](http://pythonpracticeprojects.com/lisp.html) How to write a lisp interpretator in Python [http://norvig.com/lispy.html](http://norvig.com/lispy.html) Actual example - [https://github.com/fogus/lithp](https://github.com/fogus/lithp)
