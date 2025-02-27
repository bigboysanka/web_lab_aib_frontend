# Инструменты разработчика в браузере

## Отчет по Лаб. №2
## ст. Обуваев А.С.
## гр. АСБ-3-036



### Задание №1. Исследование заголовков и тела обычных запросов и их ответов.

    - Request URL        - это адрес ресурса, на который отправляется HTTP-запрос.
    - Request Method     - это тип HTTP-запроса, такой как GET, POST, PUT, DELETE и другие, используемый для взаимодействия с ресурсом.
    - Status Code        - это трехзначный числовой код, возвращаемый сервером в ответ на HTTP-запрос, чтобы указать состояние выполнения запроса.
    Например, код 200 означает успешный запрос, а код 404 означает, что ресурс не найден.
    - Remote Address     - это IP-адрес сервера или компьютера, с которого отправляется HTTP-запрос.
    - Referrer Policy    - это политика, которая определяет, как браузер должен отправлять информацию об источнике запроса (URL предыдущей
    страницы) при переходе по ссылке или отправке формы.
    - content-type       - это заголовок HTTP-ответа или запроса, который указывает тип данных содержимого (например, текст/html, application
    json, image/jpeg и т. д.).
    - cache-control     - это заголовок HTTP, который определяет, как браузер или прокси-сервер должны кэшировать и обрабатывать содержимое.
    - cookie             - это небольшой фрагмент данных, отправляемый сервером и хранящийся в браузере пользователя. Куки используются для
    отслеживания состояния сеанса и для хранения информации о пользователе.
    - user-agent         - это заголовок HTTP-запроса, который содержит информацию о браузере, операционной системе и других свойствах клиента,
    отправляющего запрос.
    - referer           - это заголовок HTTP-запроса, который содержит URL предыдущей страницы, с которой был сделан переход или отправлен запрос.

#### Ответьте на вопросы:

1. Каждый из этих заголовков содержит информацию о получаемом ресурсе или о клиенте.
2. Remote Address (Удаленный адрес) состоит из двух частей: IP-адреса и порта. IP-адрес идентифицирует устройство или компьютер, с которого
    отправляется запрос или на которое направляется ответ. Порт указывает на конкретное приложение или службу на удаленном устройстве, которое
    обрабатывает соединение.

3. Порт подключения - это числовой идентификатор, который определяет конкретное приложение или службу, к которой происходит подключение на
    удаленном устройстве. В контексте сетевых соединений, порт позволяет множеству приложений на одном устройстве обрабатывать входящие и исходящие
    сетевые пакеты. Каждое приложение использует свой уникальный порт для обмена данными через сеть. Например, HTTP-сервер может прослушивать на
    порту
    80, а FTP-сервер - на порту 21.

4. Заголовки HTTP-запроса и ответа обычно разделены на следующие секции:

    - General (Общие) - содержит общую информацию о запросе или ответе, такую как версия протокола и цель запроса.
    - Request Headers (Заголовки запроса) - содержит дополнительную информацию о запросе, такую как User-Agent, Accept-Language и другие
    заголовки, которые передаются серверу.
    - Response Headers (Заголовки ответа) - содержит дополнительную информацию о ответе, такую как Content-Type, Cache-Control и другие заголовки,
    которые сервер отправляет вместе с ответом.
    - Entity Headers (Заголовки сущности) - содержит информацию о теле запроса или ответа, такую как Content-Length, Content-Encoding и другие
    заголовки, связанные с содержимым.

    Каждая секция имеет свою роль в передаче данных и управлении соединением между клиентом и сервером.

5. Некоторые заголовки могут повторяться в разных секциях. Например, заголовок "Content-Type" может быть присутствовать и в Request Headers
(Заголовках запроса), и в Response Headers (Заголовках ответа). Это связано с тем, что клиент отправляет информацию о типе содержимого, который он
ожидает от сервера (в Request Headers), а сервер отвечает с информацией о типе содержимого, который он отправляет клиенту (в Response Headers).

6. Тело ответа (Response Body) - это часть HTTP-ответа, которая содержит фактическое содержимое или данные, возвращаемые сервером. Например, если
вы запрашиваете веб-страницу, то тело ответа будет содержать HTML-код страницы. Тело ответа может содержать различные типы данных, такие как
текст, изображения, видео, JSON и другие.

### Задание №2. Исследование указывающих ответов сервера.

    Адрес изменился с http://rgups.ru/ на https://rgups.ru/

1. Из-за чего произошло изменение адреса в адресной строке? Какие заголовки в этом поучаствовали и как?
    Это произошло из за того что сервер вернул статус ответа 301,что ознаечает что ресурс был перемещён в другой URL.


