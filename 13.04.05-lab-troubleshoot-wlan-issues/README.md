## Топология

![](./assets/topology.png)

## Таблица адресации

| Устройство                          | Интерфейс       | IP-адрес           |
|-------------------------------------|-----------------|--------------------|
| Домашний беспроводной маршрутизатор | Интернет        | DHCP               |
| Домашний беспроводной маршрутизатор | LAN             | 192.168.0.1        |
| R1                                  | G0/0/0.10       | 192.168.10.1/24    |
| R1                                  | G0/0/0.20       | 192.168.20.1/24    |
| R1                                  | G0/0/0.200      | 192.168.200.1/24   |
| R1                                  | G0/0/1          | 172.31.1.1/24      |
| SW1                                 | VLAN 200        | 192.168.200.100/24 |
| LAP-1                               | G0              | DHCP               |
| WLC-1                               | Управление      | 192.168.200.254/24 |
| Сервер RADIUS                       | NIC             | 172.31.1.254/24    |
| ПК администратора                   | NIC             | 192.168.200.200/24 |
| Веб-сервер                          | NIC             | 203.0.113.78/24    |
| DNS Server                          | NIC             | 10.100.100.254     |
| Home Admin                          | NIC             | DHCP               |
| Ноутбук                             | Сетевой адаптер | DHCP               |
| Laptop1                             | Wireless0       | DHCP               |
| Laptop2                             | Wireless0       | DHCP               |
| мини-компьютеры;                    | Wireless0       | DHCP               |
| Смартфон                            | Wireless0       | DHCP               |

## Информация о сети WLAN

| WLAN          | SSID     | Аутентификация          | Имя пользователя | Пароль    |
|---------------|----------|-------------------------|------------------|-----------|
| Домашняя сеть | HomeSSID | WPA2-Personal           | Не применимо     | Cisco123  |
| WLAN VLAN10   | SSID-10  | WPA-2 PSK/Personal      | Не применимо     | Cisco123  |
| WLAN VLAN 20  | SSID-20  | WPA-2 802.1x/Enterprise | user2            | user2Pass |

## Цели

В этом упражнении вы будете устранять различные проблемы в домашних беспроводных и корпоративных беспроводных сетях.

-   Устранение неполадок с подключением беспроводной локальной сети в домашней сети.

-   Устранение неполадок с подключением к беспроводной локальной сети в сети предприятия.

## Общие сведения и сценарий

Теперь, когда вы узнали, как настроить беспроводную связь в домашних и корпоративных сетях, вам нужно научиться устранять неполадки в беспроводных средах. Ваша цель - включить соединение между хостами в сетях с веб-сервером по IP-адресу и URL-адресу. Связь между домашней и корпоративной сетями не требуется.

Для доступа к беспроводному маршрутизатору используйте имя пользователя **admin**. и пароль admin.

Управление WLC имя пользователя **admin** с паролем **Cisco123**.

## Инструкции

### Часть 1. Поиск и устранение неполадок в работе сети

**Примечание**: В этом упражнении вы будете только устранять неполадки домашнего беспроводного маршрутизатора, WLC и беспроводных хост-устройств.

**Шаг 1. проверка связи.**

1.  Проверьте соединение между различными беспроводными хостами и веб-сервером по IP и URL **www.netacad.pt**.

2.  Запишите хосты, которые не могут получить доступ к веб-серверу, в таблице в шаге 2.

**Шаг 2. Исследуйте проблемы и запишите результаты.**

1.  Изучите проблемы с подключением к каждому хосту. Проблемы могут быть с конфигурацией хоста или с другими компонентами беспроводной сети.

2.  Заполните следующую таблицу.

| Устройство | Сеть<br>Home/Enterprise | Проблема | Решение |
|---|---|---|---|
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |
| &nbsp; |  |  |  |

### Часть 2. Исправить проблемы

Внесите изменения в конфигурации устройства, чтобы узлы могли подключиться к сети. Проверьте, чтобы все хосты могли достичь цели соединения при подключении к веб-серверу как по IP-адресу, так и по URL-адресу.

[Скачать файл Packet Tracer для локального запуска](./assets/13.4.5-packet-tracer---troubleshoot-wlan-issues_ru-RU.pka)