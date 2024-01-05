# var-som-mx6-notes

Собственный опыт и наблюдения по [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/).

## Содержание

- [var-som-mx6-notes](#var-som-mx6-notes)
  - [Содержание](#содержание)
    - [1. Зачем оно нужно?](#1-зачем-оно-нужно)
    - [2. Содержимое папок репозитория](#2-содержимое-папок-репозитория)
      - [2.1 `./docs`](#21-docs)
      - [2.2 `./debs`](#22-debs)
    - [4. Полезные ссылки для `var-som-mx6`](#4-полезные-ссылки-для-var-som-mx6)
      - [4.1 Официальные источники Variscite](#41-официальные-источники-variscite)
      - [4.2 Внешние материалы](#42-внешние-материалы)
    - [5. Заметки по `var-som-mx6`](#5-заметки-по-var-som-mx6)
      - [5.1 Общие заметки](#51-общие-заметки)
      - [5.2 Заметки по компиляции ОС и ядра](#52-заметки-по-компиляции-ос-и-ядра)
      - [5.3 Заметки по обновлению и переносу системы на EMMC память](#53-заметки-по-обновлению-и-переносу-системы-на-emmc-память)
    - [6. Первичная настройка Debian 9 на `var-som-mx6`](#6-первичная-настройка-debian-9-на-var-som-mx6)
      - [6.1 Подключение по SSH](#61-подключение-по-ssh)
      - [6.2 Установка `sudo` и добавление пользователя в его группу](#62-установка-sudo-и-добавление-пользователя-в-его-группу)
      - [6.3 Установка русского языка](#63-установка-русского-языка)
      - [6.4 Установка основных пакетов](#64-установка-основных-пакетов)
      - [6.5 Добавление пользователя в группу `input` (может понадобится для управления устройствами ввода)](#65-добавление-пользователя-в-группу-input-может-понадобится-для-управления-устройствами-ввода)
      - [6.6 Установка `PyQt5` и `qml` через `apt`](#66-установка-pyqt5-и-qml-через-apt)
      - [6.7 Настройка синхронизации времени и часового пояса](#67-настройка-синхронизации-времени-и-часового-пояса)

### 1. Зачем оно нужно?

В данном репозитории собрана разнообразная информация
по [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/).

### 2. Содержимое папок репозитория

#### 2.1 `./docs`

- `variwiki-RELEASE_STRETCH_V2-0_VAR-SOM.pdf` - pdf-версия [мануала сборки Debian 9 Stretch R02 с ядром 4.9.88](https://variwiki.com/index.php?title=Debian_Build_Release&release=RELEASE_STRETCH_V2.0_VAR-SOM-MX6);
- `variwiki-RELEASE_THUD_V1-0_VAR-SOM-MX6.pdf` - pdf-версия [мануала сборки Yocto Thud с ядром 4.14.78](https://variwiki.com/index.php?title=Yocto_Build_Release&release=RELEASE_THUD_V1.0_VAR-SOM-MX6);
- `Hardware` - различная документация и схемы по [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/).

#### 2.2 `./debs`

Некоторые `.deb` пакеты, что бы не терялись.

- `touchegg_2.0.12_armhf.deb` - [touchegg](https://github.com/JoseExposito/touchegg). Со временем, пакет может устареть.
- `libts0_1.19-1_armhf.deb` - зависимость [tslib 1.22](https://github.com/libts/tslib/releases/tag/1.22).
- `libts-bin_1.19-1_armhf.deb` - зависимость [tslib 1.22](https://github.com/libts/tslib/releases/tag/1.22).

### 4. Полезные ссылки для [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/)

#### 4.1 Официальные источники Variscite

- [4.1 Стартовый мануал](https://variwiki.com/index.php?title=VAR-SOM-MX6_Start_Here);
- [4.2 Unit Testing (некоторая информация по конфигурациям)](https://variwiki.com/index.php?title=VAR-SOM-MX6_Yocto_Unit_Testing_V9);
- [4.3 Хаб прошивок](https://variwiki.com/index.php?title=VAR-SOM-MX6);
- [4.4 Мануал по сборке Yocto Thud с ядром 4.14.78](https://variwiki.com/index.php?title=Yocto_Build_Release&release=RELEASE_THUD_V1.0_VAR-SOM-MX6);
- [4.5 Мануал по сборке Debian 9 Stretch R02 с ядром 4.9.88](https://variwiki.com/index.php?title=Debian_Build_Release&release=RELEASE_STRETCH_V2.0_VAR-SOM-MX6);
- [4.7 Изменение лого загрузки](https://variwiki.com/index.php?title=Yocto_Linux_logo);
- [4.8 Интеграция Docker в Yocto Thud с ядром 4.14.78](https://variwiki.com/index.php?title=Docker_Guide&release=RELEASE_THUD_V1.0_VAR-SOM-MX6);
- [4.10 FTP-сервер Variscite с некоторой документацией и сборками ОС](ftp://customerv@ftp.variscite.com/VAR-SOM-MX6/);
- [4.11 Репозиторий Variscite на GitHub](https://github.com/varigit);
- [4.9 Репозиторий Yocto Dunfell v1.0 release for VAR-SOM-MX6 на GitHub](https://github.com/varigit/variscite-bsp-platform/releases/tag/dunfell-fslc-4.4-2.1.x-mx6-v1.0);
- [4.12 Variscite Debian with Linux release](https://variwiki.com/index.php?title=Debian_Build_Release&release=RELEASE_STRETCH#VAR-SOM-MX6).

#### 4.2 Внешние материалы

- [4.6 Добавление работы UART port (USB to UART support)](https://www.imx6rex.com/software/imx6-rex-basic-hw-verification-tests/#usb_to_uart);
- [4.13 Ubuntu Bionic 18.04.3 LTS для плат i.MX6 с ускорением графического процессора etnaviv - январь 2020 г. (основное ядро ​​5.4.6) (Boundary Devices)](https://boundarydevices.com/ubuntu-bionic-18-04-3-lts-for-i-mx6-7-boards-with-etnaviv-gpu-acceleration-january-2020-mainline-kernel-5-4-6/);
- [4.14 U-Boot 2020.10 для платформ i.MX (Boundary Devices)](https://boundarydevices.com/u-boot-2020-10-for-i-mx-platforms/).

### 5. Заметки по [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/)

#### 5.1 Общие заметки

- [`Docker-ce` не работает на Debian 9 Stretch (проверено)](https://github.com/docker/for-linux/issues/275);
- `OpenGL` странно работает в `PyQt5` (скорее не работает);
- Еще один способ завести multitouch touchscreen - [touchegg](https://github.com/JoseExposito/touchegg).
  Конфигурация на свое усмотрение. Zoom жест так и не завелся, но работает вызов контекстного меню по жесту двух пальцев.
  На Debian 9 пришлось ставить вручную, устанавливая локальные `.deb` пакеты.
- Проверку сенсора удобно проверять с помощью [tslib](https://github.com/libts/tslib).
  Рабочий вариант - собрать из исходников и установить требуемые зависимости локальными `.deb` пакетами.

  Первым делом нужно будет выполнить калибровку экрана:

  ```sh
  ts_calibrate
  ```

  После выполнения калибровки должен появится файл `/etc/pointercal`. У меня он появился не по этому пути, а по пути `/usr/local/etc/pointercal`.
  Если так случилось, нужно скопировать найденный `pointercal` в `/etc/pointercal`.
  Вариант поиска файла `pointercal`:

  ```sh
  sudo find / -name pointercal
  ```

  После калибровки можно проверит работу сенсорного экрана.

  Для сенсорного экрана в одно касание:

  ```sh
  sudo ts_test
  ```

  Для сенсорного экрана с поддержкой multitouch:

  ```sh
  sudo ts_test_mt
  ```

#### 5.2 Заметки по компиляции ОС и ядра

- Для включения использования дисплея по LVDS необходимо редактировать файл
  `./debian_var-som-mx6/src/kernel/arch/arm/boot/dts/imx6qdl-var-mx6cb-rdisplay.dtsi`:

  Пример подключения [Mitsubishi Electric AT104XH11](https://ru.mouser.com/ProductDetail/Mitsubishi-Electric/AT104XH11?qs=wd5RIQLrsJigeWhrNc%2FHwg==):

  ```conf
  ...
  lvds-channel@1 {
    fsl,data-mapping = "spwg";
    fsl,data-width = <24>;
    status = "okay";

    primary;

    display-timings {
      native-mode = <&timing1>;
      timing1: hsd100pxn1 {
        clock-frequency = <38251000>;
        hactive = <1024>;
        vactive = <768>;
        hback-porch = <112>;
        hfront-porch = <32>;
        vback-porch = <3>;
        vfront-porch = <17>;
        hsync-len = <80>;
        vsync-len = <4>;
      };
    };
  };
  ...
  ```

- Если хочется, что бы конфиг сборки ядра не менялся перед сборкой с помощью скрипта Variscite, можно закомментировать 2 строки файла
  `./debian_var-som-mx6/make_var_som_mx6_debian.sh` в функциях `make_kernel()` и `make_kernel_modules()`:

  ```sh
  ...
  make ARCH=arm CROSS_COMPILE=${1} ${G_CROSS_COMPILER_JOPTION} -C ${4}/ ${2}
  ...
  make ARCH=arm CROSS_COMPILE=${1} ${G_CROSS_COMPILER_JOPTION} -C ${3} ${2}
  ...
  ```

- Для конфигурации сборки ядра в ручную с помощью `make menuconfig` можно выполнить в консоли 2 команды:

  ```sh
  cd ./debian_var-som-mx6/src/kernel/
  make menuconfig
  ```

- Местоположение сгенерированного файла сборки ядра: `./debian_var-som-mx6/src/kernel/.config`;

- Заставить работать сенсор PM1310 через USB удалось с помощью редактирования `./debian_var-som-mx6/src/kernel/.config`:

  ```conf
  CONFIG_HID=y
  CONFIG_HIDRAW=y
  CONFIG_HID_GENERIC=y
  CONFIG_HID_MULTITOUCH=y
  ```

  Спасибо за это некому **Simon Yeh 葉尚智** из [amtouch.com](https://www.amtouch.com/).

  Скорее всего, это заставить работать другие multitouch-сенсоры, если они уже включены исходный в код ядра.

  Связные флаги:
  - `CONFIG_TOUCHSCREEN_PENMOUNT` => PenMount RS-232;
  - `CONFIG_HID_PENMOUNT` => PenMount 6000 USB Driver.

- К слову, у PM1310 в X.org неплохо работает multitouch с драйвером `wacom`. Пример конфигурации `/usr/share/X11/xorg.conf.d/40-libinput.conf`:

```conf
...
Section "InputClass"
        Identifier "libinput touchscreen catchall"
        MatchProduct "PenMount PM1310|PM1310|1310|14e1:3508|HID 14e1:3508"
        MatchIsTouchscreen "on"
        MatchDevicePath "/dev/input/event*"
        Driver "wacom"
EndSectio
...
```

#### 5.3 Заметки по обновлению и переносу системы на EMMC память

- Обновление Debian 9 => Debian 10 => Debian 11 возможно.
  На каждом этапе необходимо убедится, что система полностью обновлена:

  ```sh
  sudo apt update
  sudo apt upgrade
  sudo apt dist-upgrade
  ```

  После в файле `/etc/apt/sources.list` необходимо заменить все вхождения:
  - Для Debian 9 => Debian 10: `stretch` на `buster`;
  - Для Debian 10 => Debian 11: `buster` на `bullseye`.

  После изменений в файле выполнить оновление системы:

  ```sh
  sudo apt update
  sudo apt upgrade
  sudo apt dist-upgrade
  ```

  Проверялось лишь поэтапное обновление системы. Обновление Debian 9 => Debian 11 не проверялось.
- При выполнении скрипта `/usr/sbin/debian-install.sh` для переноса системы на EMMC выполняется перенос не той системы, которая установлена на SD-карте.
  Будет скопирован текущий образ ядра и установлена система, лежащая по пути `/opt/images/Debian/rootfs.tar.gz`.

  Это изеачальный скомпелированный Debian 9.
  Попытка подменить `rootfs.tar.gz` перед выполнением скрипта возможна, но потерпела неудачу - система после этого не стартовала.

### 6. Первичная настройка Debian 9 на [`var-som-mx6`](https://www.variscite.com/product/system-on-module-som/cortex-a9/var-som-mx6-cpu-freescale-imx6/)

#### 6.1 Подключение по SSH

`OpenSSH`-сервер в Debian 9 включен по умолчанию. Пароль от пользователя `root` по умолчанию: `root`.
Также, по умолчанию, есть обычный пользователь `x_user`. Его пароль по умолчанию не найден, но легко меняется через `passwd`.

#### 6.2 Установка `sudo` и добавление пользователя в его группу

```sh
apt upgrade && apt install sudo
usermod -aG sudo x_user
```

#### 6.3 Установка русского языка

```sh
sudo ln -s /etc/locale.alias /usr/share/locale/locale.alias
sudo dpkg-reconfigure locales
```

После выбрать `ru_RU UTF-8 UTF-8` и `en_EN UTF-8 UTF-8`, по умолчанию выбрать `ru_RU UTF-8 UTF-8`.

#### 6.4 Установка основных пакетов

```sh
sudo apt install bash-completion mc neofetch htop curl git software-properties-common xinput
```

После установки включить `bash_completion` добавлением в файл `~/.bashrc` строк:

```sh
if [ -f /etc/bash_completion ]; then
 . /etc/bash_completion
fi
```

#### 6.5 Добавление пользователя в группу `input` (может понадобится для управления устройствами ввода)

```sh
sudo gpasswd -a $USER input
```

#### 6.6 Установка `PyQt5` и `qml` через `apt`

```sh
sudo apt install python3-pyqt5 python3-pyqt5.qtquick python3-pyqt5.qtpositioning qml-module-qtlocation qml-module-qtpositioning qml-module-qtquick-controls
```

#### 6.7 Настройка синхронизации времени и часового пояса

Выбор часового пояса (в данном случае, UTC+3)

```sh
sudo timedatectl set-timezone Europe/Moscow
```
