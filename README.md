# **Лента проектов**

## 1. Проекты прогнозирования спроса розничной сети
### 1.1. Система прогзнозирования продаж мягкой мебели в следующем месяце. 
Розничная сеть 40 торговых центров, около 100 точек продаж. 200+ моделей мебели в 300+ возможных облицовочных материалах.
В проекте реализован полный цикл работы с данными:
* Получение первичных данных из учетных систем (1С, MS SQL, Excel, внешние источники);
* Предобработка данных, пропускм, реклассификация, объединение данных;
* Блок фиче-инжиниринга. Кластеризация, уникальность, усреднение, выделение волатильности цен. Итоговый датасет около 100 фич;
* Блок корреляции и селекции фич;
* Отбор моделей. В текущей версии оставлены 2 бустинга (lightgbm, catboost), lasso регрессия и 2х слойная нейросеть;
* Оптимизация гиперпараметров каждой модели с помощью bayesian-optimization;
* Разделение данных на блоки для самостоятельных прогнозов;
* Обобщение прогнозов, формирование итогового ансамбля;
* Есть реадакция проекта с организацией stacking, где финальный прогноз делает бустинг lightgbm;
* Блок анализа распределения метрики по структуре данных;
* Формирование итоговых выгрузок для дальнейшей работы в учетных системах.
<br>

## 2. Проекты Kaggle 
### [2.1. Predict Future Sales. TOP 5%](https://www.kaggle.com/competitions/competitive-data-science-predict-future-sales/overview)  
In this competition you will work with a challenging time-series dataset consisting of daily sales data, kindly provided by one of the largest Russian software firms - 1C Company. 

We are asking you to predict total sales for every product and store in the next month.
<br>

## 3. Проекты MADE
### 3.1. Задача классификации пациентов по результатам анализов. (3 место / 2000+)
### 3.2. Задача подсчета числа квадратов по базе картинок с произвольными фигурами  
<br>

## 4. Проекты KARPOV.COURSES
### 4.1. Система дашбордов на базе Apache Superset
### 4.2. [Система поиска анамалий и информирования через Telegramm Bot](https://ibb.co/9NXbWRS)
### 4.3. ETL система на базе Apache Airflow  
<br>

## 5. Проекты Яндекс.Практикум
### 5.1. [Проект прогнозирования оттока клиентов в телеком.](https://github.com/AlexeyPoptsov/portfolio/tree/main/01_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%BE%D1%82%D1%82%D0%BE%D0%BA%D0%B0%20%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%BE%D0%B2)
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

### 5.2. [Проект прогнозирования спроса такси.](https://github.com/AlexeyPoptsov/portfolio/tree/main/02_%D0%9F%D1%80%D0%BE%D0%B3%D0%BD%D0%BE%D0%B7%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%81%D0%BF%D1%80%D0%BE%D1%81%D0%B0%20%D1%82%D0%B0%D0%BA%D1%81%D0%B8)
***Суть задачи: по известным историческим данным о заказах такси спрогнозировать количество заказов на следующий час.*** 
Решена типовая задача по анализу временных рядов с оценкой стационарности исходных данных. Выполнен этап предобработки данных с последующим этапом генерации дополнительных фич, 
для работы деревьев применялся отдельный этап приведения ряда к стационарности путем логарифмирования и использования первых разностей.

Для решения использовались несколько разноплановых моделей, линейная регрессия с регулиризацией ***RidgeCV*** из **_sklearn_** и бустинг над деревьями
_**LGBMRegressor**_ из **_lightgbm_**. 

Для оценки качества работы модели использована метрика **_RMSE._**  

### 5.3. [Расчет прибыльности месторождений.](https://github.com/AlexeyPoptsov/portfolio/tree/main/03_%D0%A0%D0%B0%D1%81%D1%87%D0%B5%D1%82%20%D0%BF%D1%80%D0%B8%D0%B1%D1%8B%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BC%D0%B5%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9)
В нескольких регионах в каждом из 10 000 месторождений проведены измерения качества и запасов нефти.
На основании исходных данных разработана модель машинного обучения, которая определяет регион, где добыча принесёт наибольшую прибыль.
Расчитана возможная прибыль и оценены риски техникой **_Bootstrap_**.

### 5.4. [Проект классификации тональности комментариев в соцсети.](https://github.com/AlexeyPoptsov/portfolio/tree/main/04_%D0%9A%D0%BB%D0%B0%D1%81%D1%81%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F%20%D1%82%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8%20%D0%BA%D0%BE%D0%BC%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%80%D0%B8%D0%B5%D0%B2)
Решалась типовая задача классификации, использовалась модель логистической регрессии из ***sklearn***, а также бустинг над
деревьями из ***lightgbm***. Задача требовала полного цикла отработки сырых текстов: матчинга,
лемматизации, векторизации ***TF-IDF***.

### 5.5. [Проект определения возраста по фото](https://github.com/AlexeyPoptsov/portfolio/tree/main/05_%D0%9E%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F%20%D0%B2%D0%BE%D0%B7%D1%80%D0%B0%D1%81%D1%82%D0%B0%20%D0%BF%D0%BE%20%D1%84%D0%BE%D1%82%D0%BE)
на основе сверточной нейросети **_ResNet50_** библиотеки **_keras_**.
Так работа проводилась на типовом датасете это скорее методический проект, целью которого была
задача погрузится в архитектуру полно связанных и сверточных нейросетей.
