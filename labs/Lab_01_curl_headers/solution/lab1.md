# HTTP|HTTPS и их параметры

## Лабораторная №1
## ст. Обуваев А.С.
## гр. АСБ-3-036
___________________________________________________

В данной работе вы будете отправлять HTTP запросы и изучать HTTP ответы.
### Цель работы
Познакомиться с протоколом HTTP и протоколом HTTPS, а так же особенностями установления соединения между источником и получателем.

Использовал такие ключи:

`-I` - указывает отправить только заголовки HTTP-ответа сервера, без тела ответа.  
`-v` - делает подробный вывод информации о запросе.  
`-L` - указывает следовать перенаправлениям при запросе, если сервер возвращает код (301 или 302).  
`-k` - отключает проверку SSL-сертификата.




#### Скрипт: 'curl (URL сайта) -I -L -k -v'

#### РГУПС

```shell
*   Trying 80.72.224.90:80...
* Connected to rgups.ru (80.72.224.90) port 80 (#0) 
> HEAD / HTTP/1.1
> Host: rgups.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
HTTP/1.1 301 Moved Permanently
< Server: nginx/1.19.1
Server: nginx/1.19.1
< Date: Thu, 12 Oct 2023 17:09:24 GMT
Date: Thu, 12 Oct 2023 17:09:24 GMT
< Content-Type: text/html
Content-Type: text/html
< Content-Length: 169
Content-Length: 169
< Connection: keep-alive
Connection: keep-alive
< Location: https://rgups.ru/
Location: https://rgups.ru/

<
* Connection #0 to host rgups.ru left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://rgups.ru/'
*   Trying 80.72.224.90:443...
* Connected to rgups.ru (80.72.224.90) port 443 (#1)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server accepted http/1.1
* using HTTP/1.1
> HEAD / HTTP/1.1
> Host: rgups.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Server: nginx/1.19.1
Server: nginx/1.19.1
< Date: Thu, 12 Oct 2023 17:09:24 GMT
Date: Thu, 12 Oct 2023 17:09:24 GMT
< Content-Type: text/html; charset=utf-8
Content-Type: text/html; charset=utf-8
< Connection: keep-alive
Connection: keep-alive
< X-Powered-By: ProcessWire CMS
X-Powered-By: ProcessWire CMS
< Set-Cookie: wire=8a534ee2534584b59ade30300ffe38ed; path=/; HttpOnly; SameSite=Lax
Set-Cookie: wire=8a534ee2534584b59ade30300ffe38ed; path=/; HttpOnly; SameSite=Lax
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate
Cache-Control: no-store, no-cache, must-revalidate
< Pragma: no-cache
Pragma: no-cache

<
* Connection #1 to host rgups.ru left intact
```

#### РЖД


```shell
*   Trying 212.164.138.124:80...
* Connected to rzd.ru (212.164.138.124) port 80 (#0)
> HEAD / HTTP/1.1
> Host: rzd.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
HTTP/1.1 301 Moved Permanently
< Date: Thu, 12 Oct 2023 17:11:02 GMT
Date: Thu, 12 Oct 2023 17:11:02 GMT
< Content-Type: text/html
Content-Type: text/html
< Content-Length: 150
Content-Length: 150
< Connection: keep-alive
Connection: keep-alive
< Location: https://rzd.ru:443/
Location: https://rzd.ru:443/

<
* Connection #0 to host rzd.ru left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://rzd.ru:443/'
*   Trying 212.164.138.124:443...
* Connected to rzd.ru (212.164.138.124) port 443 (#1)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server accepted http/1.1
* using HTTP/1.1
> HEAD / HTTP/1.1
> Host: rzd.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
* schannel: server closed the connection
< HTTP/1.1 403 Forbidden
HTTP/1.1 403 Forbidden
< Connection: close
Connection: close
< Content-Length: 109
Content-Length: 109
< Content-Type: text/html
Content-Type: text/html

<
* Excess found: excess = 109 url = / (zero-length body)
* Closing connection 1
* schannel: shutting down SSL/TLS connection with rzd.ru port 443
```

#### Python


```shell
*   Trying 151.101.192.223:80...
* Connected to python.org (151.101.192.223) port 80 (#0)
> HEAD / HTTP/1.1
> Host: python.org
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
HTTP/1.1 301 Moved Permanently
< Connection: close
Connection: close
< Content-Length: 0
Content-Length: 0
< Server: Varnish
Server: Varnish
< Retry-After: 0
Retry-After: 0
< Accept-Ranges: bytes
Accept-Ranges: bytes
< Date: Thu, 12 Oct 2023 17:15:52 GMT
Date: Thu, 12 Oct 2023 17:15:52 GMT
< Via: 1.1 varnish
Via: 1.1 varnish
< X-Served-By: cache-fra-eddf8230035-FRA
X-Served-By: cache-fra-eddf8230035-FRA
< X-Cache: HIT
X-Cache: HIT
< X-Cache-Hits: 0
X-Cache-Hits: 0
< X-Timer: S1695968816.908715,VS0,VE0
X-Timer: S1695968816.908715,VS0,VE0
< Location: https://www.python.org/
Location: https://www.python.org/
< Strict-Transport-Security: max-age=315360000; preload
Strict-Transport-Security: max-age=315360000; preload

<
* Closing connection 0
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://www.python.org/'
*   Trying 146.75.52.223:443...
* Connected to www.python.org (146.75.52.223) port 443 (#1)
* schannel: disabled automatic use of client certificate
* ALPN: offers http/1.1
* ALPN: server accepted http/1.1
* using HTTP/1.1
> HEAD / HTTP/1.1
> Host: www.python.org
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
HTTP/1.1 200 OK
< Connection: keep-alive
Connection: keep-alive
< Content-Length: 50116
Content-Length: 50116
< Server: nginx
Server: nginx
< Content-Type: text/html; charset=utf-8
Content-Type: text/html; charset=utf-8
< X-Frame-Options: SAMEORIGIN
X-Frame-Options: SAMEORIGIN
< Via: 1.1 vegur, 1.1 varnish, 1.1 varnish
Via: 1.1 vegur, 1.1 varnish, 1.1 varnish
< Accept-Ranges: bytes
Accept-Ranges: bytes
< Date: Thu, 12 Oct 2023 17:15:56 GMT
Date: Thu, 12 Oct 2023 17:15:56 GMT
< Age: 1374
Age: 1374
< X-Served-By: cache-iad-kiad7000025-IAD, cache-lin2290029-LIN
X-Served-By: cache-iad-kiad7000025-IAD, cache-lin2290029-LIN
< X-Cache: HIT, HIT
X-Cache: HIT, HIT
< X-Cache-Hits: 3, 5
X-Cache-Hits: 3, 5
< X-Timer: S1695968817.775739,VS0,VE0
X-Timer: S1695968817.775739,VS0,VE0
< Vary: Cookie
Vary: Cookie
< Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```