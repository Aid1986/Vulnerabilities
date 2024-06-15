# Сурмач Андрей Андреевич
# Vulnerabilities
# Задание_1
Службы

С помощью nmap можно обнаружить 23 порта, которые прослушивают OpenSSH, telnet, Apache, PostgreSQL, MySQL и кто только не.

![1](https://github.com/Aid1986/Vulnerabilities/blob/main/1.png)

#### Уязвимости

* [MySQL 5.1.23 - Server InnoDB CONVERT_SEARCH_MODE_TO_INNOBASE Function Denial of Service ](https://www.exploit-db.com/exploits/30744) – работает для MySQL 5.1.23 и ранее.<br>
Вызывает "отказ в обслуживании" за счёт ввода определённых данных.
* [PostgreSQL 8.3.6 - Conversion Encoding Remote Denial of Service](https://www.exploit-db.com/exploits/32849)<br>
Смена кодировки, из-за которой происходит разрыв соединений.
* [ProFTPd 1.3 - 'mod_sql' 'Username' SQL Injection](https://www.exploit-db.com/exploits/32798) – актуально для 1.3.1-1.3.2. <br>
SQL-инъекция.

---
# Задание_2

