# Linux Cheatsheet


## Contents
- Main commands
- Process monitoring commands
- Performance monitoring commands
- Networking tools
- Text manipulation
- Troubleshooting tools
- File systems
- CRON


## Main commands
- __cd__: Изменение рабочей директории.
- __chmod__: Управление правами доступа.
- __chown__: Управление владением.
- __cp__: Копирование файлов и каталогов, создание бэкапов. Не удобна при копировании больших файлов, так как нет вывода прогресса копирования.
- __df__: Информация об использовании дискового пространства.
- __dirb__: 
- __du__: 
- __env__: 
- __export__: 
- __fierce__: 
- __find__: 
- __free__: 
- __gunzip__: 
- __gzip__: 
- __head__: Инструмент для отображения первых строк текстового файла.
- __history__: 
- __host__: 
- __ifconfig__: 
- __ip__: 
- __kill__: 
- __less__:
- __locate__:
- __ls__:
- __man__:
- __mkdir__:
- __more__:
- __mount__:
- __mv__:
- __nikto__:
- __pwd__:
- __rm__:
- __service__:
- __ssh__:
- __sudo__:
- __tail__: Инструмент для отображения последней части файла.
- __tar__:
- __touch__:
- __uname__:
- __uptime__:
- __useradd__:
- __userdel__:
- __usermod__:
- __w__:
- __wget__:
- __whatis__:
- __whois__:
- __zip__:


## Process monitoring commands
- __ps__:
- __top__:
- __htop__:
- __atop__:
- __lsof__:


## Performance monitoring commands
- __nmon__:
- __iostat__:
- __sar__:
- __vmstat__:


## Networking tools
- __traceroute__:
- __ping__:
- __mtr__:
- __nmap__:
- __netstat__:
- __ufw__:
- __iptables__/__nftables__:
- __tcpdump__:
- __dig__:
- __scp__:


## Text manipulation
- __awk__:
- __sed__:
- __grep__:
- __sort__:
- __cut__:
- __uniq__:
- __cat__:
- __echo__:
- __fmt__:
- __tr__:
- __nl__:
- __wc__:


## Troubleshooting tools
- __hping__:
- __memdump__:
- __nslookup__:
- __wireshark__:
- __winhex__:
- __npcap__:
- __ipconfig__:
- __masscan__:
- __angry ip scanner__:
- __arp__:
- __ethereal__:
- __route__:
- __curl__:
- __dd__:


## File systems
- __bin__: Двоичные файлы многих основных программ, которые должны присутствовать при монтировании системы.
- __sbin__:Аналогичен bin, но содержит файлы утилит системного администрирования.
- __boot__: Файлы для загрузки системы.
- __dev__: Файлы устройства.
- __etc__: Общесистемные файлы конфигурации для хоста, которые используются администратором системы и службами, такие как файл паролей или файлы настроек сетей.
- __home__: Домашний каталог пользователей.
- __lib__: Библиотеки, необходимые двоичным файлам в каталогах bin, sbin.
- __media__: Медиа файлы. При подключении съемного носителя создается папка в этом каталоге с содержимым носителя.
- __mnt__: Временно смонтированные файлы системы. Используется администратором системы для ручного монтирования файловых систем.
- __opt__: Дополнительные пакеты ПО. Используется проприентарным ПО.
- __proc__: Автоматически сгенерированные файлы системы, которые содержат информацию о запущенных процессах и состоянии ядра.
- __root__: Домашняя директория root.
- __run__: Данные программ во время выполнения (сокеты, ID процессов).
- __srv__: Специфичные данные, обслуживаемые этой системой (Файлы Apache).
- __sys__: Виртуальный диалог, представляющий информацию о системе.
- __tmp__: Временные файлы. При перезагрузке системы содержимое каталога удаляется.
- __usr__: Исполняемые файлы пользовательских программ.
- __var__: Постоянно изменяемые файлы (файлы журналов, кэш программ).


## CRON
### Format
```
[Minute (0..59)] [Hour (0..23)] [Day (1..31)] [Month (1..12)] [Weekday (0..6)] [Command to be executed]
```
### Operators
- __*__: all values.
- __,__: separate individual values.
- __-__: a range of values.
- __/__: divide a value into steps.
### Special strings
- __@reboot__: every reboot.
- __@hourly__: once every hour - same as `0 * * * *`.
- __@daily__: once every day - same as `0 0 * * *`.
- __@midnight__: once every midnight - same as `@daily`.
- __@weekly__: once every week - same as `0 0 * * 0`.
- __@monthly__: once every month - same as `0 0 1 * *`.
- __@yearly__: once every year - same as `0 0 1 1 *`.
### Examples
```
Every 15 mins:
*/15 * * * *

Every 2 hours:
0 */2 * * *

Every week Mon-Sat at 6pm:
0 18 * * 0-6

Every Sat and Sun on 2:10am:
10 2 * * 6,7

Adding tasks easily:
echo “@reboot echo hi” | crontab

Open in editor - optional for another user:
crontab -e [-u user]

List tasks - optional for another user:
crontab -l [-u user]

Delete crontab file - optional for another user:
crontab -r [-u user]
```