---
## Front matter
lang: ru-RU
title: Лабораторная работа №15
subtitle: Администрирование локальных сетей
author:
  - Мишина А. А.
date: 22 мая 2025

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

## Цель работы

- Настроить динамическую маршрутизацию между территориями организации.

## Задание

1. Настроить динамическую маршрутизацию по протоколу OSPF на маршрутизаторах msk-donskaya-gw-1, msk-q42-gw-1, msk-hostel-gw-1, sch-sochi-gw-1.
2. Настроить связь сети квартала 42 в Москве с сетью филиала в г. Сочи напрямую.
3. В режиме симуляции отследить движение пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.
4. На коммутаторе провайдера отключить временно vlan 6 и в режиме симуляции убедиться в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.
5. На коммутаторе провайдера восстановить vlan 6 и в режиме симуляции убедиться в изменении маршрута прохождения пакета ICMP с ноутбука администратора сети на Донской в Москве (Laptop-PT admin) до компьютера пользователя в филиале в г. Сочи pc-sochi-1.

# Выполнение лабораторной работы

## Настройка OSPF

![Настройка маршрутизатора msk-donskaya-gw-1](image/1.png){#fig:001 width=70%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе msk-donskaya-gw-1](image/2.png){#fig:002 width=70%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе msk-donskaya-gw-1](image/3.png){#fig:003 width=50%}

## Настройка OSPF

![Настройка маршрутизатора msk-q42-gw-1](image/4.png){#fig:004 width=70%}

## Настройка OSPF

![Настройка маршрутизирующего коммутатора msk-hostel-gw-1](image/5.png){#fig:005 width=70%}

## Настройка OSPF

![Настройка маршрутизатора sch-sochi-gw-1](image/6.png){#fig:006 width=70%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе msk-donskaya-gw-1](image/7.png){#fig:007 width=70%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе msk-q42-gw-1](image/8.png){#fig:008 width=60%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе msk-q42-gw-1](image/9.png){#fig:009 width=50%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизирующем коммутаторе msk-hostel-gw-1](image/10.png){#fig:010 width=50%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизирующем коммутаторе msk-hostel-gw-1](image/11.png){#fig:011 width=50%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе sch-sochi-gw-1](image/12.png){#fig:012 width=50%}

## Проверка

![Проверка состояния протокола OSPF на маршрутизаторе sch-sochi-gw-1](image/13.png){#fig:013 width=50%}

## Настройка линка 42-й квартал–Сочи

![Настройка интерфейсов коммутатора provider-sw-1](image/14.png){#fig:014 width=70%}

## Настройка линка 42-й квартал–Сочи

![Настройка маршрутизатора msk-q42-gw-1](image/15.png){#fig:015 width=70%}

## Настройка линка 42-й квартал–Сочи

![Настройка коммутатора sch-sochi-sw-1](image/16.png){#fig:016 width=70%}

## Настройка линка 42-й квартал–Сочи

![Настройка маршрутизатора sch-sochi-gw-1](image/17.png){#fig:017 width=70%}

## Проверка настроек

![Маршрут при пересылке пакетов между admin и pc-sochi](image/18.png){#fig:018 width=50%}

## Проверка настроек

![Движение пакета ICMP при пересылке с администратора на ПК-Сочи](image/19.png){#fig:019 width=70%}

## Проверка настроек

![Перестройка маршрута при отключении 6 vlan](image/20.png){#fig:020 width=35%}

## Проверка настроек

![Перестройка маршрута при включении 6 vlan](image/21.png){#fig:021 width=70%}

## Выводы

- В результате выполнения данной лабораторной работы я приобрела практические навыки по настройке динамической маршрутизации между территориями организации.