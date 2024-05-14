### Homework 5

Використовувати аплікацію CarService із попереднього ДЗ.

Сутність Owner перейменувати на User (ім'я цієї змінної в Car може лишитися) - це стосується і сервісу, і контролера, і таблиці в базі даних (за допомогою liquibase переназвати таблицю).
Зробити sql міграцію на видалення усіх даних з Car і Owner (User). Видалення має відбуватися до перейменування.

Налаштувати security для аплікації. За допомогою сутності User розширити інтерфейс UserDetails. Додати поле в базі для зберігання пароля і ролі.

Додати ендпоінти для реєстрації/авторизації (ендпоінти можна назвати на власний розсуд, аби функціонал зберігся):
1. POST /auth/signup - зареєструвати нового користувача (завжди видається стандартна роль - назву можна придумати самому).
2. POST /auth/signin - увійти за допомогою username/password - має повертати accessToken і refreshToken у JWT форматі.

Усі ендпоінти окрім /auth/** і /error повинні бути доступні лише для авторизованих користувачів.
Авторизація користувачів відбувається за допомогою accessToken.

Зробити наступні обмеження:
1. Оновлювати/видаляти (PUT/DELETE) авто може лише власник або користувач із роллю ADMIN*.
2. Створювати/оновлювати/видаляти Maintenance може лише користувач із роллю ADMIN*.
3. Видаляти користувача може лише користувач із роллю ADMIN*.
4. Змінювати дані користувача може лише сам користувач або користувач з роллю ADMIN.
5. У системі не повинно бути 2 однакових username або email.

_*_ - роль ADMIN можна поставити вручну через базу даних