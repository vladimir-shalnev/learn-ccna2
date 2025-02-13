<!-- 15.6.3 -->
## Статические маршруты

Статические маршруты можно настроить для IPv4 и IPv6. Оба протокола поддерживают следующие типы статических маршрутов: стандартный, по умолчанию, плавающий и суммарный. Статические маршруты настраиваются с помощью команды глобальной конфигурации **ip route**.

При настройке статического маршрута следующий переход может быть идентифицирован по IP-адресу, интерфейсу выхода или использовать оба варианта. При указании места назначения создается один из трех следующих типов статических маршрутов: следующий переход, непосредственно связанный и полностью указанный.

Статические маршруты IPv4 настраиваются с помощью следующей команды глобальной конфигурации **ip route** _network-address subnet-mask_ {_ip-address_ | _exit-intf_ [_ip=address_]} [**distance**]. Статические маршруты IPv6 настраиваются с помощью следующей команды глобальной конфигурации **ipv6 route** _ipv6-prefix/prefix-length_ {_ipv6-address_ | _exit-intf_ [_ipv6-address_]} [**distance**]. 

Для просмотра таблицы маршрутизации IPv4 используется команда **show ip route** | **begin Gateway**. Для просмотра таблицы маршрутизации IPv6 используется команда **show ipv6 route** | **begin C**.

## Настройка статических маршрутов для пересылки IP-пакетов

В статическом маршруте следующего перехода указывается только IP-адрес следующего перехода. Выходной интерфейс определяется исходя из следующего транзитного участка. При настройке статического маршрута также можно использовать выходной интерфейс для настройки адреса следующего перехода. Непосредственно подключенные статические маршруты следует использовать только с последовательными интерфейсами «точка-точка».

В полностью заданном статическом маршруте указываются как выходной интерфейс, так и IP-адрес следующего перехода. Он используется в случаях, когда выходной интерфейс представляет собой интерфейс множественного доступа и необходимо явно определить следующий переход. Он должен быть напрямую подключен к указанному выходному интерфейсу.

В полностью заданном статическом маршруте указываются как выходной интерфейс, так и IPv6-адрес следующего перехода. Наряду с командами **show ip route**, **show ipv6 route**, **ping** и **traceroute**, другие полезные команды для проверки статических маршрутов включают в себя **show ip route static**, **show ip route** _network_ и **show running-config | section ip route**. Замените ip на ipv6 для версий команды IPv6.

## Настройка статических маршрутов для пересылки IP-пакетов по умолчанию

**Статический маршрут по умолчанию** — это маршрут, которому соответствуют все пакеты. Он не требует совпадения никаких самых левых битов между маршрутом по умолчанию и IP адресом назначения. Такие маршруты обычно используются при подключении пограничного роутер к сети поставщика услуг Интернет.

## Настройка плавающих статических маршрутов

**Плавающие статические маршруты** — это маршруты, используемые для предоставления резервного пути основному статическому или динамическому маршруту на случай сбоя в работе канала. Для этой цели плавающий статический маршрут настраивается с более высоким значением административного расстояния, чем основной. 

По умолчанию статические маршруты имеют значение административного расстояния, равное 1, поэтому они имеют приоритет перед маршрутами, полученными от протоколов динамической маршрутизации. Административные расстояния некоторых общих протоколов динамической маршрутизации внутренних шлюзов являются EIGRP = 90, OSPF = 110 и IS-IS = 115. 

Плавающие статические маршруты IP настраиваются с помощью аргумента **distance** для указания административного расстояния. Если это значение не задано, используется значение по умолчанию (1). Команды **show ip route** и **show ipv6 route** показывает, что маршрут по умолчанию к роутеру записан в таблицу маршрутизации.

## Настройка статических маршрутов хостов

Маршрут хоста представляет собой адрес IPv4 с 32-разрядной маской или адрес IPv6 с 128-разрядной маской. Существует три способа добавления маршрута узла в таблицу маршрутизации: автоматически устанавливается, когда IP-адрес настроен на роутере, настроен как статический маршрут узла, или автоматически получается с помощью других методов, не охваченных этим модулем.

Cisco IOS автоматически устанавливает маршрут узла, также известный как локальный, при настройке адреса интерфейса на роутере. Маршрут хоста может быть настроенным вручную статическим маршрутом для направления трафика на определенное целевое устройство, такое как сервер, показанный на рисунке. Для статических маршрутов IPv6-адрес следующего перехода может быть локальным адресом связи соседнего роутера.

Однако при использовании локального адреса канала в качестве следующего перехода необходимо указать тип и номер интерфейса. Для этого исходный маршрут статического узла IPv6 удаляется, а затем полностью указанный маршрут настраивается с адресом IPv6 сервера и локальным адресом канала IPv6 роутера ISP.

<!-- 15.6.4 -->
<!-- quiz -->