2. Адрес был изменён в исходном запросе или потребовались дополнительные запросы, если были дополнительные запросы, то сколько?
    В первом запросе было запрошено повышение страницы, во втором запросе мы перешли на полученную страницу.

3. Какой статус ответа имеет первоначальный запрос?
    301 Moved Permanently


### Задание №3. Исследование получения и передачи cookie.
    Повторите запрос на https://ya.ru/ и изучите заголовки влияющие на получение и отправку **cookie** параметров.

#### После чего:
1. Перечислите название этих параметров и формат данных в них.
    Name(user_id),
    Value(12345 или JohnDoe),
    Expires/Max-Age(Sat, 01 Jan 2023 00:00:00 GMT или в сек. 3600 для 1-го часа),
    Domain(rgups.ru),
    Path(/products),
    Secure(защищенное HTTPS-соединение),
    HTTP Only(доступен только через HTTP-запросы и недоступен JavaScript),
    SameSite(кросс-сайтовые запросы: Strict, Lax, None),
    Partition Key(строка, число или другой тип данных, в зависимости от конкретной базы данных или системы хранения данных),
    Priority(числовое значение или уровень приоритета(Пример: 7 или Medium)).

2. Как можно удобно просмотреть все cookie, используемые на странице? Что означают их параметры Name, Value, Domain, Path и Expires?
    1. Открыть необходимый веб-сайт.
    2. Открыть панель разработчика (клавиша F12).
    3. Открыть вкладку Application.
    4. В левой панели открыть вкладку Cookies в разделе Storage.

3. Как просмотреть все cookie связанные с текущим (просматриваемым) сайтом?
    1. Открыть необходимый веб-сайт.
    2. Открыть панель разработчика (клавиша F12).
    3. Перейти во вкладку Application.
    4. В левой панели выберите Cookies в разделе Storage.
    5. У каждой cookie есть свой Domain:

4. Опишите своими словами как вы понимаете суть и назначение cookie?
    Cookie - это набор данных, отправляемые сервером и хранящиеся на устройстве пользователя. Куки используются для отслеживания состояния сеанса
    и для хранения информации о пользователе. Они позволяют веб-сайтам запоминать предпочтения и данные пользователя, такие как логин, языковые
    настройки, корзина покупок и другие. 

### Задание №4. Исследование построения документов и сопутствующих запросов.
Изучите вкладку Elements и дерево тегов документа. Изучите список запросов на вкладке Network.

#### Ответьте на вопросы:
1. Что такое DOM? — Опишите своими словами
     DOM-это структура, которая представляет веб-страницу в виде дерева объектов. Она позволяет манипулировать содержимым страницы, изменять ее
    внешний вид и поведение. DOM позволяет получать доступ к элементам страницы, изменять их свойства и атрибуты, добавлять новые элементы и
    удалять существующие.

2. Может ли итоговый документ отличаться от тела ответа, полученного от сервера? Если да, то по каким причинам это может происходить?
    Да, итоговый документ может отличаться от тела ответа, полученного от сервера. Это может происходить по нескольким причинам:

    1. JavaScript: Если на странице есть JavaScript-код, то он может изменять содержимое страницы после загрузки. Например, скрипт может добавлять
    новые элементы на страницу или изменять текст уже существующих элементов.

    2. CSS: CSS-стили могут изменять внешний вид элементов на странице. Например, стиль может изменять цвет фона или шрифт текста.

    3. AJAX: Технология AJAX позволяет загружать данные асинхронно, без перезагрузки всей страницы. Это означает, что часть содержимого страницы
    может быть загружена после того, как основная часть страницы уже была загружена.

    4. Серверные скрипты: Серверные скрипты могут генерировать содержимое страницы динамически в зависимости от запроса пользователя. Например,
    если пользователь запрашивает список товаров на сайте, серверный скрипт может генерировать HTML-код для этого списка на основе данных из базы
    данных.

    Все эти факторы могут привести к тому, что итоговый документ будет отличаться от тела ответа, полученного от сервера.

3. Почему если вы сделали всего один запрос, в списке огромное количество запросов и ответов? Что они из себя представляют и на каком основании
браузер их делает?
    Это связано с тем, что на странице загружается множество ресурсов, таких как изображения, стили, скрипты и т.д. Браузер делает эти
    запросы автоматически для загрузки всех необходимых ресурсов, которые нужны для отображения страницы.

### Задание №5. Определение параметров запроса.
Откройте главный сайт университета https://www.rgups.ru/services/time/. Используя инструменты разработчика вкладку Network определить запрос и
параметры запроса позволяющие получить ваше расписание.

#### Ответьте на вопросы:
1. Запрос к какому эндпоинту необходимо выполнить для получения вашего расписания
    https://www.rgups.ru/ajax/schedule.php?action=timetable&fac-id=1&course-id=3&group-id=26365&edu-type=internal

