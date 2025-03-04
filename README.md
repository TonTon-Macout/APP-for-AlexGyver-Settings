
# APP-for-AlexGyver-Settings
Виндовс приложение для поиска и отображения вебморды устройств с установленной библиотекой [Settings AlexGyver](https://github.com/GyverLibs/Settings) <br><br>
Программа написанна на Python, exe можно собрать самому из скрипта, [инструкция ниже ↓](#compiler)<br> 
Или скачать zip-архив с скомпилированным exe и иконками, [последняя версия  ↓](#relise)<br><br>
Для запуска exe файла установка не требуется, поместите его со всеми иконками в удобную вам папку и пользуйтесь<br> <br>
При первом старте если включен защитник, система предупредит о неопознаном издателе, нужно нажать дополнительно -> выполнить в любом случае, ну или собирать exe самостоятельно<br><br>
При обновлении можно просто заменить exe файл на новый, все настройки сохранятся (если обратное не указано в сведении о новой версии) 
<br>

![Снимок экрана 2025-02-21 001827](https://github.com/user-attachments/assets/8ed7cbc6-779f-4c44-bbec-a7e77492f784)

## Возможности приложения:
+ поиск и отображение устройств в локальной сети с  установленной библиотекой  Settings AlexGyver <br>
  - тестировано на библиотеке  Settings v1.2.5, v1.3.1
+ поиск и отображение устройств с [WLED](https://github.com/wled/WLED?ysclid=m7q4g9kdu7478403852) 
+ переключается с одного устройства на другое из окна сканирования или из меню по правой кнопке
+ можно установить поверх всех окон
+ если устройство недоступно покажет плашку и будет проверять доступность раз в 5 секунд
+ цвет рамки зависит от цвета выбранного акцента
  -  начиная с версии Settings v1.2.5 можно выбрать цвет акцента (см. документацию на сеттингс) ``` sett.config.theme = sets::Colors::Violet;```
  -  полезно когда надо быстрее отличать похожие устройства 
+ что-то там еще умеет тоже, смотри изменения в [версиях  ↓](#relise)
  
после запуска программа создаст в той же папке где находится<br>
+ папки кеша и данных браузера
+ после сканирования файл discovered_devices.json куда записываются имена и ip адреса найденных устройств<br> после создания файла в контекстном меню и выпадабщем списке адреса устройства будет доступен выбор найденных устройств
+ settings.json где хранятся настройки
+ subnet_history.json куда записываются все найденые подсети
<br> 

```
/* ДИСКЛЕЙМЕР */
Я не программист, любитель, питон знаю плохо
Программа написана наполовину с искусственными мозгами
Найдете баг - пишите, постараюсь исправить. 
А если знаете как исправить, то пишите тем более =) 
/* КОНЕЦ ДИСКЛЕЙМЕРА */
```
<br>

<h2 id="relise"  > Версии </h2>

ссылка на последнюю версию программы [Settings_app.zip](https://github.com/TonTon-Macout/APP-for-AlexGyver-Settings/releases/latest/download/Settings_app.zip)<br> <br> 
+ v.0.2.1
  - накинул немного акцентных цветов в интерфейсе, обновил и добавил новые иконки, теперь должно смотреться симпотней
  - если на гитхабе есть новая версия, в контекстном меню появится пункт ведущий на страницу релиза
  - за правый нижний угол можно изменить размер
  - в окне сканирования теперь можно изменить найденные устройства или добавить новое вручную
+ v0.2.0
  - добавил поиск устройств с WLED
    -  по умолчанию поиск включен, можно отключить в настройках 
  - добавил в настройки установку акцентного цвета по умолчанию 
    - если на загруженной странице не нашелся акцентный цвет, например если это WLED, то цвета будут применяться из настроек по умолчанию 
    - так же добавил галку "свои цвета всегда", при активации которой цвета рамки и фона всегда будут применяться из настроек 
  -  еще некотрые мелкие улучшения
+ v0.1.0
  - добавлен пункт настройки в контекстное меню
  - исправлен размер окна на небольших экранах
    -  теперь размер окна зависит от разрешения экрана
    - если все же вам не нравится предложенный размер и масштаб, его можно изменить в настройках
  - исправлены цвета
    - если включена светлая тема то некоторые поля были не видны (исправлено) 
    - добавлено применение акцентного цвета  к некоторым частям интерфейса 
  - обновлена логика определения маски подсети
    - теперь она должна определяться правильно, даже если вы послали ркн на три всем известные буквы 
    - также добавлен выпадающий список со всеми найденными сетями
  - добавлен список устройств в выпадающем списке в строке адреса 
    - в списке отображаются все найденные устройства по клику переходим на него
    - можно переключить что показывать в этом списке и строке адреса, имя устройства или адрес (в настройках) 
  - упразднен файл last_url.txt 
    - теперь последнее устройство всегда первое в списке discovered_devices.json 

+ v0.08 
  + больше не крашится если ввести неверную маску подсети
  + цвет фона в приложении зависит от цвета фона в веб интерфейсе, теперь будет лучше смотреться в светлой теме и в кастомной 
+ v0.07 
  + добавил автоопределение локальной подсети
<br>

## Известные ~~баги~~ ~~фичи~~ особенности 

+ если скрыть приложение и развернуть, появляется строка с заголовком винды на фоне приложения
  + на сколько я понял это баг библиотеки Qt и на данный момент не исправим
  + но исправления уже приняты и будут применены в будущих версиях, в какой точно хз, вероятно 5.10 (сейчас актуальная 5.8) https://codereview.qt-project.org/c/qt/qtbase/+/598187
  + как только выйдет версия с исправленым багом, приложуху обновлю
  + а пока можно после разворачивания щелкнуть чекбокс поверх экрана или строку с адресом устройства и окно исчезнет
+ наверно есть и чтото еще, но я об этом не вкурсе
<br>
<h2 id="compiler">Запуск и сборка exe файла</h2>


+ для запуска скрипта или сборки exe файла необходим [python](https://www.python.org/downloads/), я тестировал на версии 3.13 
+ кириллицы в пути лучше избегать
+ теперь последняя версия скрипта всегда всегда будет иметь имя  Settings_app.py, для удобства сборки
+ добавил батник build_Settings.exe.bat который проверит наличие иконок, скомпилирет exe и поместит его в отдельную папку со всеми необходимыми иконками, а в конце подчистит за собой и сборщиком (должны быть установлены пайтон и библиотеки
+ для ручной сборки или запуска скрипта
  + если нет python'а - установить не ниже 3 , открыть терминал -> скопировать команду -> ентер
  + после установки python, перейти в папку где расположен скрипт 
  + правкой кнопкой на пустом месте -> открыть в терминале -> скопировать команду -> энтер
  

установить библиотеки<br>
```pip install PyQt6 requests ipaddress psutil PyQt6-WebEngine```

запуск скрипта<br>
```python Settings_app.py```

сборка exe --- иконки должна лежать в той же папке где и скрипт<br>
```pyinstaller --onefile --windowed --icon=icon.ico Settings_app.py```

собирётся экзешник в папке dist, 
рядом с exe в ту же папку нужно положить все файлы иконок <br>



## 

![Снимок экрана 2025-03-05 010612](https://github.com/user-attachments/assets/e71e5cc5-4f01-4222-a0e7-28040ea85a1f)
