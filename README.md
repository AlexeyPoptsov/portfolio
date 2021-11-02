# Проекты

### 1. [Проект прогнозирования оттока клиентов в телеком.](https://github.com/AlexeyPoptsov/portfolio/tree/main/01_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%BE%D1%82%D1%82%D0%BE%D0%BA%D0%B0%20%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%BE%D0%B2)


Суть задачи, по известным характеристикам пользователя и набору используемых услуг классифицировать клиентов склонных 
к уходу. Решена типовая задача классификации с полным циклом работы с данными. Объединение
нормализация исходных данных, достаточно объемный этап фиче инжиниринга в том числе с
предварительной кластеризацией пользователей и задачей балансировки классов, подбор 
оптимальной для данной задачи модели. 

В данном проекте использовались две модели логистическая
регрессия из sklearn и бустинг над деревьями от catboost. Этап тюнинга параметров моделей для
достижения необходимого уровня метрики roc_auc.

### 2. [Проект прогнозирования спроса такси.](https://github.com/AlexeyPoptsov/portfolio/tree/main/02_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%81%D0%BF%D1%80%D0%BE%D1%81%D0%B0%20%D1%82%D0%B0%D0%BA%D1%81%D0%B8)
Задача по анализу временных рядов которая требовала
весьма объемной предподготовки данных с этапом генерации достаточно большого числа фич. Как и
во многих проектах для решения использовались несколько разноплановых моделей, в этом проекте это
регрессия из sklearn и бустинг из lightgbm.

### 3. [Проект классификации тональности комментариев в соцсети.](https://github.com/AlexeyPoptsov/portfolio/tree/main/03_%D0%9A%D0%BB%D0%B0%D1%81%D1%81%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D1%82%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BA%D0%BE%D0%BC%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%B8%D0%B5%D0%B2)
Решалась типовая задача классификации, использовалась модель логистической регрессии из sklearn, а также бустинг над
деревьями из lightgbm. Задача требовала полного цикла отработки сырых текстов: матчинга,
лемматизации, векторизации TF-IDF.
