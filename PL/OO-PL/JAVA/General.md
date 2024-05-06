Java - строго типизированный, компилируемый ООЯП общего назначения.

Приложения Java компилируются в специальный байт-код и могут работать на любой компьютерной архитектуре, для которой существует реализация виртуальной Java-машины. Компиляция превращает файл \*.java в файл \*.class.

Команда CLI для компиляции в *bash* #bash

``` bash
javac HelloWorld.java
```

Команда CLI для запуска скомпилированного файла в bash

``` bash
java HelloWorld
```

- Java-программы состоят из классов, классы содержат методы (функции), а методы — команды
- Тело класса может содержать переменные (их еще называют данными класса)
- Тело класса помещается в фигурные скобки {}
- Все команды пишутся с большой буквы
- Вызвать методы объекта, на который ссылается переменная, после имени переменной написать точку, а затем имя метода и параметры. Общий вид этой команды такой `переменная.метод(параметры);`

## Файл класса House.java

### Общий вид класса

``` java
public class House 
{
    ТЕЛО КЛАССА
}
```

### С переменными

``` java
public class House

{
    ПЕРЕМЕННАЯ А

    ПЕРЕМЕННАЯ Z

    МЕТОД 1

    МЕТОД N
}
```

[[JAVA]]