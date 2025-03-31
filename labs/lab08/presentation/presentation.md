---
## Front matter
lang: ru-RU
title: Лабораторная работа №8
subtitle: Администрирование локальных сетей 
author:
  - Мишина А. А.
date: 31 марта 2025

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

- Приобретение практических навыков по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) в локальной сети.

## Задание

1. Добавить DNS-записи для домена donskaya.rudn.ru на сервер dns.
2. Настроить DHCP-сервис на маршрутизаторе.
3. Заменить в конфигурации оконечных устройствах статическое распределение адресов на динамическое.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Cisco Packet Tracer

![Логическая схема локальной сети с добавленным DNS-сервером](image/1.png){ #fig:001 width=60% }

## Порт Fa0/2

![Активация порта](image/2.png){ #fig:002 width=60% }

## DNS-сервер

![Конфигурация dns-сервера](image/3.png){ #fig:003 width=60% }

## DNS-сервер 

![Конфигурация dns-сервера](image/4.png){ #fig:004 width=60% }

## DNS-сервер 

![Окно настройки сервиса DNS](image/5.png){ #fig:005 width=60% }

## DHCP-сервис

![Настройка DHCP-сервиса на маршрутизаторе](image/6.png){ #fig:006 width=60% }

## Просмотр

![Информация о пулах DHCP](image/7.png){ #fig:007 width=30% }

## Просмотр

![Информация о привязках выданных адресов](image/8.png){ #fig:008 width=60% }

## IP-адрес

![Просмотр статического ip-адреса](image/9.png){ #fig:009 width=60% }

## IP-адрес

![Просмотр динамически заданного ip-адреса](image/10.png){ #fig:010 width=60% }

## Проверка

![Проверка доступности устройств из разных подсетей](image/11.png){ #fig:011 width=40% }

## Web browser

![Информация по адресу www.donskaya.rudn.ru](image/12.png){ #fig:012 width=40% }

## Режим симуляции

![Запрос адреса по протоколу DHCP в режиме симуляции](image/13.png){ #fig:013 width=60% }

## Список событий

![Список событий по DHCP запросу](image/14.png){ #fig:014 width=60% }

## Запрос

![DHCP-запрос на выделение адреса. Заголовки пакета](image/15.png){ #fig:015 width=60% }

## Ответ

![DHCP-ответ с выделенным адресом. Заголовки пакета](image/16.png){ #fig:016 width=60% }

## Вывод

- В результате выполнения лабораторной работы я приобрела практические навыки по настройке динамического распределения IP-адресов посредством протокола DHCP (Dynamic Host Configuration Protocol) в локальной сети.