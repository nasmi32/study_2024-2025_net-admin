---
## Front matter
lang: ru-RU
title: Лабораторная работа №10
subtitle: Администрирование локальных сетей
author:
  - Мишина А. А.
date: 15 апреля 2025

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

- Освоить настройку прав доступа пользователей к ресурсам сети.

## Задание

1. Требуется настроить следующие правила доступа:
   - web-сервер: разрешить доступ всем пользователям по протоколу HTTP через порт 80 протокола TCP, а для администратора открыть доступ по протоколам Telnet и FTP;
   - файловый сервер: с внутренних адресов сети доступ открыт по портам для общедоступных каталогов, с внешних — доступ по протоколу FTP;
   - почтовый сервер: разрешить пользователям работать по протоколам SMTP и POP3 (соответственно через порты 25 и 110 протокола TCP), а для администратора — открыть доступ по протоколам Telnet и FTP;
   - DNS-сервер: открыть порт 53 протокола UDP для доступа из внутренней сети;
   - разрешить icmp-сообщения, направленные в сеть серверов;
   - запретить для сети Other любые запросы за пределы сети, за исключением администратора;
   - разрешить доступ в сеть управления сетевым оборудованием только администратору сети.

## Задание
   
2. Требуется проверить правильность действия установленных правил доступа.
3. Требуется выполнить задание для самостоятельной работы по настройке прав доступа администратора сети на Павловской.
4. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

## Логическая область

![Размещение ноутбука администратора в сети other-donskaya-1](image/1.png){#fig:001 width=70%}

## Ноутбук admin

![Задание статического ip-адреса ноутбуку admin](image/2.png){#fig:002 width=70%}

## Ноутбук admin

![Задание gateway-адреса и адреса DNS-сервера ноутбуку admin](image/3.png){#fig:003 width=70%}

## Проверка

![Проверка работоспособности соединения ноутбука admin](image/4.png){#fig:004 width=40%}

## Настройка

![Настройка доступа к web-серверу по порту tcp 80, добавление списка управления доступом к интерфейсу](image/5.png){#fig:005 width=70%}

## Проверка

![Проверка доступа к web-серверу через протокол HTTP](image/6.png){#fig:006 width=50%}

## Проверка

![Проверка недоступности web-сервера через ping](image/7.png){#fig:007 width=50%}

## Настройка

![Настройка дополнительного доступа для администратора по протоколам Telnet и FTP](image/8.png){#fig:008 width=70%}

## Проверка

![Проверка работы FTP у администратора](image/9.png){#fig:009 width=70%}

## Проверка

![Проверка недоступности подключения по FTP с другого устройства сети](image/10.png){#fig:010 width=70%}

## Настройка

![Настройка доступа к файловому серверу, почтовому серверу и к DNS-серверу](image/11.png){#fig:011 width=70%}

## Проверка

![Проверка доступности web-сервера по имени](image/12.png){#fig:012 width=70%}

## Проверка

![Проверка доступности web-сервера по ip-адресу](image/13.png){#fig:013 width=70%}

## Просмотр правил

![Разрешение icmp-запросов и просмотр строк правил в списке контроля доступа](image/14.png){#fig:014 width=70%}

## Настройка

![Настройка доступа для сети Other и доступа администратора к сети сетевого оборудования](image/15.png){#fig:015 width=70%}

# Самостоятельная работа

## Ping

![Пингование устройств с dep-donskaya-aamishina-1](image/16.png){#fig:016 width=40%}

## Ping

![Пингование устройств с dk-donskaya-aamishina-1](image/17.png){#fig:017 width=45%}

## Ping

![Пингование устройств с admin](image/18.png){#fig:018 width=45%}

## Логическая область

![Логическая область с размещенным ноутбуком admin на Павловской](image/19.png){#fig:019 width=70%}

## Настройка

![Настройка доступа для admin-pavlovskaya](image/20.png){#fig:020 width=70%}

## Проверка

![Проверка списка контроля доступа](image/21.png){#fig:021 width=50%}
 
## Проверка

![Проверка корректности настроенного доступа](image/22.png){#fig:022 width=40%}

## Выводы

В процессе выполнения данной лабораторной работы я освоила настройку прав доступа пользователей к ресурсам сети.