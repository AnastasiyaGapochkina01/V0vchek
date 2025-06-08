1) Дан скрипт на python
```
from flask import Flask
import sys
import os

app = Flask(__name__)

@app.route('/')
def index():
    python_version = sys.version
    current_directory = os.getcwd()
    return f"Версия Python: {python_version}\nТекущая директория: {current_directory}"

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```
Необходимо собрать для него docker image и запустить из него контейнер с помощью docker compose; проверка осуществлется командой `curl`, например
```
anestesia@projects-dev:~$ curl 127.0.0.1:5000
Версия Python: 3.9.2 (default, Mar 20 2025, 02:07:39)
[GCC 10.2.1 20210110]
Текущая директория: /home/anestesia/python
```
2) Для [приложения на nodejs](https://gitlab.com/devops201206/simple_node) собрать docker image и запустить из него контейнер с помощью docker compose
3) Дано простое приложение на golang
```
package main

import (
    "fmt"
    "log"
    "net/http"
    "time"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
    if r.URL.Path != "/" {
        http.Error(w, "404 Not Found", http.StatusNotFound)
        return
    }

    currentTime := time.Now().Format(time.RFC3339)
    greeting := "Hello!"

    fmt.Fprintf(w, "Current time: %s\n%s", currentTime, greeting)
}

func main() {
    http.HandleFunc("/", helloHandler)

    fmt.Println("Server started on 9100")
    log.Fatal(http.ListenAndServe(":9100", nil))
}
```
Необходимо собрать для него docker image и запустить из него контейнер с помощью docker compose. Проверка работоспособности
```
anestesia@projects-dev:~/golang$ curl 127.0.0.1:9100/
Current time: 2025-04-12T03:22:10Z
Hello!
```
