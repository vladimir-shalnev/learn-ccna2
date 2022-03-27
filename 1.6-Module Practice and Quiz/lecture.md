<!-- 1.6.1 -->
## Packet Tracer - Реализация небольшой сети

В этом задании Packet Tracer маршрутизаторы R1 и R2 имеют две локальные сети. Ваша задача — настроить соответствующую адресацию на каждом устройстве и проверить подключение между локальными сетями.

[Реализация небольшой сети - PDF](./assets/1.6.1-packet-tracer---implement-a-small-network_ru-RU.pdf)

[Реализация небольшой сети - PKA](./assets/1.6.1-packet-tracer---implement-a-small-network_ru-RU.pka)

<!-- 1.6.2 -->
## Лабораторная работа - настройка основных параметров маршрутизатора

Это комплексная лабораторная работа, нацеленная на повторение ранее изученных команд IOS для маршрутизатора. В первой и второй частях вам предстоит подключить кабели к оборудованию и выполнить базовую настройку конфигураций и параметров IPv4-интерфейса на маршрутизаторе. В третьей части вам нужно будет настроить удаленное подключение к маршрутизатору с помощью протокола SSH, а также использовать команды IOS для получения от устройства данных, необходимых для того, чтобы ответить на вопросы о маршрутизаторе.

[Настройка основных параметров маршрутизатора - PDF](./assets/1.6.2-packet-tracer----configure-basic-router-settings---physical-mode_ru-RU.pdf)

[Настройка основных параметров маршрутизатора - PKA](./assets/1.6.2-packet-tracer----configure-basic-router-settings---physical-mode_ru-RU.pka)

**Лабораторное оборудование**

[Настройка основных параметров маршрутизатора - PDF](./assets/1.6.2-lab---configure-basic-router-settings_ru-RU.pdf)

<!-- 1.6.3 -->
## Что я изучил в этом модуле?

**Первоначальная настройка коммутатора**

После включения коммутатор Cisco проходит следующие стадии загрузки: Переменная среды BOOT устанавливается с помощью команды режима глобальной конфигурации **boot system**. IOS находится в отдельной папке и указан путь к папке. Индикаторы коммутатора и его портов служат для контроля его работы и характеристик. Загрузчик предоставляет доступ к коммутатору, если операционная система не может быть использована из-за отсутствия или повреждения системных файлов. Загрузчик имеет командную строку, которая обеспечивает доступ к файлам, хранящимся во флэш-памяти. Чтобы подготовить коммутатор для доступа к удаленному управлению, он должен быть настроен с IP-адресом и маской подсети. Имейте в виду, что для управления коммутатором из удаленной сети на коммутаторе должен быть настроен на шлюз по умолчанию. Чтобы настроить коммутатор SVI, необходимо сначала настроить интерфейс управления, затем настроить шлюз по умолчанию и, наконец, проверить конфигурацию.

**Найстройка портов коммутатора**

Полнодуплексная связь повышает эффективность использования полосы пропускания, позволяя обоим сторонам канала одновременно передавать и принимать данные. Полудуплексная связь однонаправленная. Порты коммутатора можно настроить вручную с помощью определенных параметров дуплекса и скорости. Используйте автосогласование, если параметры скорости и дуплексного режима устройства, подключенного к порту, неизвестны или могут измениться. Интерфейс с функцией auto-MDIX автоматически определяет требуемый тип кабельного соединения (прямой или перекрестный) и соответствующим образом настраивает подключение. Существует несколько команд **show**, которые можно использовать при проверке конфигураций коммутатора. Используйте команду **show running-config** и **show interfaces** команду для проверки конфигурации порта коммутатора. Выходные данные команды **show interfaces** также полезны для обнаружения распространенных проблем на уровне доступа к сети, так как они отображают состояние протокола линии и канала передачи данных. Сообщения об ошибках ввода из команды show interfaces включают: карликовые кадры, гигантские кадры, ошибки CRC, а также коллизии и поздние коллизии. Используйте **show interfaces** , чтобы определить, нет ли в сети соединения или нет соединения между коммутатором и другим устройством.

**Удаленный защищеный доступ**

