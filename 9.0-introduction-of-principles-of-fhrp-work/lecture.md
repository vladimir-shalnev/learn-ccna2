# Введение в принципы работы 

<!-- 9.0.1 -->
## Почему я должен выполнить этот модуль?

Добро пожаловать в принципы работы FHRP!

Ваша сеть работает и работает. Вы сделали избыточность уровня 2 без каких-либо петель уровня 2. Все ваши устройства получают свои адреса динамически. Вы являетесь мега специалистом в сетевом администрировании! Но, подождите. Один из ваших маршрутизаторов, маршрутизатор шлюза по умолчанию, упал. Ни один из хостов не может отправлять сообщения за пределами непосредственной сети. Это займет некоторое время, чтобы снова работать этот маршрутизатор шлюза по умолчанию. У вас много злых людей спрашивают, как скоро сеть будет «резерв».

Вы можете легко избежать этой проблемы. Протокол резервирования первого перехода (FHRP) ( Протокол резервирования первого перехода) - это решение, которое вам нужно. В этом модуле обсуждаются, что делает FHRP, и все типы FHRP, которые доступны вам. Одним из таких типов является патентованный Cisco FHRP, называемый Hot Standby Router Protocol (HSRP). Вы узнаете, как работает HSRP, а затем выполните действие трассировки пакетов, где вы будете настраивать и проверять HSRP. Не будем ждать, начнем!

<!-- 9.0.2 -->
## Что я буду изучать в этом модуле?

**Цель модуля:** Принципы работы FHRP

**Задачи модуля:** Объяснить, как FHRP предоставляет службы шлюза по умолчанию в резервной сети.

| **Заголовок темы** |	**Цель темы** |
| --- | --- |
| **Протокол резервирования первого перехода (FHRP)** | Объяснить назначение и принципы работы протоколов резервирования первого перехода (FHRP). |
| **HSRP** | Объясните принципы работы протокола HSRP. |