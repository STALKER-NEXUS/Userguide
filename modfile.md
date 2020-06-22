# Stalker Nexus File
## <a href="README.md"> На главную </a>
#### Скриптовый файл для лаунчера STALKER-NEXUS

## Краткая информация
Файл написан для удосбства разработчиков и удобной адаптации мода под наш сервис
На данный момент имеються 3 *snf* файла которые различаються частью команд:
- **install.snf** - файл установки модификации
- **patch.snf** - файл установки патча для модификации
- **run.snf** - файл запуска модификации

## Синтаксис
 Расмотрим файл *install.snf*
 ```dockerfile
 # comment
 
INSTALL_VER 1.0

INSTALL_GAME STALKER

INSTALL_ENGINE shoc:1.0004

FILES
    gamemoda.db_test1
    gamemoda.db_test2
    gamemoda.db_test3
    gamemoda.db_test4
    gamemoda.db_test5
    bin.zip
    custom.zip
    
INCLUDE ALL_PATCHES

ACTIONS
    FILE gamedata.db_test1; DEST $db/; ACTION move; VERSION 1.0; CRC true; 
    FILE gamedata.db_test2; DEST $db/; ACTION move; VERSION 1.0; CRC true; 
    FILE gamedata.db_test3; DEST $db/; ACTION move; VERSION 1.0; CRC true; 
    FILE gamedata.db_test4; DEST $db/; ACTION move; VERSION 1.0; CRC true; 
    FILE gamedata.db_test5; DEST $db/; ACTION move; VERSION 1.0; CRC true; 
    FILE bin.zip; DEST $bin/; ACTION extract; VERSION 1.0; CRC true; 
    FILE custom.zip; DEST $custom/; ACTION extract; VERSION 1.0; CRC true; 
 ```
__Внимание__  синтаксис чувствителен к табуляции и регистру!

## Основные команды
| Команда      |   Описание         | 
| ------------- |-------------| 
| INSTALL_VER   | Указываем версию установочного файла | 
| INSTALL_GAME  | Указываем Тип \ игру для установки (STALKER , UE, Arma, etc) если данная игра присуствует на компьютере то повторная установка не будет  | 
| INSTALL_ENGINE  | Если в качестве INSTALL_GAME указан STALKER то указываем платформу и через двоеточие патч      |
| FILES | Указываем список файлов для загрузки на клиент с сервера сервиса. Каждый новый файл начинаеться с новой строки|
|INCLUDE|Указываем подключаеммые файлы *.snf* но так же можно указать, и патчи дополнительной командой ALL_PATCHES|
|ACTIONS|Действия с файлами , <a href="#actions-команды"> подробный список команд для ACTION </a> |
|||
## ACTIONS команды

| Команда      |   Описание         | 
| ------------- |-------------| 
|FI:E||
|DEST||
|SRC||
|ACTION||
|VERSION||
|CRC||