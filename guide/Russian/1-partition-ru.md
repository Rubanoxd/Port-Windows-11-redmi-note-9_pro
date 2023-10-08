  <img align="right" src="https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/blob/main/Miatoll.png" width="350" alt="Windows 11 Running On A Redmi Note 9 Pro">


# Запуск Windows на Redmi Note 9 Pro

## Установка

## Разметка телефона

### Необходимые файлы

- [Модифицированный OFOX](https://t.me/c/1868522977/9268)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Notes:
> **Warning** Если вы попытаетесь удалить какой-либо раздел через diskpart, Windows отправит UFS команду, которая ОЧИСТИТ ВСЮ ПАМЯТЬ!!! Не делайте этого.
- Все ваши данные будут удалены! Сохраните важную информацию.
- Все команды были проверены.
- Игнорируйте предупреждения `udevadm`.
- Не запускайте команды дважды.
- НЕ ПЕРЕЗАПУСКАЙТЕ ТЕЛЕФОН если думаете, что совершили ошибку. Обратитесь за помощью в наш [Telegram чат](https://t.me/+S9ne8FTvuoU5M2M1)

#### ⚠️  Не запускайте команды вразброс, вводите их по очереди!

##### ⚠️ НЕ СОВЕРШАЙТЕ ОШИБКИ!!! ВЫ МОЖЕТЕ ОКИРПИЧИТЬ ВАШ ТЕЛЕФОН, ЕСЛИ ОШИБЁТЕСЬ В КОМАНДЕ!!!

##### Запустите модифицированный OrangeFOX
```cmd
fastboot boot <Ofox_A12-FBEv1-miatoll-mod.img>
```

#### Выключите MTP

#### Запустите ADB и утилиту разметки
```cmd
adb shell
```
```sh
parted /dev/block/sda
```


#### Удалите раздел `userdata`
> Вы можете убедиться что 18 это раздел userdata введя команду
>  `print all`
```sh
rm 18
```

#### Создание разделов
> Если у вас всплывает предупреждения которое говорит вам Ignore/Cancel, просто напишите "i" и нажмите Enter

<details>
<summary><b><strong>Для моделей с 64GB памятью</strong></b></summary>

- Создание ESP раздела (Данные Windows bootloader и EFI файлы)
```sh
mkpart esp fat32 11GB 11.4GB
```

- Раздел куда вы установите Windows
```sh
mkpart win ntfs 11.4GB 42.4GB
```
  
- Раздел для Android
```sh
mkpart userdata ext4 42.4GB 59.4GB
```

  </summary>
</details>

<details>
<summary><b><strong>Для моделей с 128GB памятью</strong></b></summary>


- Создание ESP раздела (Данные Windows bootloader и EFI файлы)
```sh
mkpart esp fat32 11GB 11.4GB
```

- Раздел куда вы установите Windows
```sh
mkpart win ntfs 11.4GB 65.4GB
```
  
- Раздел для Android
```sh
mkpart userdata ext4 65.4GB 123GB
```
  </summary>
</details>

#### Сделайте ESP раздел запускаемым, что бы EFI могло обнаружить его
```sh
set 18 esp on
```

#### Выйдите из parted
```sh
quit
```

#### Перезапустите рекавери

#### Снова откройте командную строку телефона
```cmd
adb shell
```

#### Форматирование разделов
-  Форматирование раздела ESP как FAT32
```sh
mkfs.fat -F32 -s1 /dev/block/by-name/esp -n ESPMIATOLL
```

-  Форматирование раздела для Windows как NTFS
```sh
mkfs.ntfs -f /dev/block/by-name/win -L WINMIATOLL
```

- Форматирование Data
Откройте меню форматирование и нажмите Очистить Data, 
и нажмите `да`.

#### Проверьте запускается ли Android
Перезапустите телефон и вы должны увидить что Android всё ещё работает.


## [Следующий этап: Установка Windows](/guide/Russian/2-install-ru.md)
