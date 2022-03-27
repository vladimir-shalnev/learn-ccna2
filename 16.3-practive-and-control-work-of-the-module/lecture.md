# Практика и контрольная работа модуля

<!-- 16.3.1 -->
## Packet Tracer - Поиск и устранение неполадок, связанных со статическими маршрутами и маршрутами по умолчанию
В этом упражнении вы будете устранять неисправности, настраивать статические и стандартные маршруты и исправлять любые найденные ошибки.

- Поиск и устранение неполадок в статических маршрутах IPv4.
- Поиск и устранение неполадок в статических маршрутах IPv6.
- Настройка статических маршрутов IPv4 для пересылки IP-пакетов
- Настройка статических маршрутов IPv4 для пересылки IP-пакетов
- Настройка статических маршрутов IPv6 для пересылки IP-пакетов

[Открыть описание в PDF](./assets/16.3.1-packet-tracer---troubleshoot-static-and-default-routes_ru-RU.pdf)

[Скачать файл для Packet Tracer](./assets/16.3.1-packet-tracer---troubleshoot-static-and-default-routes_ru-RU.pka)

<!-- 16.3.2 -->
## Лабораторная работа - Поиск и устранение неполадок, связанных со статическими маршрутами и маршрутами по умолчанию
В этой лабораторной работе вы выполните следующие задачи.

- Оценка работы сети
- Сбор информации, создание плана действий и внесение исправлений

**Устранение неполадок статических маршрутов IPv4 и IPv6 и маршрутов по умолчанию - режим симуляции физического оборудования**

[Открыть описание в PDF](./assets/16.3.2-packet-tracer---troubleshoot-ipv4-and-ipv6-static-and-default-routes---physical-mode_ru-RU.pdf)

[Скачать файл для Packet Tracer](./assets/16.3.2-packet-tracer---troubleshoot-ipv4-and-ipv6-static-and-default-routes---physical-mode_ru-RU.pka)

**Поиск и устранение неполадок, связанных со статическими маршрутами и маршрутами по умолчанию**

[Открыть описание в PDF](./assets/16.3.2-lab---troubleshoot-ipv4-and-ipv6-static-and-default-routes_ru-RU.pdf)

<!-- 16.3.3 -->
## Что я изучил в этом модуле?
**Обработка пакетов с использованием статических маршрутов**

1. Пакет приходит на интерфейс маршрутизатора R1.
2. У маршрутизатора R1 нет определенного маршрута к сети назначения; таким образом, R1 использует статический маршрут по умолчанию.
3. Маршрутизатор R1 инкапсулирует пакет в новый кадр. Поскольку канал к маршрутизатору R2 является каналом типа «точка-точка», R1 добавляет адрес типа «все единицы» в адрес назначения второго уровня.
4. Кадр пересылается из соответствующего интерфейса. Пакет приходит на интерфейс маршрутизатора R2.
5. Маршрутизатор R2 деинкапсулирует кадр и выполняет поиск маршрута к адресату. R2 имеет статический маршрут к сети назначения из одного из своих интерфейсов.
6. Маршрутизатор R2 инкапсулирует пакет в новый кадр. Поскольку канал к маршрутизатору R3 является каналом типа «точка-точка», R2 добавляет адрес типа «все единицы» в адрес назначения второго уровня.
7. Кадр пересылается из соответствующего интерфейса. Пакет приходит на интерфейс маршрутизатора R3.
8. Маршрутизатор R3 деинкапсулирует кадр и выполняет поиск маршрута к адресату. R3 имеет подключенный маршрут к сети назначения из одного из своих интерфейсов.
9. R3 ищет запись таблицы ARP для сети назначения, чтобы найти MAC-адрес уровня 2 для PC3. Если запись отсутствует, R3 отправляет запрос ARP с одного из своих интерфейсов, а PC3 посылает ARP-ответ, который включает MAC-адрес PC3.
10. R3 инкапсулирует пакет в новый кадр с MAC-адресом соответствующего интерфейса в качестве адреса уровня 2 источника и MAC-адресом PC3 в качестве MAC-адреса назначения.
11. Кадр пересылается из соответствующего интерфейса. Пакет поступает на интерфейс сетевого адаптера (NIC) компьютера PC3.

**Поиск и устранение проблем с конфигурацией статических маршрутов IPv4 и маршрутов IPv4 по умолчанию**

Существуют факторы воздействия на сети, которые могут вызвать изменение их статуса, Может произойти сбой интерфейса или интернет провайдер обрывает соединение. Каналы могут быть перегружены или администратор может ввести неправильную конфигурацию. Часто используемые команды ОС IOS для поиска и устранения неполадок:
- ping
- traceroute
- show ip route
- show ip interface brief
- show cdp neighbors detail

<!-- 16.3.4
Контрольная работа модуля - Поиск и устранение неполадок, связанных со статическими маршрутами и маршрутами по умолчанию -->