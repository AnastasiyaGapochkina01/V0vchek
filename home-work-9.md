1) Написать скрипт, который будет собирать информацию о системе и выводить ее в табличном виде:
- версия ОС
- количество ядер cpu
- размер оперативной памяти
- размер ФС, смонтированной в /
2) Написать скрипт, который будет получать сколько процентов диска использовано и делать запись в файл /var/log/disk_space.log, если это число превысило 80%
3) Написать скрипт, который заменяет расширения у файлов в заданной диреткории: скрипту передается 3 аргумента какое расширение меняем, на какое меняем и в какой директории, например
```
./change.sh txt file ./
```
результатом будет изменение расширения txt на file всех файлов в текущей директории
