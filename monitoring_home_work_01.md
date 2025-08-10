1) Подключить запущенное в [домашке](https://github.com/AnastasiyaGapochkina01/V0vchek/blob/main/docker_home_work_05.md) к prometheus
2) Создать дашборд в grafana с
- панелью, показывающей запущено приложение или нет
- графиком общего количества запросов за 1 минуту
- круговой диаграмму с разбивкой по эндпоинтам
- количеством ошибок (например, HTTP статусы 4xx и 5xx) в виде графика
- графиком или таблицей с количеством запросов по HTTP методам (GET, POST и т.д.)
3) Создать дашборд в grafana для метрик
- node-exporter
- cadvisor-exporter
- nginx-exporter
P.S все экспортеры запустить в docker
