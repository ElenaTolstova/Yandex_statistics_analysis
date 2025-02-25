<div style="border: solid gray 2px; padding: 20px">
    
# Исследование данных аренды самокатов GoFast.

Суть проекта: нам предстоит проанализировать данные аренды самокатов GoFast пользователями из нескольких городов, а также данные об их поездках. Проверим некоторые гипотезы, которые могут помочь бизнесу вырасти.

---
Чтобы совершать поездки по городу, пользователи сервиса GoFast пользуются мобильным приложением. Сервисом можно пользоваться:
- без подписки

    - абонентская плата отсутствует;
    - стоимость одной минуты поездки — 8 рублей;
    - стоимость старта (начала поездки) — 50 рублей;

- с подпиской Ultra
    - абонентская плата — 199 рублей в месяц;
    - стоимость одной минуты поездки — 6 рублей;
    - стоимость старта — бесплатно.

---
   
**Описание данных**

В основных данных есть информация о пользователях, их поездках и подписках.

Таблица users_go:
- `user_id` - уникальный идентификатор пользователя
- `name` - имя пользователя
- `age` - возраст
- `city` - город
- `subscription_type` - тип подписки (free, ultra)

Таблица rides_go:
- `user_id` - уникальный идентификатор пользователя
- `distance` - расстояние, которое пользовтаель проехал в текущей сессии (в метрах)
- `duration` - продолжительность сессии (в минутах) - время с того момента, как пользователь нажал кнопку "Начать поездку" до момента, как он нажал кнопку "Завершить поездку"
- `date` - дата совершения поездки

Таблица subscriptions_go:
- `subscription_type` - тип подписки
- `minute_price` - стоимость одной минуты поездки по данной подписке
- `start_ride_price` - стоимость начала поездки
- `subscription_fee` - стоимость ежемесячного платежа
---
    
**Цель исследования**

1. Изучить данные по вакансиям портала HH.ru и выявить интересные закономерности.
2. Выявить различия в предлагаемых вакансиях для Аналитиков данных и специалистов по Data Science.
3. Написать выводы по результатам исследования.
---
    
***Ход исследования***
    
Данные о вакансиях получим из двух файлов: vacancies_da.xlsx и vacancies_sa.xlsx О качестве датасета информации нет. Перед тем как приступать к цели исследования, нам необходимо изучить данные.
    
Проверим данные на предмет ошибок и оценим их влияние на результаты исследования. В процессе преодобработки данных попробуем исправить все ошибки, которые могут привести к искажению конечного результата. Далее мы проиллюстрируем все гипотезы и выводы на подходящих графиках и приступим к исследовательскому анализу данных и выявлению закономерностей.
    
Таким образом, мое исследование пройдет в следующие этапы:
    
- Загрузка и предобработка данных.
- Исследовательский анализ данных.
- Объединение датафреймов в общий с данными и разделение его на два: пользователей с подпиской и пользователей без подписки.
- Подсчет выручки, суммарного расстояния, количества поездок и суммарного времени для каждого пользователя за каждый месяц.
- Проверка гипотез.
- Подбор параметров распределений для двух задач и визуализация их на графиках.
- Формулирование выводов и рекомендаций.
