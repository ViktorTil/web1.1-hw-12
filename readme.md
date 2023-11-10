Cтворено REST API для зберігання та управління контактами. API побудований з використанням інфраструктури FastAPI, використовується модуль перевірки достовірності даних Pydantic та використовується SQLAlchemy для управління базою даних(PostgreSQL).
Реализован механизм аутентификации в приложении;
Реализован механизм авторизации с помощью JWT токенов, чтобы все операции с контактами производились только зарегистрированными пользователями;
Пользователь имеет доступ только к своим операциям с контактами;
Механизм авторизации с помощью JWT токенов реализован парой токенов: токена доступа access_token и токен обновления refresh_token

Контакти зберігаються в базі даних та містять в собі наступну інформацію:

Ім'я
Прізвище
Електронна адреса
Номер телефону
День народження

API має можливість виконувати наступні дії только для зарегистрированных пользователей:

Створити новий контакт
Отримати список всіх контактів
Отримати один контакт за ідентифікатором
Оновити існуючий контакт
Видалити контакт
На придачу до базового функціоналу CRUD API також має наступні функції:

Контакти доступні для пошуку за іменем, прізвищем чи адресою електронної пошти (Query).
API має змогу отримати список контактів з днями народження на найближчі 7 днів.

Для запуска нужно в контенере запустіть Postgres.
В DBeaver в соединении Postgres создать новую БД : rest_api.
В основной папке запускаем main.py 
Далее в браузере открываем : http://127.0.0.1:8000/docs/ и тестируем!
Сначала регистрируем нового пользователя, а затем уже, после логина, авторизуем пользователя : Authorize при помощи bearer и почта-пароль, получаем доступ к функциям API.