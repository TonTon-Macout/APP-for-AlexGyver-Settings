
# APP-for-AlexGyver-Settings
Виндовс приложение для поиска и отображения вебморды устройств с установленной библиотекой [Settings AlexGyver](https://github.com/GyverLibs/Settings) 

Возможности приложения:
+ поиск и отображение устройств в локальной сети с  установленной библиотекой  Settings AlexGyver <br>
тестированно на библиотеке  Settings v1.2.5
+ переключается с одного устройства на другое из окна сканирования или из меню по правой конпке
+ можно установить поверх всех окон
+ если устройство недоступно покажет плашку и будет проверять доступность раз в 5 секунд
+ цвет рамки зависит от цвета выбранного акцента <br>начиная с версии Settings v1.2.5 можно выбрать цвет акцента (см. документацию на сеттингс)<br>``` sett.config.theme = sets::Colors::Violet;```<br> полезно когда надо быстрее отличать похожие устройства
+ что-то там еще умеет тоже
  
после запуска программа создаст в тойже папке где находится<br>
+ папки кеша и данных браузера
+ файл last_url.txt куда записывается ip адрес последнего открытого устройства
+ а после сканирования файл discovered_devices.json куда записываются имена и ip адреса найденых устройств


/* ДИСКЛЕЙМЕР */<br>
Я не программист, питон знаю плохо, и еще хуже фреймворк PyQt6 интерфейса<br>
Программа написана наполовину с исскуственными мозгами<br>
Найдете баг - пишите, постараюсь исправить. <br>
А если знаете как исправить, то пишите тем более =) <br>

Файл .exe получается под 150 мегабайт, сюда не влазит <br> 
в последствии загружу на какойнибудь файлообменник <br> 
для сборки или запуска скрипта нужно установить питон, подробности ниже

/* конец дисклеймера */<br>

+ для запуска скрипта или сборки exe файла необходим последний [python](https://www.python.org/downloads/), я тестировал на версии 3.13 
+ после установки python, перейти в папку где расположен скрипт 
+ правкой кнопкой -> открыть в терминале -> скопировать команду -> энтер
+ кириллицы в пути лучше избегать

установить библиотеки<br>
```pip install PyQt6 requests ipaddress```

запуск скрипта<br>
```python Settings_app_v0.06.py```

сборка exe --- иконка должна лежать в той же папке где и скрипт<br>
```pyinstaller --onefile --windowed --icon=icon.ico Settings_app_v0.06.py```

собирётся экзешник в папке dist 
рядом нужно положить все файлы иконок 

![Снимок экрана 2025-02-16 172425](https://github.com/user-attachments/assets/20cf2ee4-79ae-41fb-9882-3e3b45f95cdd)

![Снимок экрана 2025-02-17 133219](https://github.com/user-attachments/assets/883ddaac-a6ff-4d05-95b0-96d962eecf1e)
![Снимок экрана 2025-02-17 133134](https://github.com/user-attachments/assets/ac6db62d-6e23-4c82-b540-6b34492f5029)

![Снимок экрана 2025-02-16 172516](https://github.com/user-attachments/assets/fc6bfe1a-0f53-4b14-afa5-2e16a265367c)
![Снимок экрана 2025-02-16 172501](https://github.com/user-attachments/assets/7ffa2837-f7b2-49a1-9e6a-eac7ec83827a)
![Снимок экрана 2025-02-16 172442](https://github.com/user-attachments/assets/53e3930d-a9bb-4b06-b86a-c11e99b0361c)


