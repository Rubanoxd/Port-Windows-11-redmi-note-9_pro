<img align="right" src="https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/blob/main/Miatoll.png" width="350" alt="Windows 11 Running On A Redmi Note 9 Pro">


# Запуск Windows на Redmi Note 9 Pro

## Удаление

### Зачем оно нужно?



Если вы хотите удалить windows, это используется вместо удаления разделов вручную, чтобы избежать человеческих ошибок + написания целого руководства, посвященного только удалению.
Если вы хотите разблокировать загрузчик, вам потребуется, чтобы таблица разделов была стоковой.

### Нужные файлы

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)
- [gpt_both0.bin](https://github.com/Rubanoxd/Port-Windows-11-redmi-note-9_pro/releases/tag/Binaries)

### Восстановите GPT
> Вместо ```<gpt_both0.bin>``` введите путь gpt_both0.bin файла.

```cmd
fastboot flash partition:0 <gpt_both0.bin>
```

### Форматирование DATA, что бы избежать бутлупов и вернуть стоковый размер 
```cmd
fastboot -w
```
