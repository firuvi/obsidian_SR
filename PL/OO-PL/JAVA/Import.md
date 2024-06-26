### Зачем нужен Import?

В Java классы организованы в пакеты. Это помогает избежать конфликтов имен и улучшить управляемость кодом, особенно в больших проектах. Когда ты используешь класс из стандартной библиотеки Java или из сторонних библиотек, тебе нужно явно указать, откуда этот класс нужно взять. Это делается с помощью оператора `import`.

- **`import java.util.Scanner;`** говорит компилятору Java, что в коде будет использоваться класс `Scanner`, который находится в пакете `java.util`.

### Какие элементы Java загружены изначально?

Java по умолчанию импортирует все классы из пакета `java.lang`, такие как `String`, `Math`, `System`, и другие. Это означает, что тебе не нужно явно импортировать классы из `java.lang`. Однако для всех других классов из стандартной библиотеки Java, включая коллекции из `java.util` (такие как `ArrayList`, `HashMap`, `Scanner` и др.), тебе нужно явно указать импорт.

### Альтернатива полному импорту

Если ты используешь класс только один раз или хочешь явно указать, к какому пакету он относится в конкретной части кода, можно использовать класс с его полным именем, без предварительного импорта. Например:

```Java
java.util.Scanner scanner = new java.util.Scanner(System.in);
```

Это устраняет необходимость в операторе `import` на верху файла, но делает код более громоздким и менее читабельным, особенно если класс используется многократно.

[[JAVA]]

