## 1. Установка Java Development Kit (JDK)

Перед установкой IntelliJ IDEA убедись, что на твоём компьютере установлен *JDK*. IntelliJ требует JDK для компиляции и запуска Java-приложений.

- Перейди на официальный сайт Oracle ([oracle.com](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)) или на сайт OpenJDK ([jdk.java.net](https://jdk.java.net/)), скачай JDK .
- Следуй инструкциям на сайте для установки JDK на свой компьютер.

## 2. Проверка установки Java

После установки JDK проверь, что установка прошла успешно, открыв терминал или командную строку и введя следующую команду:

``` bash
java -version
```

Если установка прошла успешно, ты увидишь версию установленной Java.

## 3. Скачивание и установка IntelliJ IDEA

Перейди на сайт [JetBrains](https://www.jetbrains.com/idea/download/) Скачай установщик и следуй инструкциям по установке.

## 4. Настройка переменной среды JAVA_HOME

Чтобы Java-приложения, включая среды разработки, могли находить установленный JDK, необходимо настроить переменную среды `JAVA_HOME`:

1. **Открой Системные настройки**. Это можно сделать через Панель Управления или нажав правой кнопкой мыши на иконку Пуск и выбрав "Система".
2. **Перейди к дополнительным системным настройкам**. Слева ты найдешь ссылку "Дополнительные параметры системы". В открывшемся окне выбери вкладку "Дополнительно".
3. **Настройки среды**. Нажми на кнопку "Переменные среды" в нижней части окна.
4. **Создай или обнови переменную JAVA_HOME**:
- Если переменная `JAVA_HOME` уже существует, выбери её и нажми "Изменить", чтобы обновить путь до новой папки JDK.
- Если переменной нет, нажми "Создать" и введи `JAVA_HOME` в поле имени и путь к папке, куда ты распаковал JDK, в поле значения.

## 5. Обновление переменной Path

Также может потребоваться добавить путь к исполняемым файлам JDK в переменную среды Path, чтобы можно было запускать `java`, `javac` и другие инструменты из командной строки:

1. В том же окне "Переменные среды" найди переменную `Path` и выбери "Изменить".
2. Нажми "Создать" и добавь путь к папке `bin` внутри папки JDK (например, `C:\Program Files\Java\jdk-22\bin`).
3. Нажми ОК для сохранения.

## Обновление конфигураций в IDE:

Если ты используешь IntelliJ IDEA, убедись, что для твоих проектов установлена новая версия JDK. В IntelliJ IDEA это можно сделать, открыв *File > Project Structure > Project*, и выбрав новую версию JDK в выпадающем списке для "Project SDK".

Удалять старую версию JDK или нет — решать тебе, но если решишь оставить, это может быть полезно для тестирования приложений в разных средах. Просто убедись, что для текущих проектов используется правильная версия JDK.


[[IntelliJ IDEA]]

