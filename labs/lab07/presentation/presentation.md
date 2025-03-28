---
## Front matter
lang: ru-RU
title: Лабораторная работа №7
subtitle: Администрирование локальных сетей 
author:
  - Мишина А. А.
date: 27 марта 2025

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

- Получить навыки работы с физической рабочей областью Packet Tracer, а также учесть физические параметры сети.

## Задание

Требуется заменить соединение между коммутаторами двух территорий msk-donskaya-sw-1 и msk-pavlovskaya-sw-1 на соединение, учитывающее физические параметры сети, а именно — расстояние между двумя территориями. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Город

![Физическая рабочая область Packet Tracer](image/1.png){ #fig:001 width=40% }

## Здания

![Изображение зданий в физической рабочей области Packet Tracer](image/2.png){ #fig:002 width=60% }

## Donskaya

![Серверное помещение](image/3.png){ #fig:003 width=60% }

## Donskaya

![Отображение серверных стоек](image/4.png){ #fig:004 width=17% }

## Pavlovskaya

![Перемещение устройств на другую территорию](image/5.png){ #fig:005 width=60% }

## Pavlovskaya

![Размещение устройств на территории Pavlovskaya](image/6.png){ #fig:006 width=60% }

## Проверка

![Проверка работоспособности соединения](image/7.png){ #fig:007 width=60% }

## Настройки

![Активация разрешения на учет физических характеристик среды передачи](image/8.png){ #fig:008 width=60% }

## Здания

![Размещение территорий на расстояние 1000 метров друг от друга](image/9.png){ #fig:009 width=60% }

## Проверка

![Проверка работоспособности соединения](image/10.png){ #fig:010 width=60% }

## Повторители

![Повторитель с модулями PT-REPEATER-NM-1FFE и PT-REPEATER-NM-1CFE для подключения оптоволокна и витой пары по технологии Fast Ethernet](image/11.png){ #fig:011 width=60% }

## Pavlovskaya

![Пермещение msk-pavlovskaya-aamishina-mc-1 на территорию Pavlovskaya](image/12.png){ #fig:012 width=60% }

## Итоговая схема сети

![Схема сети с учётом физических параметров сети в логической рабочей области Packet Tracer](image/13.png){ #fig:013 width=60% }

## Проверка

![Проверка работоспособности соединения](image/14.png){ #fig:014 width=60% }

## Вывод

- В результате выполнения лабораторной работы я получила навыки работы с физической рабочей областью Packet Tracer, а также учитывала физические параметры сети.