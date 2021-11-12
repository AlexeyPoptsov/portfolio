# Проекты 

### 1. [Проект прогнозирования оттока клиентов в телеком.](https://github.com/AlexeyPoptsov/portfolio/tree/main/01_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%BE%D1%82%D1%82%D0%BE%D0%BA%D0%B0%20%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%BE%D0%B2)


***Суть задачи: по известным характеристикам пользователя и набору используемых услуг классифицировать клиентов склонных 
к уходу.*** Решена типовая задача классификации с полным циклом работы с данными. Объединение
нормализация исходных данных, этап фиче инжиниринга в том числе с
предварительной кластеризацией пользователей и задачей балансировки классов, подбор 
оптимальной для данной задачи модели. 

В данном проекте использовались две модели ***LogisticRegression***
из ***sklearn*** и ***CatBoostClassifier*** из ***catboost***. Блок тюнинга параметров моделей выполнен в два этапа. 
Грубый этап поиска параметров с использованием ***RandomizedSearchCV***, далее более точный поиск возле 
полученных центров с использованием ***GridSearchCV***

В проекте оптимизировалась метрика ***roc_auc***, наилучшее полученное значение на тестовых данных 0.84.

### 2. [Проект прогнозирования спроса такси.](https://github.com/AlexeyPoptsov/portfolio/tree/main/02_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%81%D0%BF%D1%80%D0%BE%D1%81%D0%B0%20%D1%82%D0%B0%D0%BA%D1%81%D0%B8)
***Суть задачи: по известным историческим данным о заказах такси спрогнозировать количество заказов на следующий час.*** 
Решена типовая задача по анализу временных рядов с оценкой стационарности исходных данных. Выполнен этап предобработки данных с последующим этапом генерации дополнительных фич, 
для работы деревьев применялся отдельный этап приведения ряда к стационарности путем логарифмирования и использования первых разностей.

Для решения использовались несколько разноплановых моделей, линейная регрессия с регулиризацией ***RidgeCV*** из **_sklearn_** и бустинг над деревьями
_**LGBMRegressor**_ из **_lightgbm_**. 

Для оценки качества работы модели использована метрика **_RMSE._**  

### 3. [Расчет прибыльности месторождений.](https://github.com/AlexeyPoptsov/portfolio/tree/main/03_%D0%A0%D0%B0%D1%81%D1%87%D0%B5%D1%82%20%D0%BF%D1%80%D0%B8%D0%B1%D1%8B%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9)
В нескольких регионах в каждом из 10 000 месторождений проведены измерения качества и запасов нефти.
На основании исходных данных разработана модель машинного обучения, которая определяет регион, где добыча принесёт наибольшую прибыль.
Расчитана возможная прибыль и оценены риски техникой **_Bootstrap_**.

### 4. [Проект классификации тональности комментариев в соцсети.](https://github.com/AlexeyPoptsov/portfolio/tree/main/04_%D0%9A%D0%BB%D0%B0%D1%81%D1%81%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D1%82%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BA%D0%BE%D0%BC%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%B8%D0%B5%D0%B2)
Решалась типовая задача классификации, использовалась модель логистической регрессии из ***sklearn***, а также бустинг над
деревьями из ***lightgbm***. Задача требовала полного цикла отработки сырых текстов: матчинга,
лемматизации, векторизации ***TF-IDF***.

### 5. [Проект определения возраста по фото](https://github.com/AlexeyPoptsov/portfolio/tree/main/05_%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D0%B2%D0%BE%D0%B7%D1%80%D0%B0%D1%81%D1%82%D0%B0%20%D0%BF%D0%BE%20%D1%84%D0%BE%D1%82%D0%BE)
на основе сверточной нейросети **_ResNet50_** библиотеки **_keras_**.
Так работа проводилась на типовом датасете это скорее методический проект, целью которого была
задача погрузится в архитектуру полно связанных и сверточных нейросетей.