Telnet является более ранним протоколом, использующим небезопасную незашифрованную передачу как данных, так и идентификационной информации (имя пользователя и пароль) между взаимодействующими устройствами. Протокол Secure shell (SSH) — это протокол, который обеспечивает безопасное (зашифрованное) подключение для управления удаленным устройством. SSH обеспечивает защиту удаленных подключений, предоставляя надежное шифрование данных аутентификации устройства (имя пользователя и пароль), а также данных, передаваемых между устройствами. Используйте команду **show version** на коммутаторе, чтобы увидеть, какое IOS работает коммутатор в данный момент. Имя файла IOS, которое включает комбинацию «k9», поддерживает криптографические функции и возможности. Чтобы настроить SSH, необходимо убедиться, что коммутатор поддерживает его, настроить IP-адрес домена, создать пары ключей RSA, настроить аутентификацию с использованием, настроить линии VTY и включить SSH версии 2. Чтобы убедиться, что SSH работает, используйте команду **show ip ssh**, чтобы отобразить данные о версии и конфигурации SSH на устройстве.

**Базовая конфигурация маршрутизатора**

Всегда должны выполняться следующие задачи начальной настройки: присвоить устройству имя, чтобы отличить его от других маршрутизаторов и настроить пароли, настроить баннер для предоставления юридического уведомления о несанкционированном доступе и сохранить изменения на маршрутизаторе. Одним из существенных различий между коммутаторами и маршрутизаторами являются поддерживаемые устройствами типы интерфейсов. Например, коммутаторы 2-го уровня поддерживают локальные сети, в связи с чем они оснащены несколькими портами FastEthernet или Gigabit Ethernet. Топология двойного стека используется для демонстрации конфигурации интерфейсов IPv4 и IPv6 маршрутизатора. Маршрутизаторы поддерживают локальные и глобальные сети, и могут обеспечивать соединение между разными типами сетей. Таким образом, они поддерживают множество типов интерфейсов. Например, маршрутизаторы семейства Cisco G2 SR используют один или два интегрированных интерфейса Gigabit Ethernet и разъемы для высокоскоростных интерфейсных карт WAN (HWIC) для поддержания разных типов сетевых интерфейсов, включая последовательный, DSL и кабельный интерфейсы. Интерфейс обратной петли предоставляет собой логический, внутренний по отношению к маршрутизатору интерфейс. Он не назначается физическому порту и не может быть подключен к другому устройству.

**Проверка связи между подключенными на прямую сетями**

Используйте следующие команды, чтобы быстро определить состояние интерфейса: **show ip interface brief** и **show ipv6 interface brief** просмотреть сводку всех интерфейсов (адреса IPv4 и IPv6 и рабочее состояние), s**how running-config interface interface-id** просмотреть команды, применяемые к указанному интерфейсу, **show ip route** и **show ipv6 route** просмотреть таблицы маршрутизации IPv4 или IPv6, хранящейся в ОЗУ. Выходные данные команд **show ip interface brief** и **show ipv6 interface brief** можно использовать для быстрого выявления состояния всех интерфейсов маршрутизатора. Результат выполнения команды **show ipv6 interface gigabitethernet 0/0/0** , отображает состояние интерфейса и все IPv6-адреса, принадлежащие этому интерфейсу. Кроме локального адреса канала и глобального индивидуального адреса, выходные данные содержат групповые адреса, назначенные интерфейсу и начинающиеся с префикса FF02. Выходные данные отображают текущие команды **show running-config interface**, настроенные на указанном интерфейсе. Команда **show interfaces** отображает информацию об интерфейсе и счетчик потока пакетов для всех интерфейсов на устройстве. Проверьте конфигурацию интерфейса с помощью команд **show ip interface** и **show ipv6 interface**, которые отображают информацию, связанную с IPv4 и IPv6 для всех интерфейсов маршрутизатора. Проверьте маршруты с помощью команд **show ip route** и **show ipv6 route**. Фильтруйте вывод команды show, используя символ (|). Использовать выражения фильтра: **section**, **include**, **exclude** и **begin**. По умолчанию журнал команд включен и в его буфере хранятся последние 10 команд. Чтобы отобразить содержимое буфера, используйте команду привилегированного режима **show history**.

<!-- 1.6.4 -->
## Контрольная по модулю - Базовая конфигурация устройства