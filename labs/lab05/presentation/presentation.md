---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
subtitle: Администрирование локальных сетей 
author:
  - Мишина А. А.
date: 13 марта 2025

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
 - '\makeatletter'

 - '\makeatother'
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

- Получить основные навыки по настройке VLAN на коммутаторах сети.

## Задание

1. На коммутаторах сети настроить Trunk-порты на соответствующих интерфейсах, связывающих коммутаторы между собой.
2. Коммутатор msk-donskaya-sw-1 настроить как VTP-сервер и прописать на нём номера и названия VLAN.
3. Коммутаторы msk-donskaya-sw-2 — msk-donskaya-sw-4, mskpavlovskaya-sw-1 настроить как VTP-клиенты, на интерфейсах указать принадлежность к соответствующему VLAN.
4. На серверах прописать IP-адреса.
5. На оконечных устройствах указать соответствующий адрес шлюза и прописать статические IP-адреса из диапазона соответствующей сети, следуя регламенту выделения ip-адресов.
6. Проверить доступность устройств, принадлежащих одному VLAN, и недоступность устройств, принадлежащих разным VLAN.
7. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-donskaya-aamishina-sw-1](image/1.png){ #fig:001 width=80% }

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-donskaya-aamishina-sw-2](image/2.png){ #fig:002 width=80% }

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-donskaya-aamishina-sw-3](image/3.png){ #fig:003 width=80% }

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-donskaya-aamishina-sw-4](image/4.png){ #fig:004 width=80% }

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-donskaya-aamishina-sw-1](image/5.png){ #fig:005 width=80% }

## Настройка Trunk-портов

![Настройка Trunk-портов на msk-pavlovskaya-aamishina-sw-1](image/6.png){ #fig:006 width=80% }

## Коммутатор msk-donskaya-aamishina-sw-1

![Задание VLAN](image/7.png){ #fig:007 width=80% }

## Коммутатор msk-donskaya-aamishina-sw-1

![Проверка VLAN](image/8.png){ #fig:008 width=80% }

## VTP-сервер

![Конфигурация VTP msk-donskaya-aamishina-sw-1](image/9.png){ #fig:009 width=80% }

## VTP-клиент

![Конфигурация VTP msk-donskaya-aamishina-sw-2](image/10.png){ #fig:010 width=80% }

## VTP-клиент

![Конфигурация VTP msk-donskaya-aamishina-sw-3](image/11.png){ #fig:011 width=80% }

## VTP-клиент

![Конфигурация VTP msk-donskaya-aamishina-sw-4](image/12.png){ #fig:012 width=80% }

## Проверка

![Проверка VTP статуса](image/13.png){ #fig:013 width=80% }

## Проверка

![Проверка отображения VLAN](image/14.png){ #fig:014 width=60% }

## VTP-клиент

![Конфигурация VTP msk-pavlovskaya-aamishina-sw-1](image/15.png){ #fig:015 width=80% }

## VLAN

![Конфигурация VTP msk-donskaya-aamishina-sw-4](image/16.png){ #fig:016 width=80% }

## VLAN

![Конфигурация VTP msk-pavlovskaya-aamishina-sw-1](image/17.png){ #fig:017 width=80% }

## VLAN

![Конфигурация VTP msk-donskaya-aamishina-sw-2](image/18.png){ #fig:018 width=80% }

## VLAN

![Конфигурация VTP msk-donskaya-aamishina-sw-3](image/19.png){ #fig:019 width=80% }

## IP-адреса

![Задание IP-адреса шлюзу](image/20.png){ #fig:020 width=80% }

## IP-адреса

![Задание IP-адреса](image/21.png){ #fig:021 width=40% }

## Проверка

![ifconfig](image/22.png){ #fig:022 width=80% }

## Проверка

![Пингование](image/23.png){ #fig:023 width=60% }

## Симуляция

![Режим симуляции](image/24.png){ #fig:024 width=80% }

## PDU

![Информация о PDU](image/25.png){ #fig:025 width=60% }

## Вывод

- В процессе выполнения данной лабораторной работы я получила основные навыки по настройке VLAN на коммутаторах сети.