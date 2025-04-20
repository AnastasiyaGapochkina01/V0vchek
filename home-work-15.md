1) Установить и запустить minikube на ВМ\
https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fdebian+package
2) Запустить pod`ы
- nginx
- apache
- php:8.2-fpm
- debian
3) Получить информацию о запущенных подах
4) Удалить запущенные pod`ы
5) Запустить pod с двумя контейнерами как тут https://github.com/kubernetes/website/blob/main/content/en/examples/pods/two-container-pod.yaml и сделать запрос на nginx с помощью curl
6) Удалить все запущенные pod`ы
7) Запустить pod из image ```debian```, с именем demo-container, и в котором выполняется command ```printenv```, получить информацию о pod`е
8) Запустить репликасет с 3 репликами приложения с image ```gcr.io/google-samples/hello-app```
9) Удалить все созданные сущности
10) Запустить deployment с 3 репликами приложения с image ```gcr.io/google-samples/hello-app```
11) Обновить версию деплоймента с ```gcr.io/google-samples/hello-app``` на ```gcr.io/google-samples/hello-app:1.0```, а потом на ```gcr.io/google-samples/hello-app:2.0```
12) Откатить деплоймент на изначальную версию
13) Удалить все сущности