2. Что содержится в теле ответа


    <div class="schedule-section">
                        <div class="schedule-section-legend"><i></i> – в режиме видеоконференцсвязи</div>
                
        <table class="table">             <tr>
                    <th class="" colspan="6">
                        Понедельник                </th>
                </tr>
                        <tr>
                            <td class="" >1</td>
                            <td class="" >8.20-9.50</td>
                            <td class="" >обе недели</td>
                                <td class="">Военная подготовка ()</td>
                                <td class=""> ..</td>
                                <td class=""></td>
                        </tr>
                        <tr>
                            <td class="" >2</td>
                            <td class="" >10.05-11.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Военная подготовка ()</td>
                                <td class=""> ..</td>
                                <td class=""></td>
                        </tr>
                        <tr>
                            <td class="" >3</td>
                            <td class="" >12.05-13.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Военная подготовка ()</td>
                                <td class=""> ..</td>
                                <td class=""></td>
                        </tr>
                        <tr>
                            <td class="" >4</td>
                            <td class="" >13.50-15.20</td>
                            <td class="" >обе недели</td>
                                <td class="">Военная подготовка ()</td>
                                <td class=""> ..</td>
                                <td class=""></td>
                        </tr>
                        <tr>
                            <td class="" >5</td>
                            <td class="" >15.30-17.00</td>
                            <td class="" >обе недели</td>
                                <td class="">Военная подготовка ()</td>
                                <td class=""> ..</td>
                                <td class=""></td>
                        </tr>

                <tr>
                    <th class="" colspan="6">
                        Вторник                </th>
                </tr>
                        <tr>
                            <td class="" >2</td>
                            <td class="" >10.05-11.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Системы и технологии искусственного интеллекта (ЛЕК)</td>
                                <td class="">МОСКАТ Н.А.</td>
                                <td class="">Д404</td>
                        </tr>
                        <tr>
                            <td class="" >3</td>
                            <td class="" >12.05-13.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Экономика и менеджмент (ПРАК)</td>
                                <td class="">ТИМЧЕНКО О.В.</td>
                                <td class="">С409</td>
                        </tr>
                        <tr>
                            <td class="" >4</td>
                            <td class="" >13.50-15.20</td>
                            <td class="" >обе недели</td>
                                <td class="">Схемотехника и архитектура вычислительных систем (ЛЕК)</td>
                                <td class="">ЛЯЩЕНКО А.М.</td>
                                <td class="">Г313</td>
                        </tr>
                        <tr>
                            <td class="" >5</td>
                            <td class="" >15.30-17.00</td>
                            <td class="" >обе недели</td>
                                <td class="">Системы и технологии искусственного интеллекта (ЛАБ)</td>
                                <td class="">ЖУРАВЛЕВ Д.С. [2]</td>
                                <td class="">Г305</td>
                        </tr>

                <tr>
                    <th class=" info" colspan="6">
                        Среда (сегодня)                </th>
                </tr>
                        <tr>
                            <td class="" >2</td>
                            <td class="" >10.05-11.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Системы и технологии искусственного интеллекта (ЛАБ)</td>
                                <td class="">МОСКАТ Н.А. [1]</td>
                                <td class="">Г305</td>
                        </tr>
    <!--4-->                      <tr>
                            <td class="success" rowspan="4">3</td>
                            <td class="success" rowspan="4">12.05-13.35</td>
                            <td class="disable success" >над чертой</td>
                                    
                                    <td class="disable success">Безопасность жизнедеятельности (ЛЕК)</td>
                                    <td class="disable success">ПЕРЕВЕРЗЕВ И.Г.</td>
                                    <td class="disable success">М150</td>
                            </tr>
                            <tr>
                                <td class=" success" rowspan="3">под чертой</td>
                                    <td class=" success">Безопасность жизнедеятельности (ЛАБ)</td>
                                    <td class=" success">ЯИЦКОВА Н.М. [1]</td>
                                    <td class=" success">М152</td>
    </tr><tr>                                <td class=" success">Безопасность жизнедеятельности (ЛАБ)</td>
                                    <td class=" success">АБДУЛЬМАНОВА К.И. [2]</td>
                                    <td class=" success">М158</td>
    </tr><tr>                          </tr>
                                        </tr>
                        <tr>
                            <td class="" >4</td>
                            <td class="" >13.50-15.20</td>
                            <td class="" >обе недели</td>
                                <td class="">Веб-программирование (ЛЕК)</td>
                                <td class="">КАПКАЕВ А.А.</td>
                                <td class="">Г315</td>
                        </tr>
    <!--5-->                      <tr>
                            <td class="" rowspan="5">5</td>
                            <td class="" rowspan="5">15.30-17.00</td>
                            <td class="disable " rowspan="3">над чертой</td>
                                    
                                    <td class="disable ">Веб-программирование (ЛАБ)</td>
                                    <td class="disable ">ХУСАИНОВ В.Р. [2]</td>
                                    <td class="disable ">Д412</td>
    </tr><tr>                                  
                                    <td class="disable ">Веб-программирование (ЛАБ)</td>
                                    <td class="disable ">КАПКАЕВ А.А. [1]</td>
                                    <td class="disable ">Г302</td>
    </tr><tr>                        </tr>
                            <tr>
                                <td class=" " rowspan="3">под чертой</td>
                                    <td class=" ">Веб-программирование (ЛАБ)</td>
                                    <td class=" ">ХУСАИНОВ В.Р. [2]</td>
                                    <td class=" ">Д406</td>
    </tr><tr>                                <td class=" ">Веб-программирование (ЛАБ)</td>
                                    <td class=" ">КАПКАЕВ А.А. [1]</td>
                                    <td class=" ">Г302</td>
    </tr><tr>                          </tr>
                                        </tr>
                        <tr>
                            <td class="" rowspan="2">6</td>
                            <td class="" rowspan="2">17.10-18.40</td>
                            <td class="" rowspan="2">обе недели</td>
                                <td class="">Системное программное обеспечение вычислительных систем (ЛАБ)</td>
                                <td class="">НИКИТЧЕНКО С.Л. [2]</td>
                                <td class="">Д406</td>
    </tr><tr>                            <td class="">Системное программное обеспечение вычислительных систем (ЛАБ)</td>
                                <td class="">МИЗЮКОВ Г.С. [1]</td>
                                <td class="">Д407</td>
    </tr><tr>                    </tr>

                <tr>
                    <th class="" colspan="6">
                        Четверг (завтра)                </th>
                </tr>
    <!--4-->                      <tr>
                            <td class="" rowspan="4">1</td>
                            <td class="" rowspan="4">8.20-9.50</td>
                            <td class="disable " rowspan="3">над чертой</td>
                                    
                                    <td class="disable ">Схемотехника и архитектура вычислительных систем (ЛАБ)</td>
                                    <td class="disable ">МИРОШНИКОВ А.М. [1]</td>
                                    <td class="disable ">Г303</td>
    </tr><tr>                                  
                                    <td class="disable ">Схемотехника и архитектура вычислительных систем (ЛАБ)</td>
                                    <td class="disable ">СОКИРКА А.Д. [2]</td>
                                    <td class="disable ">Г302</td>
    </tr><tr>                        </tr>
                            <tr>
                                <td class=" " >под чертой</td>
                                    <td class=" ">Безопасность жизнедеятельности (ПРАК)</td>
                                    <td class=" ">БАЛАНОВА М.В.</td>
                                    <td class=" ">М232</td>
                            </tr>
                                        </tr>
                        <tr>
                            <td class="" >2</td>
                            <td class="" >10.05-11.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Базы данных (ЛЕК)</td>
                                <td class="">ИГНАТЬЕВА О.В.</td>
                                <td class="">Г313</td>
                        </tr>
                        <tr>
                            <td class="" rowspan="2">3</td>
                            <td class="" rowspan="2">12.05-13.35</td>
                            <td class="" rowspan="2">обе недели</td>
                                <td class="">Базы данных (ЛАБ)</td>
                                <td class="">ГАЛЬЦЕВА А.А. [1]</td>
                                <td class="">Г315</td>
    </tr><tr>                            <td class="">Базы данных (ЛАБ)</td>
                                <td class="">МУКОНИНА М.И. [2]</td>
                                <td class="">Г315</td>
    </tr><tr>                    </tr>

                <tr>
                    <th class="" colspan="6">
                        Пятница                </th>
                </tr>
                        <tr>
                            <td class="" >2</td>
                            <td class="" >10.05-11.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Экономика и менеджмент (ЛЕК)</td>
                                <td class="">КАЛАШНИКОВ И.А.</td>
                                <td class="">Д404</td>
                        </tr>
                        <tr>
                            <td class="" >3</td>
                            <td class="" >12.05-13.35</td>
                            <td class="" >обе недели</td>
                                <td class="">Системное программное обеспечение вычислительных систем (ЛЕК)</td>
                                <td class="">ЖУКОВ В.В.</td>
                                <td class="">Д404</td>
                        </tr>

    </table></div>

3. Какого типа запрос вы выполнили?
    GET
4. Какие данные вы использовали для получения расписания
    action: timetable - Обращение к расписанию
    fac-id: 1 - id факультета
    course-id: 3 # - id курса
    group-id: 26365 - id группы
    edu-type: internal - тип обучения
