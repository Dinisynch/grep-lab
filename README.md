# Лабораторная работа

## Цель
Научиться использовать команду `grep` для выполнения поисковых операций.

## Предварительные требования:

1. Установленная команда `grep` на локальной машине.
   
## Часть 1: Простое задание


#### Шаги:

1. **Создайте файл с тестовыми данными**:
   ```bash
   echo -e "Hello, World!\nThis is a test file.\nGrep is a powerful tool.\nLet's learn how to use grep.\nGrep can find patterns in text files.\n" > example.txt
   ```


2. **Поиск строки в файле**:

   ```bash
   grep "Hello" example.txt
   ```
   **Ожидаемый результат**:
   ```
   Hello, World!
   ```
3. **Игнорирование регистра при поиске**:
   ```bash
   grep -i "grep" example.txt
   ```
   **Ожидаемый результат**:
   ```
   Grep is a powerful tool.
   Let's learn how to use grep.
   Grep can find patterns in text files.
   ```
4. **Показать номера строк с совпадениями**:
   ```bash
    grep -n "Grep" example.txt
   ```
    **Ожидаемый результат**:
   ```
   3:Grep is a powerful tool.
   5:Grep can find patterns in text files.
   ```
5. **Вывод строк, которые НЕ содержат шаблон**:
   ```bash
   grep -v "Grep" example.txt
   ```
   **Ожидаемый результат**:
   ```
   Hello, World!
   This is a test file.
   Let's learn how to use grep.
   ```

### Задача на выполнение

##### Цель:
Использовать команду `grep` для выполнения сложных поисковых операций, включая использование регулярных выражений, рекурсивного поиска и фильтрации данных.

##### Задание:
1. **Создайте файл `log.txt` и добавьте туда следующий текст**:
   ```bash
   echo -e "2023-12-25 10:15:42 User1 Login successful\n2023-12-22 14:56:33 User2 Login failed\n2023-12-21 16:48:59 User3 Logout\n2023-12-20 09:32:21 User4 Login successful\n2023-12-19 18:23:45 User5 Login failed\n2023-12-18 07:14:38 User6 Login successful\n2023-12-17 11:25:29 User7 Login successful\n2023-12-23 20:17:03 User8 Login failed\n2023-12-24 13:48:27 User9 Login successful\n2023-12-21 05:36:54 User10 Logout\n2023-12-20 22:15:13 User11 Login failed\n2023-12-19 04:56:12 User12 Login successful\n2023-12-18 08:47:53 User13 Login failed\n2023-12-17 12:28:39 User14 Logout\n2023-12-24 19:49:55 User15 Login successful\n2023-12-23 14:35:41 User16 Login failed\n2023-12-22 06:15:37 User17 Login successful\n2023-12-25 17:26:14 User18 Login failed\n2023-12-24 21:35:50 User19 Login successful\n2023-12-23 13:47:30 User20 Logout\n2023-12-22 05:36:33 User21 Login failed\n2023-12-21 08:45:10 User22 Login successful\n2023-12-20 09:57:22 User23 Login failed\n2023-12-19 10:58:11 User24 Logout\n2023-12-18 11:33:44 User25 Login successful\n2023-12-17 12:47:59 User26 Login failed\n2023-12-16 13:58:24 User27 Login successful\n"
   ```

2. **Найдите все строки, содержащие успешные входы (Login successful)**.
   - Используйте команду `grep` для поиска строк, содержащих "Login successful".
   - Запишите результат в файл `successful_logins.txt`.

3. **Используя регулярное выражение, найдите все строки, содержащие временной период, например, с 2023-12-23 по 2023-12-25**.
   - Используйте команду `grep` с регулярным выражением для поиска строк за указанный период.
   - Запишите результат в файл `logins_in_period.txt`.

4. **Найдите все строки, где указано имя пользователя (UserX), который выполнил вход (Login successful) или выход (Logout)**.
   - Используйте команду `grep` с регулярным выражением для поиска строк, содержащих "User" и "Login" или "Logout".
   - Запишите результат в файл `user_actions.txt`.

5. **Используя рекурсивный поиск, найдите все файлы в текущем каталоге и его подкаталогах, содержащие слово "Login"**.
   - Создайте подкаталог `logs` и создайте в нем файл с следующими данными для поиска.
     ```
     "Additional log data\n2023-12-15 14:49:53 User28 Login failed\n2023-12-14 15:37:12 User29 Logout\n2023-12-13 16:23:49 User30 Login successful\n"
     ```
   - Используйте команду `grep` с опцией рекурсивного поиска.
   - Запишите результат в файл `all_logins.txt`.


### Ссылки на материалы

- [Документация по регулярным выражениям в grep](https://www.gnu.org/software/grep/manual/grep.html#Regular-Expressions)
- [Углубленное руководство по использованию grep](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)


### Как успешно сдать работу?

1. Создайте новый репозиторий на GitHub.
2. Добавьте файл `README.md` с описанием лабораторной работы, включая шаги и задачи.
3. Создайте файлы `log.txt`, `successful_logins.txt`, `logins_in_period.txt`, `user_actions.txt` и `all_logins.txt` и добавьте их в репозиторий.

Пример структуры репозитория:
```
grep-lab/
├── README.md
├── log.txt
├── successful_logins.txt
├── logins_in_period.txt
├── user_actions.txt
└── all_logins.txt
```
