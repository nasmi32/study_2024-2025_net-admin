---
## Front matter
title: "Отчёт по лабораторной работе №9"
subtitle: "Дисциплина: Администрирование локальных сетей"
author: "Мишина Анастасия Алексеевна"

## Generic options
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 14pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучить возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними [@netadmin].

# Задание

1. Сформировать резервное соединение между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-3.
2. Настроить балансировку нагрузки между резервными соединениями.
3. Настроить режим Portfast на тех интерфейсах коммутаторов, к которым подключены серверы.
4. Изучить отказоустойчивость резервного соединения.
5. Сформировать и настроить агрегированное соединение интерфейсов Fa0/20 -- Fa0/23 между коммутаторами msk-donskaya-sw-1 и msk-donskaya-sw-4.
6. При выполнении работы необходимо учитывать соглашение об именовании.

# Выполнение лабораторной работы

Сформируем резервное соединение между коммутаторами msk-donskaya-aamishina-sw-1 и msk-donskaya-aamishina-sw-3 (рис. [-@fig:001]). Для этого:

- заменим соединение между коммутаторами msk-donskaya-aamishina-sw-1 (Gig0/2)и msk-donskaya-aamishina-sw-4 (Gig0/1) на соединение между коммутаторами msk-donskaya-aamishina-sw-1 (Gig0/2) и msk-donskaya-aamishina-sw-3 (Gig0/2);
- сделаем порт на интерфейсе Gig0/2 коммутатора msk-donskaya-aamishina-sw-3 транковым (рис. [-@fig:002]);
- соединение между коммутаторами msk-donskaya-aamishina-sw-1 и msk-donskaya-aamishina-sw-4 сделаем через интерфейсы Fa0/23, не забыв активировать их в транковом режиме (рис. [-@fig:003]), (рис. [-@fig:004]).

