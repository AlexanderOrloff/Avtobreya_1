# Домашнее задание 2. Извлечение коллокаций + NER

Выберите корпус отзывов на товары одной из категорий Amazon:
https://nijianmo.github.io/amazon/index.html

Допустим, что вам нужно подготовить аналитический отчет по этим отзывам — например, для производителя нового продукта этой категории. Для этого будем искать упоминания товаров в отзывах (будем считать их NE). Учтите, что упоминание может выглядеть не только как "Iphone 10", но и как "модель", "телефон" и т.п.

1. (3 балла) Предложите 3 способа найти упоминания товаров в отзывах. 
Например: составить шаблоны вида "холодильник XXX", найти все соответствующие n-граммы и выделить из них называние товара.
Могут помочь заголовки и дополнительные данные с Amazon (Metadata [здесь](https://nijianmo.github.io/amazon/index.html))
Какие данные необходимы для каждого из способов? Какие есть достоинства/недостатки?

2. (2 балла) Реализуйте один из предложенных вами способов.

Примеры в качестве подсказки (можно использовать один из них): 
- написать правила с помощью [natasha/yargy](https://github.com/natasha/yargy)
- составить мини-словарь сущностей/дескрипторов, расширить с помощью эмбеддингов (например, word2vec)

3. (1 балл) Соберите n-граммы с полученными сущностями (NE + левый сосед / NE + правый сосед)

4. (3 балла) Ранжируйте n-граммы с помощью 3 коллокационных метрик (t-score, PMI и т.д.). Не забудьте про частотный фильтр / сглаживание.
Выберите лучший результат (какая метрика  ранжирует выше коллокации, подходящие для отчёта).

5. (1 балл) Сгруппируйте полученные коллокации по NE, выведите примеры для 5 товаров.
Должны получиться примерно такие группы:
```
watch 
--- 
stylish watch
good watches
great watch
love this watch
...
```

**Бонус**: если придумаете способ объединить синонимичные упоминания (например, "Samsung Galaxy Watch", "watch", "smartwatch")