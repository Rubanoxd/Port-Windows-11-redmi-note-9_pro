# Running Windows on the Redmi Note 9 Pro

<img align="center" src="https://github.com/wormstest/src_vayu_windows/blob/main/2Poco X3 Pro Windows.png" alt="Windows 11 Running On A Poco X3 Pro">

## ⚠️ **Warning**

We're not responsible for bricked devices, missing recovery partitions, dead xiaomi factoryline ~workers~ cowboys, dead microSD cards, dead pmics, dead ram, dead display ics, dead cpus, any xiaomi/poco shenanigans, dead cats or dogs, nuclear wars or you getting fired because you forgot to boot back in to android for the alarm.

This project is in an early stage, all the files here have been contributed by other users, here you will find a guide with the working files we managed to get. This is a delicate process, do it under your own risk and follow all the steps carefully.

**IF YOU AREN'T COMFORTABLE MODDING YOUR PHONE OR ITS PARTITION TABLE OR YOU ARE PARANOID OF BRICKING YOUR DEVICE CLICK AWAY NOW!!! YOU HAVE BEEN WARNED, YOU ARE ON YOUR OWN IF YOU BRICK YOUR DEVICE!!! AGAIN! YOU HAVE BEEN WARNED!!!**

## Project status

Beta. Most of the hardware works, but some components do not work yet.

#### Features

- [ ] Audio ```Only by USB or Bluetooth```
- [x] Battery status
- [x] Bluetooth
- [x] Brightness
- [ ] Camera
- [ ] Charging ```In progress, working partially```
- [x] Display
- [ ] FM
- [x] GPU
- [x] LTE ```Only SIM1; requires provisioning on every boot```
- [ ] SD 
- [x] Touchscreen
- [x] UFS
- [x] USB ```PD hub needed```
- [x] Wi-Fi

#### Sensors
- [x] Accelerometer
- [ ] Fingerprint
- [x] GPS
- [x] Gyroscope
- [x] Light sensor
- [x] Magnetometer
- [x] Proximity


## Guides and requirements

<details> 
<summary><strong>Required Tools/Files</strong></summary>

Human:

- Understand English, Spanish or Russian 

- Understand how to use TWRP

- Understand how to use CMD

- Functioning brain

PC:

- [Windows on ARM image](https://uupdump.net/) (Windows 11 is recommended)

- [platform-tools](https://developer.android.com/studio/releases/platform-tools).

- [DriverUpdater](https://github.com/WOA-Project/DriverUpdater/releases/) to install the [drivers](https://github.com/degdag/Vayu-Drivers/releases/tag/v2.1.0)

Phone:
- [UEFI image](https://github.com/degdag/edk2-msm/releases/tag/V2.1.0)

- [TWRP](https://forum.xda-developers.com/t/recovery-3-4-0-14-miatoll-twrp-xiaomi-redmi-note-9s-9-pro-9-pro-max-poco-m2-pro.4125487/)

</details> 

<details> 

<summary><strong>For people who followed the old guide, broke their partition table or want to uninstall Windows</strong></summary>

- [English](guide/English/restore-stock-en.md)

- [Español](guide/Español/0-transicion-es.md)
 
- [Русский](/guide/Russian/restore-stock-ru.md) 

- [Українська](/guide/Ukrainian/restore-stock-uk.md) 

- [Lietuvių](guide/Lithuanian/restore-stock-lt.md)

</details> 

### Windows installation instructions

<details> 

<summary><strong>English</strong></summary>

1 - [Create partitions](guide/English/1-partition-en.md)

2 - [Install Windows](guide/English/2-install-en.md)
  
</details> 
  
<details> 

<summary><strong>Español</strong></summary>

1 - [Crear particiones](guide/Español/1-particiones-es.md)

2 - [Instalar Windows](guide/Español/2-instalacion-es.md)
  
</details> 

<details> 
  
<summary><strong>Русский</strong></summary>

1 - [Создание разделов](/guide/Russian/1-partition-ru.md)

2 - [Установка Windows](/guide/Russian/2-install-ru.md)
  
</details> 

<details> 

<summary><strong>Українська</strong></summary>

1 - [Створення розділів](guide/Ukrainian/1-partition-uk.md)

2 - [Встановлення Windows](guide/Ukrainian/2-install-uk.md)
  
</details> 

<details> 

<summary><strong>Lietuvių</strong></summary>

1 - [Particijų sukūrimas](guide/Lithuanian/1-partition-lt.md)

2 - [Įdiegti Windows](guide/Lithuanian/2-install-lt.md)
  
</details> 

### Other guides:

<details> 

<summary><strong>English</strong></summary>

- [If you just want to update the drivers follow these commands](guide/English/update-en.md)
  
</details> 

<details> 

<summary><strong>Español</strong></summary>

- [Si solo quieres actualizar los drivers sigue estos comandos](guide/Español/Actualizar-es.md)
  
</details> 

<details> 

<summary><strong>Русский</strong></summary>

- [Если вы хотите обновить драйвера, следуйте этим командам](guide/Russian/update-ru.md)

</details> 

<details> 

<summary><strong>Українська</strong></summary>

- [Якщо ви хочете оновити драйвера, дотримуйтесь цих команд](guide/Ukrainian/update-uk.md)

</details> 

<details> 

<summary><strong>Lietuvių</strong></summary>

- [Jeigu norite atnaujinti tik draiverius, sekite šias komandas](guide/Lithuanian/update-lt.md)
  
</details> 

## Contributors

<details> 

<summary><b><strong>Credits</strong></b></summary>

- [Morc](Https://GitHub.com/themorc) ```Made the vayu images```

- [Icesito68](https://github.com/Icesito68) ```Made Windows partitioning commands and made this repo```

- [Map220v](https://github.com/map220v) ```Provided help and vayu UEFI uses nabu UFS patches and ACPI and also ported mi pad 5 drivers```

- [Degdag](https://github.com/degdag) ```Improves UEFI and ported drivers```

- [halal-beef](https://github.com/halal-beef) ```Built EDK2 and modified it enough to boot Windows, also ported drivers```
  
- [Renegade Project](https://github.com/edk2-porting) ```Making the core of this project```

- [gus33000](https://github.com/gus33000) ```Providing help, also made base install guide, all of the original drivers and the msc script```

- [Renegade Project Discord members](https://discord.gg/XXBWfag) ```Provided Help```
 
- [ArturoGC06](https://github.com/ArturoGC06) ```Helped in the beginning of the project to the translations and gave Windows data```

- [SebastianZSXS](https://github.com/SebastianZSXS) ```Helped to patch Windows PE```

- [MollySophia](https://github.com/MollySophia) ```Helped to fix battery status```

- [haouarihk](https://github.com/haouarihk) ```Great suggestions on the command notes, also made the new guide```

- [bibarub](https://github.com/bibarub) ```Guide improvenents```

- [wormstest](https://github.com/wormstest) ```Russian and Ukrainian translation``` 

- [proganime1200](https://github.com/proganime1200) ```Tremendously helped to make this possible, heavily contirbuted to the old guide by finding bk01-04 partitions and had managed to nearly get winpe booting in the early stages```

</details>  

