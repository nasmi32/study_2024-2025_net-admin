---
## Front matter
title: "Доклад на тему: Средство моделирования Mininet. Установка и пример моделирования."
subtitle: "Дисциплина: Администрирование локальных сетей"
author: "Мищина Анастасия Алексеевна"

## Generic otions
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
fontsize: 12pt
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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

# Введение

Mininet — это мощный инструмент для эмуляции сетей, который широко используется для тестирования и разработки SDN-приложений. Поскольку Mininet изначально разработан для Linux-систем, его использование на Windows требует некоторых дополнительных шагов, таких как настройка виртуальной машины и установка вспомогательного программного обеспечения. В этом докладе мы рассмотрим процесс установки и настройки Mininet на Windows, начиная с загрузки образа виртуальной машины и заканчивая обновлением Mininet до последней версии.

# Установка и настройка Mininet

## Настройка образа Mininet

Перейдем к настройке образа Mininet, который можно скачать по ссылке с официального сайта Mininet. Образ виртуальной машины, который мы используем, — это `mininet-2.3.0-210211-ubuntu-20.04.1-legacy-server-amd64-ovf`. Импортируем его в VirtualBox: "Файл" -> "Импорт конфигурации" и указываем путь к файлу `.ovf`. После импорта важно настроить сетевые параметры виртуальной машины: выбираем виртуальный адаптер хоста и добавляем дополнительный сетевой адаптер типа **Host-only Network**. Второй адаптер позволит нам подключаться к виртуальной машине с хостовой системы (Windows) через SSH.

## Подключение к виртуальной машине

После настройки VirtualBox запускаем виртуальную машину. При первом запуске система запросит логин и пароль. Используем стандартные учетные данные:

- Логин: `mininet`
- Пароль: `mininet`

После входа в систему необходимо определить IP-адрес виртуальной машины с помощью команды `ifconfig`. Внутренний адрес машины будет иметь вид `192.168.x.y`, в моем случае `192.168.56.102`. Этот адрес понадобится для подключения к виртуальной машине с хостовой системы.

Для удобства работы настроим SSH-подключение. С хостовой машины (Windows) открываем терминали и подключаемся к виртуальной машине с помощью команды:

```bash
ssh -Y mininet@192.168.x.y
```

## Настройка XTerm

Mininet активно использует графические приложения, такие как XTerm, для отображения терминалов виртуальных сетевых узлов. Однако по умолчанию XTerm использует растровые шрифты малого размера, что может затруднить чтение. Для улучшения читаемости перейдем на векторные шрифты и увеличим их размер.

Для этого редактируем файл конфигурации XTerm, который находится по пути `/etc/X11/app-defaults/XTerm`. Добавляем в него следующие строки:

```bash
xterm*faceName: Monospace
xterm*faceSize: 14
```

Здесь мы выбрали моноширинный шрифт с размером 14 пунктов. После сохранения изменений все новые окна XTerm будут использовать указанные настройки.

## Настройка X11 для суперпользователя

При попытке запуска графических приложений от имени суперпользователя (например, с использованием `sudo`) может возникнуть ошибка:

```
X11 connection rejected because of wrong authentication.
```

Эта ошибка связана с тем, что X-соединение устанавливается от имени пользователя `mininet`, а приложение запускается от имени `root`. Чтобы исправить эту проблему, необходимо скопировать значение куки (MIT magic cookie) из пользователя `mininet` в файл для пользователя `root`.

Для этого выполняем следующие шаги:

1. В терминале виртуальной машины выполняем команду:

   ```bash
   xauth list $DISPLAY
   ```

   Эта команда покажет значение куки для текущего сеанса.

2. Переходим в режим суперпользователя:

   ```bash
   sudo -i
   ```

3. Добавляем куку для пользователя `root`:

   ```bash
   xauth add mininet-vm/unix:10  MIT-MAGIC-COOKIE-1  <ваше_значение_куки>
   ```

После этого графические приложения запускаются без ошибок.

## Работа с Mininet из-под Windows

Для работы с Mininet на Windows необходимо установить X-сервер, который будет отображать графические приложения, запущенные на виртуальной машине. Одним из популярных вариантов является **VcXsrv Windows X Server**. Его можно установить через Chocolatey, выполнив команду:

```bash
choco install vcxsrv
```

После установки запускаем XLaunch и настраиваем его для работы с Mininet. Выбираем опции:

- Multiple windows;
- Display number: -1;
- Start no client.

Для подключения к виртуальной машине используем SSH-клиент, например, Putty. В настройках Putty включаем опцию "Enable X11 forwarding" в разделе "Connection" -> "SSH" -> "X11". Это позволит перенаправлять графические приложения с виртуальной машины на хост.

## Обновление Mininet

Для обновления Mininet до последней версии необходимо сначала настроить доступ к интернету на виртуальной машине. Для этого в VirtualBox добавляем интерфейс NAT и активируем его в виртуальной машине с помощью команды:

```bash
sudo dhclient eth1
```

После этого переименовываем текущую директорию Mininet:

```bash
mv ~/mininet ~/mininet.orig
```
И скачиваем новую версию Mininet из репозитория:

```bash
cd ~
git clone https://github.com/mininet/mininet.git
```
Затем переходим в директорию Mininet и выполняем установку:

```bash
cd ~/mininet
sudo make install
```

# Практическая часть

Построим сеть, состоящую из

# Заключение

Установка и настройка Mininet на Windows — это многоэтапный процесс, который требует внимательности и понимания основных принципов работы виртуальных машин и сетей. Однако, после правильной настройки, Mininet становится мощным инструментом для тестирования и разработки SDN-приложений. Обновление Mininet до последней версии позволяет использовать новые функции и исправления, что делает процесс разработки более эффективным и удобным.

# Список литературы{.unnumbered}

::: {#refs}
:::
