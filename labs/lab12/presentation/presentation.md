---
## Front matter
lang: ru-RU
title: Лабораторная работа №12
subtitle: Администрирование локальных сетей
author:
  - Мишина А. А.
date: 29 апреля 2025

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

# Цель работы

- Приобрести практические навыки по настройке доступа локальной сети к внешней сети посредством NAT.

# Задание

1. Сделать первоначальную настройку маршрутизатора provider-gw-1 и коммутатора provider-sw-1 провайдера: задать имя, настроить доступ по
паролю и т.п.
2. Настроить интерфейсы маршрутизатора provider-gw-1 и коммутатора
provider-sw-1 провайдера.
3. Настроить интерфейсы маршрутизатора сети «Донская» для доступа к сети провайдера.
4. Настроить на маршрутизаторе сети «Донская» NAT с правилами.
5. Настроить доступ из внешней сети в локальную сеть организации.
6. Проверить работоспособность заданных настроек.
7. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Первоначальная настройка

![Первоначальная настройка маршрутизатора provider-gw-1](image/1.png){#fig:001 width=70%}

## Первоначальная настройка

![Первоначальная настройка коммутатора provider-sw-1](image/2.png){#fig:002 width=70%}

## Настройка интерфейсов

![Настройка интерфейсов маршрутизатора provider-gw-1](image/3.png){#fig:003 width=50%}

## Настройка интерфейсов

![Настройка интерфейсов коммутатора provider-sw-1](image/4.png){#fig:004 width=50%}

## Настройка интерфейсов

![Настройка интерфейсов маршрутизатора msk-donskaya-gw-1](image/5.png){#fig:005 width=50%}

## Проверка

![Проверка доступа с маршрутизатора на Донской к маршрутизатору провайдера](image/6.png){#fig:006 width=70%}

## Настройка пула адресов для NAT

![Настройка пула адресов для NAT](image/7.png){#fig:007 width=70%}

## Настройка списка доступа для NAT

![Настройка списка доступа для NAT](image/8.png){#fig:008 width=70%}

## Настройка PAT

![Настройка Port Address Translation (PAT) на субинтерфейсах маршрутизатора](image/9.png){#fig:009 width=70%}

## Проверка

![Проверка доступности к маршрутизаторам от ноутбука админ](image/10.png){#fig:010 width=40%}

## Настройка доступа из Интернета

![Настройка доступа из Интернета](image/11.png){#fig:011 width=70%}

## Проверка

![Добавление ноутбука](image/12.png){#fig:012 width=70%}

## Проверка

![Проверка доступа из Интернета по ftp](image/13.png){#fig:013 width=70%}

## Проверка

![Проверка доступа из Интернета к web-серверу](image/14.png){#fig:014 width=70%}

## Проверка

![Доступ dep-donskaya-1 к 192.0.2.13](image/15.png){#fig:015 width=70%}

## Проверка

![Доступ dk-donskaya-1 к www.yandex.ru](image/16.png){#fig:016 width=70%}

## Проверка

![Доступ dk-donskaya-1 к stud.rudn.university](image/17.png){#fig:017 width=70%}

## Проверка

![Доступ adm-donskaya-1 к www.rudn.ru](image/18.png){#fig:018 width=70%}

## Выводы

- В результате выполнения данной лабораторной работы я приобрела практические навыки по настройке доступа локальной сети к внешней сети посредством NAT.
