### 3. Проект классификации тональности комментариев
**Описание задачи:**
Интернет-магазин запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.

В проекте реализована задача предобработки и векторизации сырого текста с последующим обучением моделей классификации коментариев на позитивные и негативные. 

Оценка качества проведена на основе метрики  **F1** 

### Содержание проекта
<div class="toc"><ul class="toc-item"><li><span><a href="#Подготовка" data-toc-modified-id="Подготовка-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Подготовка</a></span><ul class="toc-item"><li><span><a href="#Разобьем-коменты-на-твиты-с-фильтрацией-символов." data-toc-modified-id="Разобьем-коменты-на-твиты-с-фильтрацией-символов.-1.1"><span class="toc-item-num">1.1&nbsp;&nbsp;</span>Разобьем коменты на твиты с фильтрацией символов.</a></span></li><li><span><a href="#Удалим-стоп-слова" data-toc-modified-id="Удалим-стоп-слова-1.2"><span class="toc-item-num">1.2&nbsp;&nbsp;</span>Удалим стоп слова</a></span></li><li><span><a href="#Лемматизируем" data-toc-modified-id="Лемматизируем-1.3"><span class="toc-item-num">1.3&nbsp;&nbsp;</span>Лемматизируем</a></span></li><li><span><a href="#Соотношение-классов" data-toc-modified-id="Соотношение-классов-1.4"><span class="toc-item-num">1.4&nbsp;&nbsp;</span>Соотношение классов</a></span></li><li><span><a href="#Разделим-на-трейн-и-тест-выборки" data-toc-modified-id="Разделим-на-трейн-и-тест-выборки-1.5"><span class="toc-item-num">1.5&nbsp;&nbsp;</span>Разделим на трейн и тест выборки</a></span></li><li><span><a href="#Скорректируем-соотношение-классов" data-toc-modified-id="Скорректируем-соотношение-классов-1.6"><span class="toc-item-num">1.6&nbsp;&nbsp;</span>Скорректируем соотношение классов</a></span></li><li><span><a href="#Векторизуем-методом-TF--IDF" data-toc-modified-id="Векторизуем-методом-TF--IDF-1.7"><span class="toc-item-num">1.7&nbsp;&nbsp;</span>Векторизуем методом TF- IDF</a></span></li></ul></li><li><span><a href="#Обучение" data-toc-modified-id="Обучение-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Обучение</a></span><ul class="toc-item"><li><span><a href="#Модель-LogisticRegression" data-toc-modified-id="Модель-LogisticRegression-2.1"><span class="toc-item-num">2.1&nbsp;&nbsp;</span>Модель LogisticRegression</a></span><ul class="toc-item"><li><span><a href="#Подготовим-и-обучим-модель" data-toc-modified-id="Подготовим-и-обучим-модель-2.1.1"><span class="toc-item-num">2.1.1&nbsp;&nbsp;</span>Подготовим и обучим модель</a></span></li><li><span><a href="#Оценим-метрику-F1" data-toc-modified-id="Оценим-метрику-F1-2.1.2"><span class="toc-item-num">2.1.2&nbsp;&nbsp;</span>Оценим метрику F1</a></span></li><li><span><a href="#Оценим-важность-коэффициентов" data-toc-modified-id="Оценим-важность-коэффициентов-2.1.3"><span class="toc-item-num">2.1.3&nbsp;&nbsp;</span>Оценим важность коэффициентов</a></span></li></ul></li><li><span><a href="#Модель-LGBMClassifier" data-toc-modified-id="Модель-LGBMClassifier-2.2"><span class="toc-item-num">2.2&nbsp;&nbsp;</span>Модель LGBMClassifier</a></span><ul class="toc-item"><li><span><a href="#Подготовим-и-обучим-модель" data-toc-modified-id="Подготовим-и-обучим-модель-2.2.1"><span class="toc-item-num">2.2.1&nbsp;&nbsp;</span>Подготовим и обучим модель</a></span></li><li><span><a href="#Оценим-метрику-F1" data-toc-modified-id="Оценим-метрику-F1-2.2.2"><span class="toc-item-num">2.2.2&nbsp;&nbsp;</span>Оценим метрику F1</a></span></li><li><span><a href="#Оценим-важность-коэффициентов" data-toc-modified-id="Оценим-важность-коэффициентов-2.2.3"><span class="toc-item-num">2.2.3&nbsp;&nbsp;</span>Оценим важность коэффициентов</a></span></li></ul></li></ul></li><li><span><a href="#Выводы" data-toc-modified-id="Выводы-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Выводы</a></span></li></ul></div>

---

### Некоторые визуализации проекта

**_Соотношение классов_**

![](https://i.ibb.co/b6FSHtb/image.png)


**_WordCloud негативных и позитивных комментариев_**

![](https://i.ibb.co/qsSfsfx/image.png)
![](https://i.ibb.co/gTfyVsk/image.png)

**_Оценка важности коэффициентов в регрессионной модели_**

![](https://i.ibb.co/NYKD0hx/image.png)

