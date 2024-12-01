# Marketing_project


**ПОСТАНОВКА ЗАДАЧИ**

**Заказчик этого исследования** — руководство интернет-магазина. 


**Исходные данные:** Предоставлены в трёх файлах:
- `apparel_messages.csv`  — таблица с данными коммуникации с клиентом
- `apparel_purchases.csv` — таблица с данными о покупках клиентов.
- `apparel_target_binary.csv`  — таблица с данными о целевом признаке.


**Цель исследования**: предсказать вероятность покупки клиентом в течение 90 дней.

**Задачи исследования:**
- Разработать модель для прогнозирования вероятности покупки клиентом в течение 90 дней.

Таким образом, исследование направлено на улучшение взаимодействия клиентами.

**Ход исследования**

Данные мы получим из файлов: `apparel_messages.csv`, `apparel_purchases.csv`, и `apparel_target_binary.csv.`.

Мы проверим данные на ошибки и оценим их влияние на исследование. Затем, на этапе предобработки мы отыщем возможность исправить самые критичные ошибки данных. Далее проведем исследовательский анализ данных и выявим основные закономерности в данных. После этого подготовим данные к машинному обучению, путем объединения данных. 


**РЕАЛИЗАЦИЯ ПРОЕКТА**


1. **Загрузка и первичный обзор данных:**
   - Были импортированы необходимые библиотеки для работы с данными и визуализации.
   - Данные успешно загружены из трёх csv-файлов.
   - Проведен первичный анализ типов данных и отсутствие пропусков в данных, что свидетельствует о высоком качестве информации.


2. **Предобработка данных:**
   - Аномальные значения были удалены для обеспечения точности данных.
   - Визуализация данных подтвердила отсутствие аномалий в количественных параметрах после удаления аномалий.


3. **Исследовательский анализ данных:**
   - Были исследованы количественные и категориальные признаки визуально. 
   - Сделаны выводы на основании полчившихся графиков


4. **Корреляционный анализ:**

Исходя из матрицы корреляции можно отметить, что мультиколлиниарность между признаками - отстствует.

Присутствует умеренная зависимость между стоимостью одного предмета в заказе и средней стоимостью заказа (0,55). Оно и понятно. Также есть умеренная зависимость между средней стоимостью заказа и средним количеством предметов в заказе (0,47) - и это тоже понятно и логично. Остальные корреляции не так заметны и влияют друг на друга.

Можно отметить, что больше всего на таргет влияет среднее количество дней до следующего заказа и отрицательно виляет количество дней с момента последнего заказа.

Также следует отметить, что есть отрицательная корреляция между средней стоимостью предмета в заказе и количеством. Тоже логично, чем дороже покупка - тем меньше предметов будет в заказе. Среднее количество также отрицательно виляет на количество дней с момента последнего заказа.



6. **Использование пайплайнов и обучение модели:**
   - В разделах использования пайплайнов и обучения моделей мы провели комплексную обработку данных и обучение моделей машинного обучения.
   - Применяя стратифицированное разделение данных на обучающую и валидационную выборки, мы гарантировали сохранение распределения целевой переменной.
   - Применение различных методов предобработки данных (кодирование категориальных признаков, масштабирование числовых признаков) было осуществлено с использованием пайплайнов.
   - После подготовки данных были обучены различные модели машинного обучения с использованием GridSearchCV для поиска оптимальных гиперпараметров.
   
Итоговый анализ корреляций и использование пайплайнов позволили не только выявить взаимосвязи между различными признаками данных, но и построить эффективную модель для классификации данных


7. **Анализ важности признаков:**
В разделе 7 "Анализ важности признаков" были проведены важные шаги по пониманию того, какие атрибуты играют наиболее значимую роль в прогнозировании целевого признака. Важно отметить, что это позволяет более точно настраивать модель и оптимизировать её производительность. 


- **Наиболее важные признаки:**
   - Количество дней до следующего заказа.
   - Количество дней между последним заказом и датой выгрузки данных.
   - Средняя цену одного продукта.

Эти признаки имеют наибольший вклад в прогнозирование целевого признака и могут использоваться для оптимизации бизнес-стратегии.



- **Выводы:**
   - Покупательское поведение, такое как активность на сайте и участие в акциях, имеет решающее значение для предсказания покупок клиентов.
   - Некоторые атрибуты, такие как маркетинговая активность в текущем месяце, могут оказывать влияние, но их вклад незначителен по сравнению с другими факторами.
   - При разработке стратегии следует сосредоточиться на увеличении взаимодействия с сайтом и создании привлекательных акций для клиентов.

Эти выводы предоставляют ценную информацию для дальнейшего улучшения модели и оптимизации бизнес-процессов.

8. **"Сегментация покупателей**

- Т.к. наши модели не оказались достаточно эффективными в предсказании. Лучшая модель для поставленной задачи оказалась при подборе гиперпараметров на метрике recall. Можно пересмотреть метрику для достижения поставленной задачи.
- Предлагается заказчику пересмотреть метрику и улучшить модель с метрикой recall.