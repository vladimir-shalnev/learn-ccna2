
---

> **ВАЖНО**
> 
> Форма для ответов на вопросы будет доступна только при развертывании лабораторной работы 

---

## Топология

![](./assets/topology.png)

## Таблица адресации

| Устройство | Интерфейс | IP адрес/префикс       | Шлюз по умолчанию |
|------------|-----------|------------------------|-------------------|
| R1         | G0/0/0    | 172.16.20.1/25         | —                 |
| R1         | G0/0/1    | 172.16.20.129/25       | —                 |
| R1         | S0/1/0    | 209.165.200.225/30     | —                 |
| PC1        | NIC       | 172.16.20.10/25        | 172.16.20.1       |
| PC2        | NIC       | 172.16.20.138/25       | 172.16.20.129     |
| R2         | G0/0      | 2001:db8:c0de:12።1/64  | —                 |
| R2         | G0/0/1    | 2001:db8:c0de:13። 1/64 | —                 |
| R2         | S0/1/1    | 2001:db8:c0de:11።1/64  | —                 |
| R2         | S0/1/1    | fe80::2                | Нет               |
| PC3        | NIC       | 2001:db8:c0de:12።а/64  | fe80::2           |
| PC4        | NIC       | 2001:db8:c0de:13።а/64  | fe80::2           |

## Цели

-   Проверить IPv4-связь между подключенными напрямую сетями

-   Проверить IPv6-связь между подключенными напрямую сетями

-   Найти и устранить неполадки подключения

## Общие сведения

К роутерам R1 и R2 подключено по две локальных сети. Ваша задача — настроить соответствующую адресацию на каждом устройстве и проверить подключение между локальными сетями.

**Примечание**. Пароль пользовательского режима — **cisco**. Пароль привилегированного режима EXEC — **class**.

## Инструкции

### Часть 1. Проверка IPv4-связи между подключенными напрямую сетями

**Шаг 1. Проверьте IPv4-адреса и состояние порта на R1**

1.  Проверьте состояние настроенных интерфейсов, фильтруя выходные данные.

    ```
    R1# show ip interface brief | exclude unassigned
    ```

2.  На основе выходных данных исправляйте все проблемы состояния порта, которые вы видите.

3.  Обратитесь к **таблице адресации** и проверьте IP-адреса, настроенные на R1. При необходимости можете вносить любые коррективы в адресацию.

4.  Отобразите таблицу маршрутизации путем фильтрации, чтобы начать вывод на слово **Gateway**.

    **Примечание.** Термины, используемые для фильтрации выходных данных, могут быть сокращены до соответствия тексту, если совпадение уникально. Например, Gateway, Gate и Ga будут иметь тот же эффект. G не будет давать такой эффект. Фильтрация чувствительна к регистру

    ```
    R1# show ip route | begin Gate
    ```

    - ответьте на вопрос №1

5.  Отобразите информацию об интерфейсе и фильтра для **описания** или **подключения**.

    **Примечание.** При использовании **include** или **exclude** можно выполнить несколько поисков, разделив строки поиска символом ( **\|** )

    ```
    R1# show interface | include Desc|conn
    ```

    - Ответьте на вопрос №2

6.  Отобразите конкретную информацию интерфейса для G0/0/0 путем фильтрации для **дуплексного режима**.

    - Ответьте на вопрос №3

**Шаг 2. Проверьте подключение**

Компьютеры **PC1** и **PC2** с помощью утилиты **ping** должны успешно проверять связь между собой и сервером с **двойным стеком**. Если нет, проверьте состояние интерфейсов и назначения IP-адресов.

### Часть 2. Проверка IPv6-связи между подключенными напрямую сетями

**Шаг 1. Проверьте IPv6-адреса и состояние порта на R2**

1.  Проверьте состояние настроенных интерфейсов.

    ```
    R2# show ipv6 int brief
    ```

    - Ответьте на вопрос №4

2.  Обратитесь к **таблице адресации** и внесите необходимые исправления.

    **Примечание.** При изменении IPv6-адреса необходимо удалить неверный адрес, так как интерфейс способен поддерживать несколько IPv6-сетей.

    ```
    R2(config)# int g0/0/1
    R2(config-if)# no ipv6 address 2001:db8:c0de:14::1/64
    ```

    - Ответьте на вопрос №5

3.  Отобразите таблицу маршрутизации IPv6.

    **Примечание.** Команды фильтрации в настоящее время не работают с командами IPv6.

4. Отобразите все IPv6-адреса, настроенные на интерфейсах, путем фильтрации выходных данных **running-config**.

    Фильтрация вывода на **R2** для **ipv6** или **интерфейса** .

    ```
    R2# sh run | include ipv6|interface
    ```

    - Ответьте на вопрос №6

**Шаг 2. Проверьте подключение**

Компьютеры **PC3** и **PC4** с помощью утилиты **ping** должны успешно проверять связь между собой и сервером с **двойным стеком**. Если нет, проверьте состояние интерфейса и назначения IPv6-адресов.

<!-- [Скачать файл Packet Tracer для локального запуска](./assets/1.5.10-lab.pka) -->
