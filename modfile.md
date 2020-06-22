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

<table>
<thead>
  <tr>
    <th>Команда</th>
    <th>Описание</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><code>INSTALL_VER</code></td>
    <td>Указываем версию установочного файла</td>
  </tr>
  <tr>
    <td><code>INSTALL_GAME</code></td>
    <td>Указываем Тип \ игру для установки (STALKER , UE, Arma, etc) если данная игра присуствует на компьютере то повторная установка не будет </td>
  </tr>
  <tr>
    <td><code>INSTALL_ENGINE</code></td>
    <td>Если в качестве INSTALL_GAME указан STALKER то указываем платформу и через двоеточие патч</td>
  </tr>
  <tr>
    <td><code>FILES</code></td>
    <td>Указываем список файлов для загрузки на клиент с сервера сервиса. Каждый новый файл начинаеться с новой строки</td>
  </tr>
  <tr>
    <td><code>INCLUDE</code></td>
    <td>Указываем подключаеммые файлы *.snf* но так же можно указать, и патчи дополнительной командой <pre>ALL_PATCHES</pre></td>
  </tr>
  <tr>
    <td><code>ACTIONS</code></td>
    <td>Действия с файлами , <a href="#actions-команды"> подробный список команд для ACTION </a>
    <p>Пример<pre>ACTIONS
    FILE gamedata.db_test1; DEST $db/; ACTION move; VERSION 1.0; CRC true; </pre></p>
    </td>
  </tr>
  <tr>
    <td><code>RUN</code></td>
    <td>Указываем какой файл запустить после выполнения всех инструкций, так же можно если вы используете кастомный лаунчер то можно активировать его командой LAUNCHER вместо пути <p>Пример <pre> RUN "$bin/game.exe -key" </pre> </p></td>
  </tr>

</tbody>
</table>

## ACTIONS команды

<table>
<thead>
  <tr>
    <th>Команда</th>
    <th>Описание</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td><code>FILE</code></td>
    <td>Указываем полное название файла с расширением на конце</td>
  </tr>
  <tr>
    <td><code>SRC</code></td>
    <td>Указываем исходнйы путь файла . В файле <b>install.snf</b> не нужен</td>
  </tr>
  <tr>
    <td><code>DEST</code></td>
    <td>Указываем конечный путь</td>
  </tr>
  <tr>
    <td><code>ACTION</code></td>
    <td> <p> Действие с файлом. Доступные действия: </p><p> <ul><li>   move- перенос папки \ файла</li><li>   extract - распаковка архива </li><li>   delete - удаление папки \ файла</li><li>   replace - замена папки \ файла</li></ul></p></td>
  </tr>
    <tr>
    <td><code>VERSION</code></td>
    <td>Указываем версию файла</td>
  </tr>
    <tr>
    <td><code>CRC</code></td>
    <td>Проверяем контрольнные суммы SHA1</td>
  </tr>

</tbody>
</table>



