# Module 10 [ORM. Hibernate]

Ти працюєш в компанії SpaceTravel. Компанія займається перевезенням пасажирів між планетами.

Відповідно, є наступні сутності з наступними зв'язками:

- __Client__ (клієнт) - клієнт компанії. Має наступні властивості:
    - `id` - ідентифікатор, первинний сурогатний ключ, автоінкрементне число.
    - `name` - ім'я, від `3` до `200` символів включно
- __Planet__ (планета). Початковий або кінцевий пункт відправлення. Має наступні властивості:
    - `id` - ідентифікатор планети. Рядок, що складається виключно з латинських букв у верхньому регістрі та цифр. Наприклад, `MARS`, `VEN`
    - `name` - назва планети, рядок від `1` до `500` символів включно
- __Ticket__ (квиток). Має наступні властивості:
    - `id` - ідентифікатор квитка, первинний сурогатний ключ, автоінкрементне число.
    - `created_at` - `TIMESTAMP` в `UTC`, коли був створений цей квиток
    - `client_id` - ідентифікатор клієнта, якому належить цей квиток.
    - `from_planet_id` - ідентифікатор планети, звідки відправляється пасажир
    - `to_planet_id` - ідентифікатор планети, куди летить пасажир

## Завдання №1 - налаштуй проєкт з hibernate
Створи новий gradle проєкт. Підключи до нього наступні бібліотеки:

- PostgreSQL
- hibernate
- flyway

Переконайсь, що твій проєкт запускається та не видає ніяких помилок.

## Завдання №2 - напиши міграції для створення та наповнення БД
Напиши дві міграції.

Перша міграція (назви її `V1__create_db.sql`) має створити структуру БД - всі таблиці та зв'язки між ними. Зверни увагу на коректні обмеження. Наприклад, для таблиці `ticket` поле `client_id` має бути як foreign key для таблиці `client` по полю `id`.

Друга міграція має наповнити БД даними (назви цю міграцію `V2__populate_db.sql`). Створи як мінімум:

- `10` клієнтів
- `5` планет
- `10` квитків
Переконайсь, що програма запускається і обидві міграції коректно виконуються.

## Завдання №3 - створи CRUD сервіси для Client та Planet
Опиши сутності `Client` та `Planet`. Пропиши Hibernate мапінги для цих сутностей (таблиці в БД `client` та `planet` відповідно).

Напиши CRUD сервіси для обох сутностей - `ClientCrudService` та `PlanetCrudService`.

Напиши тестовий код, який додаватиме/видалятиме записи за допомогою цих сервісів. Переконайсь, що всі CRUD операції працюють правильно.

## Завдання №4 - залий код на Github
Залий код на Github репозиторій. Переконайсь, що файл `.gitignore` налаштований коректно, і в репозиторій потрапили лише потрібні файли.

Результат ДЗ - посилання на репозиторій.
