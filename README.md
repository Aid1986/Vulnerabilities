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

#### SYN

```console
nmap -sS <ip>
```
По протоколу TCP отправляется пакет с флагом ACK. 

Если что-то прослушивает порт, возвращается пакет с флагом SYN. Тогда для завершения отправляется пакет с RST.

![2](https://github.com/Aid1986/Vulnerabilities/blob/main/2.png)

Может прийти пакет с RST, ACK – тогда порт в списке открытых не отобразится.

![3](https://github.com/Aid1986/Vulnerabilities/blob/main/3.png)

#### FIN

```console
nmap -sA <ip>
```

По протоколу TCP отправляет пакет с флагом FIN.

Если никто не отвечает, отображает информацию по порту.

![4](https://github.com/Aid1986/Vulnerabilities/blob/main/4.png)

Если пришёл ответ, порт в список не добавляется.

![5](https://github.com/Aid1986/Vulnerabilities/blob/main/5.png)

#### Xmas

```console
nmap -sX <ip>
```

Ситуация примерно та же, что с FIN, только отпавляются три флага: FIN, PSH и URG:

![6](https://github.com/Aid1986/Vulnerabilities/blob/main/6.png)

![7](https://github.com/Aid1986/Vulnerabilities/blob/main/7.png)

#### UDP

```console
nmap -sU <ip>
```

Отличие этого метода можно обнаружить и без Wireshark – он медленный. Зато Wireshark помогает понять, почему – пакеты отправляются неколько раз. Другое заметное отличие – использование другого протокола и различие в виде запроса для некоторых портов:

![8](https://github.com/Aid1986/Vulnerabilities/blob/main/8.png)

![9](https://github.com/Aid1986/Vulnerabilities/blob/main/9.png)

Порты помечаются как открытые (но фильтрующие), если после нескольких попыток ответ не пришёл.

При получении ICMP ответа о недостижимости порт считается закрытым.

![10](https://github.com/Aid1986/Vulnerabilities/blob/main/10.png)
