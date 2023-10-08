<img align="right" src="https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/blob/main/Miatoll.png" width="350" alt="Windows 11 Running On A Redmi Note 9 Pro">


# Запуск Windows на Redmi Note 9 Pro

## Обновление драйверов

### Необходимые файлы

- [Модифицированный OFOX](https://t.me/c/1868522977/9268)
- [Образ UEFI](https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/releases/tag/Release)
- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/latest)
- [Drivers](https://github.com/Icesito68/7xx-Drivers)

##### Запустите модифицированный OrangeFOX
```cmd
fastboot boot <Ofox_A12-FBEv1-miatoll-mod.img>
```

#### Запустите скрипт
```cmd
adb shell msc.sh
```

### Установка драйверов

> Вместо `<miatollriversfolder>` укажите путь к папке с драйверами (miatoll-Drivers-Full)

```cmd
driverupdater.exe -d <miatolldriversfolder>\definitions\Desktop\ARM64\Internal\miatoll.txt -r <miatolldriversfolder> -p X:
```

## Готово!