### Homework 2

Використовувати аплікацію CarService із попереднього ДЗ.

Підключити базу даних (на вибір - PosgreSQL, MySQL чи інша)

Створити сутність __Car__, для роботи з базою даних.

```
Car { id, model, enginePower }
```

За допомогою liquibase створити міграцію (changelog/changeset) на створення таблиці __car__ у базі даних.

Додати __CarController__ з базовими _CRUD_ операціями:

1. GET /cars - повертає список усіх авто
2. GET /cars/{id} - повертає конкретне авто по ІД
3. POST /cars - створює нове авто
4. PUT /cars/{id} - оновлює дані про авто по ІД
5. DELETE /cars/{id} - видалити авто по ІД
6. Для GET /cars реалізувати пошук за наступними параметрами (@RequestParam):
    - minEnginePower - мінімальна потужність двигуна
    - maxEnginePower - максимальна потужність двигуна

Додати нову колонку _torque_ до таблиці __car__ і відповідної сутності через _changeSet_.