![Логическая схема локальной сети с резервным соединением](image/1.png){ #fig:001 width=60% }

![Настройка trunk-порта на интерфейсе Gig0/2 коммутатора msk-donskaya-aamishina-sw-3](image/2.png){ #fig:002 width=60% }

![Настройка trunk-порта на интерфейсе Fa0/23 коммутатора msk-donskaya-aamishina-sw-1](image/3.png){ #fig:003 width=60% }

![Настройка trunk-порта на интерфейсе Fa0/23 коммутатора msk-donskaya-aamishina-sw-4](image/4.png){ #fig:004 width=60% }

С оконечного устройства dk-donskaya-aamishina-1 пропингуем серверы mail и web (рис. [-@fig:005]).

![Пингование сервера mail и web](image/5.png){ #fig:005 width=60% }

В режиме симуляции проследим движение пакетов ICMP. Убедимся, что движение пакетов происходит через коммутатор msk-donskaya-aamishina-sw-2 (рис. [-@fig:006]), (рис. [-@fig:007]).

![Режим симуляции движения пакетов ICMP к серверу web](image/6.png){ #fig:006 width=60% }

![Режим симуляции движения пакетов ICMP к серверу mail](image/7.png){ #fig:007 width=60% }

На коммутаторе msk-donskaya-aamishina-sw-2 посмотрим состояние протокола STP для vlan 3 (рис. [-@fig:008]).

![Просмотр состояния протокола STP для vlan 3](image/8.png){ #fig:008 width=60% }

В качестве корневого коммутатора STP настроим коммутатор msk-donskaya-aamishina-sw-1 (рис. [-@fig:009]).

![Настройка коммутатора msk-donskaya-aamishina-sw-1 корневым](image/9.png){ #fig:009 width=60% }

Используя режим симуляции, убедимся, что пакеты ICMP пойдут от хоста dk-donskaya-aamishina-1 до mail через коммутаторы msk-donskaya-aamishina-sw-1 и msk-donskaya-aamishina-sw-3, а от хоста dk-donskaya-aamishina-1 до web через коммутаторы msk-donskaya-aamishina-sw-1 и msk-donskaya-aamishina-sw-2 (рис. [-@fig:010]), (рис. [-@fig:011]).

![Режим симуляции движения пакетов ICMP к серверу mail](image/10.png){ #fig:010 width=60% }

![Режим симуляции движения пакетов ICMP к серверу web](image/11.png){ #fig:011 width=60% }

Настроим режим Portfast на тех интерфейсах коммутаторов, к которым подключены серверы (рис. [-@fig:012]), (рис. [-@fig:013]).

![Настройка режима Portfast](image/12.png){ #fig:012 width=60% }

![Настройка режима Portfast](image/13.png){ #fig:013 width=60% }

Изучим отказоустойчивость протокола STP и время восстановления соединения при переключении на резервное соединение. Для этого используем команду ping -n 1000 mail.donskaya.rudn.ru на хосте dk-donskaya-aamishina-1 (рис. [-@fig:014]), а разрыв соединения обеспечим переводом соответствующего интерфейса коммутатора в состояние shutdown (рис. [-@fig:015]).

![Пингование mail.donskaya.rudn.ru](image/14.png){ #fig:014 width=60% }

![Разрыв соединения](image/15.png){ #fig:015 width=60% }

Видно, что на время восстановления соединения потребовалось четыре пинга, что достаточно долго. После восстановления пингование продолжилось (рис. [-@fig:016]).

![Восстановление соединения](image/16.png){ #fig:016 width=60% }

Переключим коммутаторы в режим работы по протоколу Rapid PVST+ (рис. [-@fig:017]), (рис. [-@fig:018]), (рис. [-@fig:019]), (рис. [-@fig:020]), (рис. [-@fig:021]).

![Режим работы по протоколу Rapid PVST+](image/17.png){ #fig:017 width=60% }

![Режим работы по протоколу Rapid PVST+](image/18.png){ #fig:018 width=60% }

![Режим работы по протоколу Rapid PVST+](image/19.png){ #fig:019 width=60% }

![Режим работы по протоколу Rapid PVST+](image/20.png){ #fig:020 width=60% }

![Режим работы по протоколу Rapid PVST+](image/21.png){ #fig:021 width=60% }

Изучим отказоустойчивость протокола Rapid PVST+ и время восстановления соединения при переключении на резервное соединение (рис. [-@fig:022]), (рис. [-@fig:023]). Сразу после разрыва соединения задержки по времени вообще не было, сеть моментально перестроилась. Когда обратно вернули старое соединение, потребовался один пинг, что достаточно быстро. После восстановление пингование продолжилось.

![Пингование mail.donskaya.rudn.ru](image/22.png){ #fig:022 width=60% }

![Разрыв соединения](image/23.png){ #fig:023 width=60% }

Сформируем агрегированное соединение интерфейсов Fa0/20 – Fa0/23 между коммутаторами msk-donskaya-aamishina-sw-1 и msk-donskaya-aamishina-sw-4 (рис. [-@fig:024]).

![Логическая схема локальной сети с агрегированным соединением](image/24.png){ #fig:024 width=60% }

Настроим агрегирование каналов (режим EtherChannel) (рис. [-@fig:025]), (рис. [-@fig:026]).

![Настройка агрегирования каналов на msk−donskaya-aamishina−sw−1](image/25.png){ #fig:025 width=60% }

![Настройка агрегирования каналов на msk−donskaya-aamishina−sw−4](image/26.png){ #fig:026 width=60% }

# Контрольные вопросы

1. Какую информацию можно получить, воспользовавшись командой определения состояния протокола STP для VLAN (на корневом и не на корневом устройстве)? Приведите примеры вывода подобной информации на устройствах.

С помощью этой команды вы можете просмотреть общую информацию о протоколе ST на коммутаторе. Вы можете просмотреть идентификатор Root, корневой мост и интерфейсные порты коммутатора, а также просмотреть состояния портов интерфейсов коммутатора.

Кроме того, если корневой мост настроен вручную, вы можете проверить значение приоритета коммутатора с помощью этой команды.

![Просмотр состояния протокола STP для vlan 3](image/8.png){#fig:030 width=70%}

2. При помощи какой команды можно узнать, в каком режиме, STP или Rapid PVST+, работает устройство? Приведите примеры вывода подобной информации на устройствах.

При помощи команды `show ru` просмотр текущей конфигурации.

![Команда show ru](image/27.png){#fig:027 width=70%}

3. Для чего и в каких случаях нужно настраивать режим Portfast?

Portfast -- функция, которая позволяет порту пропустить состояния listening и learning и сразу же перейти в состояние forwarding. Настраивается на портах уровня доступа, к которым подключены пользователи или сервера. Цель функции PortFast минимизировать время, которое необходимо для того чтобы порт перешел в состояние forward. Поэтому она эффективна только когда применена к портам, к которым подключены хосты.

4. В чем состоит принцип работы агрегированного интерфейса? Для чего он используется?

Агрегирование каналов — это технология объединения нескольких параллельных каналов передачи данных в сетях Ethernet в один логический. Она позволяет увеличить пропускную способность и повысить надёжность.

Основное применение технологии агрегации — объединение каналов в сетевых коммутаторах. Также можно настроить агрегирование для компьютерных сетевых адаптеров.

5. В чём принципиальные отличия при использовании протоколов LACP (Link Aggregation Control Protocol), PAgP (Port Aggregation Protocol) и статического агрегирования без использования протоколов?

LACP и PAgP - динамические протоколы, управляющие созданием и управлением агрегированных соединений. Статическое агрегирование настраивается вручную без использования протоколов.

6. При помощи каких команд можно узнать состояние агрегированного канала
EtherChannel?

Команды `show etherchannel summary` и `show etherchannel port-channel`.

# Выводы

В результате выполнения лабораторной работы я изучила возможности протокола STP и его модификаций по обеспечению отказоустойчивости сети, агрегированию интерфейсов и перераспределению нагрузки между ними.

# Список литературы{.unnumbered}

::: {#refs}
:::