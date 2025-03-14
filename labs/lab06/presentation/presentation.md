---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
subtitle: Администрирование локальных сетей 
author:
  - Мишина А. А.
date: 14 марта 2025

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

- Настроить статическую маршрутизацию VLAN в сети.

## Задание

1. Добавить в локальную сеть маршрутизатор, провести его первоначальную настройку.

2. Настроить статическую маршрутизацию VLAN.

3. При выполнении работы необходимо учитывать соглашение об именовании

# Выполнение лабораторной работы

## Маршрутизатор

![Логическая область проекта с маршрутизатором Cisco 2811](image/1.png){ #fig:001 width=60% }

## Маршрутизатор

![Конфигурация маршрутизатора](image/2.png){ #fig:002 width=60% }

## Настройка Trunk-порта

![Конфигурация коммутатора msk-donskaya-aamishina-sw-1](image/3.png){ #fig:003 width=60% }

## Маршрутизатор

![Конфигурация VLAN-интерфейсов маршрутизатора](image/4.png){ #fig:004 width=30% }

## dk-donskaya-aamishina-1

![Команда ipconfig](image/5.png){ #fig:005 width=60% }

## Проверка

![Проверка доступности оконечных устройств](image/6.png){ #fig:006 width=40% }

## Симуляция

![Передвижение ICMP-пакета по сети](image/7.png){ #fig:007 width=60% }

## Симуляция

![Передвижение ICMP-пакета по сети](image/8.png){ #fig:008 width=60% }

## Симуляция

![Информация о PDU](image/9.png){ #fig:009 width=60% }

## Вывод

- В результате выполнения лабораторной работы я настроила статическую маршрутизацию VLAN в сети.