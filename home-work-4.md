1) В домашней директории создать каталог lab04
2) В lab04 создать директорию devops-project
3) В devops-project создать директории frontend, backend и storage
4) В директории storage оздать файл data.csv с таким содержимым
```
Name Department Phone
J.Smith development +19873456
S.Grows security -
E.Bett-Rikards development +13456239
S.Brown qa +19746293
E.Green manager +16734567
```
5) В директории frontend создать файл index.html с таким содержимым
```
<!DOCTYPE html>
<html>
<body>

<h1>Frontend</h1>
</body>
</html>
```
6) В devops-project с помощью команды echo создать файл proxy.conf с содержимым
```
# TODO: nginx conf
```
7) В директории backend создать файл app с таким содержимым
```
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```
8) В lab04 создать директорию archive
9) Скопировать директории frontend, backend и storage в archive
10) Переименовать frontend, backend и storage, находящиеся в archive в frontend_bk, backend_bk и storage_bk
11) В директории frontend создать 5 файлов с именами по списку и любым содержимым:
- checkout.html
- footer.html
- logo.png
- promo
- style.css
12) Скопировать все файлы из директории frontend в frontend_bk
13) Переименовать файл logo.png в logo
14) Создать в frontend директорию styles и переместить туда style.css
15) Посмотреть первые шесть записей любого лога из /var/log
16) Посмотреть последние двадцать записей любого лога из /var/log
17) Посмотреть содержимое файла /proc/meminfo
18) Посмотреть содержимое файла /proc/cpuinfo
19) Вывести 4 и 5 строки из файла /etc/group
20) Посмотреть содержимое файла /etc/network/interfaces
21) В lab04 создать директорию logs
22) В logs создать 4 файла:
- application.log
- stderr.log
- debug.log
- manticore.log
23) С помощью tail "подцепиться" ко всем логам, открыть вторую вкладку терминала, перейти в диреткорию где лежат созданные в п22 файлв и выполнить там
```
for i in {1..10}; do echo -e "App Log Line $i at [$(date +"%Y-%m-%dT%H:%M:%S")]" >> application.log; sleep 1; echo -e "DEBUG $i" >> debug.log; echo -e "$(date +"%a %b %d %H:%M:%S") 0.00$i sec" >> manticore.log; done
```
24) Посмотреть результат в соседней вкладке и отстрелить отслеживание
