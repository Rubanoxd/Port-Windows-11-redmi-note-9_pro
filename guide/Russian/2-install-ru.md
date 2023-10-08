  <img align="right" src="https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/blob/main/Miatoll.png" width="350" alt="Windows 11 Running On A Redmi Note 9 Pro">


# Запуск Windows на Redmi Note 9 Pro

## Установка Windows
> Проверьте что MTP выключено!

### Подготовка

- [Windows ARM образ (Windows 11 is recommended)](https://uupdump.net/)
- [Готовый образ Windows ARM](https://sourceforge.net/projects/foxgsi/files/winGSI.img/download)
- [Образ UEFI](https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/releases/tag/Release)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/Icesito68/7xx-Drivers)

#### Запустите msc скрипт

```cmd
adb shell msc.sh
```

  

### Установка точек монтирования для разделов
  

#### Запустите управление дисками Windows 
> Как только SM6250 будет обнаружен как диск:

```cmd
diskpart
```


### Установите `X` как точку монтирования для раздела Windows

#### Выберите Windows раздел телефона
> Используйте `list volume` что бы найти его, он назван "WINMIATOLL"

```diskpart
select volume <number>
```

#### Установите точку монтирования X
```diskpart
assign letter=x
```

### Установите `Y` как точку монтирования для ESP

####  Выберите ESP раздел телефона
> Используйте `list volume` что бы найти его, он назван "ESPMIATOLL"

```diskpart
select volume <number>
```

#### Установите точку монтирования Y

```diskpart
assign letter=y
```

#### Выйдите из diskpart
```diskpart
exit

```

  
  

### Установка

> Вместо `путь\install.wim` введите путь install.wim,

> `install.wim` расположен в папке /sources ISO образа
> (Он также может быть назван `install.esd`)
> Вы должны монтировать или распаковать ISO образ что бы найти его

```cmd
dism /apply-image /ImageFile:путь\install.wim /index:1 /ApplyDir:X:\
```


### Установка драйверов

> Вместо `<miatollriversfolder>` укажите путь к папке с драйверами (miatoll-Drivers-Full)

```cmd
driverupdater.exe -d <miatolldriversfolder>\definitions\Desktop\ARM64\Internal\miatoll.txt -r <miatolldriversfolder> -p X:
```



### Создайте файлы для загрузчика

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

  
  

## Разрешить неподписанные драйверами

> Без этого вы словите BSOD при загрузке

```cmd
bcdedit /store Y:\EFI\Microsoft\BOOT\BCD /set {default} testsigning on
```

## Запуск Windows

### Перекиньте `<uefi.img>` на память телефона

```cmd
adb push <uefi.img> /sdcard
```

#### Вы можете использовать SD-карту

```cmd
adb push <uefi.img> /external_sd
```


### Не забудьте сделать бекап оригинального boot.img
> Вам нужно это сделать один раз
> Перекиньте на SD-карту если возможно

### Зашейте UEFI образ в BOOT
Зашейте `uefi.img` файл в BOOT раздел

## Запуск Android
> Восстановите копию оригинального boot.img

## Успех!
