Примеры использования команд

**Поиск успешных логинов**:

```bash
echo -e "2023-12-25 10:15:42 User1 Login successful\n2023-12-22 14:56:33 User2 Login failed\n2023-12-21 16:48:59 User3 Logout\n2023-12-20 09:32:21 User4 Login successful\n2023-12-19 18:23:45 User5 Login failed\n2023-12-18 07:14:38 User6 Login successful\n2023-12-17 11:25:29 User7 Login successful\n2023-12-23 20:17:03 User8 Login failed\n2023-12-24 13:48:27 User9 Login successful\n2023-12-21 05:36:54 User10 Logout\n2023-12-20 22:15:13 User11 Login failed\n2023-12-19 04:56:12 User12 Login successful\n2023-12-18 08:47:53 User13 Login failed\n2023-12-17 12:28:39 User14 Logout\n2023-12-24 19:49:55 User15 Login successful\n2023-12-23 14:35:41 User16 Login failed\n2023-12-22 06:15:37 User17 Login successful\n2023-12-25 17:26:14 User18 Login failed\n2023-12-24 21:35:50 User19 Login successful\n2023-12-23 13:47:30 User20 Logout\n2023-12-22 05:36:33 User21 Login failed\n2023-12-21 08:45:10 User22 Login successful\n2023-12-20 09:57:22 User23 Login failed\n2023-12-19 10:58:11 User24 Logout\n2023-12-18 11:33:44 User25 Login successful\n2023-12-17 12:47:59 User26 Login failed\n2023-12-16 13:58:24 User27 Login successful\n" > log.txt
grep "Login successful" log.txt > successful_logins.txt
```
![image](https://github.com/user-attachments/assets/79bf52b4-c0b6-491a-9ad6-b12264df179e)

**Поиск строк за период с 2023-12-23 по 2023-12-25**:

```bash
grep -E "2023-12-(23|24|25)" log.txt > logins_in_period.txt
```
![image](https://github.com/user-attachments/assets/8f08e330-9d71-49b6-923d-ab4f2ace1417)

**Поиск действий пользователей (Login successful или Logout)**:

```bash
grep -E "User[0-9]+ (Login successful|Logout)" log.txt > user_actions.txt
```
![image](https://github.com/user-attachments/assets/82e7d36d-dc63-4cbe-842e-a81551486604)


**Рекурсивный поиск логинов**:

```bash
mkdir logs
echo -e "Additional log data\n2023-12-15 14:49:53 User28 Login failed\n2023-12-14 15:37:12 User29 Logout\n2023-12-13 16:23:49 User30 Login successful\n" > logs/additional_log.txt
grep -r "Login" . > all_logins.txt
```
![image](https://github.com/user-attachments/assets/9402b1c8-945b-432f-b4e8-fb35a93db5f0)

