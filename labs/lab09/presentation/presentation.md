---
## Front matter
lang: ru-RU
title: Лабораторная работа №9
subtitle: Администрирование локальных сетей
author:
  - Мишина А. А.
date: 1 апреля 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Мишина Анастасия Алексеевна
  * НПИбд-02-22
  * <https://github.com/nasmi32>

:::
::: {.column width="30%"}


:::
::::::::::::::

## Цели и задачи

- Изучить возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними.

## Задание

1. Сформировать резервное соединение между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-3.
2. Настроить балансировку нагрузки между резервными соединениями.
3. Настроить режим Portfast на тех интерфейсах коммутаторов, к которым подключены серверы.
4. Изучить отказоустойчивость резервного соединения.
5. Сформировать и настроить агрегированное соединение интерфейсов Fa0/20 -- Fa0/23 между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-4.
6. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Cisco Packet Tracer

![Логическая схема локальной сети с резервным соединением](image/1.png){ #fig:001 width=60% }

## trunk-порт

![Настройка trunk-порта на интерфейсе Gig0/2 коммутатора msk-donskaya-aamishina-sw-3](image/2.png){ #fig:002 width=60% }

## trunk-порт

![Настройка trunk-порта на интерфейсе Fa0/23 коммутатора msk-donskaya-aamishina-sw-1](image/3.png){ #fig:003 width=60% }

## trunk-порт

![Настройка trunk-порта на интерфейсе Fa0/23 коммутатора msk-donskaya-aamishina-sw-4](image/4.png){ #fig:004 width=60% }

## Пингование

![Пингование сервера mail и web](image/5.png){ #fig:005 width=40% }

## Режим симуляции

![Режим симуляции движения пакетов ICMP к серверу web](image/6.png){ #fig:006 width=60% }

## Режим симуляции

![Режим симуляции движения пакетов ICMP к серверу mail](image/7.png){ #fig:007 width=60% }

## STP

![Просмотр состояния протокола STP для vlan 3](image/8.png){ #fig:008 width=60% }

## Настройка

![Настройка коммутатора msk-donskaya-aamishina-sw-1 корневым](image/9.png){ #fig:009 width=60% }

## Режим симуляции

![Режим симуляции движения пакетов ICMP к серверу mail](image/10.png){ #fig:010 width=60% }

## Режим симуляции

![Режим симуляции движения пакетов ICMP к серверу web](image/11.png){ #fig:011 width=60% }

## Portfast

![Настройка режима Portfast](image/12.png){ #fig:012 width=60% }

## Portfast

![Настройка режима Portfast](image/13.png){ #fig:013 width=60% }

## Пингование

![Пингование mail.donskaya.rudn.ru](image/14.png){ #fig:014 width=60% }

## Разрыв

![Разрыв соединения](image/15.png){ #fig:015 width=60% }

## Пингование

![Восстановление соединения](image/16.png){ #fig:016 width=60% }

## Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/17.png){ #fig:017 width=60% }

## Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/18.png){ #fig:018 width=60% }

## Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/19.png){ #fig:019 width=60% }

## Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/20.png){ #fig:020 width=60% }

## Rapid PVST+

![Режим работы по протоколу Rapid PVST+](image/21.png){ #fig:021 width=60% }

## Пингование

![Пингование mail.donskaya.rudn.ru](image/22.png){ #fig:022 width=60% }

## Разрыв

![Разрыв соединения](image/23.png){ #fig:023 width=60% }

## Cisco Packet Tracer

![Логическая схема локальной сети с агрегированным соединением](image/24.png){ #fig:024 width=60% }

## Настройка

![Настройка агрегирования каналов на msk−donskaya-aamishina−sw−1](image/25.png){ #fig:025 width=60% }

## Настройка

![Настройка агрегирования каналов на msk−donskaya-aamishina−sw−4](image/26.png){ #fig:026 width=60% }

## Вывод

- В результате выполнения лабораторной работы я изучила возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними.