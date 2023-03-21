В стандарте HTTP описываются следующие методы запроса:

### Метод GET

Запрашивает содержимое конкретного ресурса, получает данные и никак не должен изменять эти данные.

Пример запроса:

```http
HEAD /text.txt HTTP/1.1
Host: example.com
```

Пример ответа:

```http
HTTP/1.1 200 OK
Content-Type: text/plain; charset=UTF-8
```

### HEAD

Идентичен методу GET, но не обязывает сервер возвращать в ответе тело сообщения. Используется для получения метаданных, а также проверки и валидации ресурса.

Пример запроса:

```http
HEAD /text.txt HTTP/1.1
Host: example.com
```

Пример ответа:

```http
HTTP/1.1 200 OK
Content-Type: text/plain; charset=UTF-8
```

### POST

Используется для создания нового ресурса из переданных данных в запросе. Действия также могут быть другими или отсутствовать вовсе.

Пример запроса:

```http
POST /text.txt HTTP/1.1
Host: example.com

Title=Заголовок+файла
Text=Текст+файла
```

Пример ответа:

```http
HTTP/1.1 201 Created
Location: /text.txt
```

### PUT

Вызывает на сервере удаленную функцию, которая обращается к уже существующей записи на удаленном сервере. Используется для обновления данных, статей и в блоге и т.д. Действия также могут быть другими или отсутствовать вовсе.

Пример запроса:

```http
PUT /text.txt HTTP/1.1
Host: example.com

Title=Новый+заголовок+файла
Text=Новый+текст+файла
```

Пример ответа:

```http
HTTP/1.1 200 OK
Content-Type: text/plain; charset=UTF-8

Изменен контент в файле «text.txt»
```

### DELETE

Запрашивает удаление ресурса с идентификатором URI.

Пример запроса:

```http
DELETE /text.txt HTTP/1.1
Host: example.com
```

Пример ответа:

```http
HTTP/1.1 200 OK
Content-Type: text/plain; charset=UTF-8

Файл «text.txt» удален
```


### TRACE

Возвращает полученный запрос так, что клиент может увидеть, какую информацию промежуточные серверы добавляют или изменяют в запросе.

Пример запроса:

```http
TRACE / HTTP/1.1
Host: example.com
```

Пример ответа:

```http
HTTP/1.1 200 OK
Content-Type: message/http

TRACE / HTTP/1.1
Host: example.com
```

### CONNECT

Запускает двустороннюю связь с запрошенным ресурсом. Метод обычно используется для открытия прозрачного TCP/IP-туннеля.

Пример запроса:

```http
CONNECT server.example.com:80 HTTP/1.1 
Host: server.example.com:80
```

### OPTIONS

Позволяет браузеру сделать запрос о доступных вариантах взаимодействия с сервером. Помогает узнать, принимает ли сервер вызовы GET, PUT, DELETE и OPTIONS.

Пример запроса:

```http
OPTIONS * HTTP/1.1
Host: example.com
```

Пример ответа:

```http
HTTP/1.1 200 OK
Allow: OPTIONS, GET, HEAD, POST, PUT, PATCH, DELETE, TRACE
```

---
Теги: #web-security 