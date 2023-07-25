## Автоматичний старт сервера DDoS від IT Army Ukraine (ADSS)

ADSS - це скрипт, написаний на Shell, який автоматично оновлює себе і визначає версію, розрядність та дистрибутив вашої ОС Linux.

Протестована підтримка поточної версії - ubuntu, debian, fedora, centos (х86,х64,arm)

#### [English version - click here](/README-EN.md)
#### 💁 [Технічна підтримка](https://t.me/+H6PnjkydZX0xNDky)

### 💽 Встановлення та запуск

Використовуйте цю команду для встановлення :

```
curl -sL https://raw.githubusercontent.com/it-army-ua-scripts/ADSS/install/install.sh  | bash -s
```

Під час встановлення скрипт автоматично встановлює потрібні пакети:

`zip, unzip, gnupg, ca-certificates, curl, git, dialog`

### 🛠 Керування ADSS

Запуск ADSS : 

```
adss
```

Запуск ADSS англійською мовою : 

```
adss --lang en
```

Ця команда автоматично встановлює потрібні інструменти DDoS для вашої системи, налаштовує захист від брутфорса, встановлює фаєрвол, запускає MHDDOS і додає MHDDOS до автозавантаження системи. Лог процесу відображається в реальному часі :

```
adss --auto-install
```

Повне відновлення\перевстановлення скрипта до налаштувань за замовчуванням :

```
adss --restore
```

### ✪ Пункти меню
<details>
<summary>Розгорнути</summary>

- **Розширення портів :**

Для підвищення ефективності DDOS атаки, а саме на ОС Linux потрібно дозволити відкривати безліч вихідних мережевих підключень, необхідно збільшити локальний діапазон портів TCP. Це відбувається шляхом додавання до файлу `/etc/sysctl.conf` строки `net.ipv4.ip_local_port_range=16384 65535`.(пункт за бажанням, не є обов’язковим)

- **Налаштування безпеки - (пункт за бажанням, не є обов’язковим) :**
- **Встановлення захисту :**

Автоматично встановлюється у НЕ активному стані UFW Firewall та захист від брутфорса Fail2ban

- **Налаштування захисту :**

- **Налаштування фаєрвола :**

Забороняється весь вхідний трафік, окрім по 22/tcp порту для підключення до машини по SSH, дозволяється весь вихідний трафік.

- **Налаштування захисту від брутфорса :**

Дозволяє 3 спроби підключення по SSH, у випадку невдалих спроб (не вірний логін чи пароль) блокує атакуючий ip на 10 хвилин.

- **DDOS :**

- **Встановлення ддос інструментів :**

Автоматичне встановлення db1000n, distress, mhddos відповідної архітектури та розрядності для відповідної машини. Для кожної утиліти окрім завантаження, створюється системна служба. Це дозволяє стежити за її станом і у випадку збою чи перезавантаження машини автоматично запустити її знову. 

- **Управління ддос інструментами :**

- **Налаштування автозапуску :**

Автоматичний запуск ddos утиліти при включенні\перезавантаженні машини.

- **Статус атаки :**

Перегляд логу запущеної утиліти в реальному часі з автоматичним оновленням виводу.

- **Зупинити атаку :**

Пункт відображається тільки у разі активної ддос утиліти.

- **MHDDOS :**

- **Запуск/Зупинка MHDDOS :**

Змінюється у залежності від поточного стану. Почати ддос атаку.

- **Увімкнути/Вимкнути автозавантаження :**

Змінюється у залежності від поточного стану. Додає системну службу MHDDOS у список автозавантаження після перезавантаження операційної системи.

- **Налаштування MHDDOS :**

Зрозуміле покрокове тонке налаштування утиліти для збільшення\зменшення навантаження на систему, ефективності атаки шляхом додавання відповідних параметрів запуску для утиліти. (пункт за бажанням, не є обов’язковим)

- **Статус MHDDOS :**

Відображає поточний статус служби ддос утиліти (активна\мертва) з поточними параметрами запуску тонкого налаштування.

- **Пункти «DISTRESS» та «DB1000N» аналогічні до «MHDDOS»**

</details>