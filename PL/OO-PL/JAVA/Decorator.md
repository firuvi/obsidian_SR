Паттерн декоратор (Decorator) позволяет динамически добавлять новую функциональность к объектам, не изменяя их исходный код. Это очень удобно, когда нужно добавить дополнительные возможности к уже существующему объекту.

```Java
 
 BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
```

В строке кода используется шаблон декоратора #decorator:

1. **InputStreamReader** является декоратором для `InputStream` (в данном случае для `System.in`), который трансформирует байты в символы.
2. **BufferedReader** является декоратором для `Reader` (в данном случае для `InputStreamReader`), добавляя функциональность буферизации и возможность построчного чтения.

В этом примере каждый декоратор добавляет дополнительную функциональность к базовому потоку ввода:

- **`InputStreamReader`** переводит байтовые потоки в символьные, позволяя читать текст из бинарных потоков ввода.
- **`BufferedReader`** добавляет буферизацию, что делает чтение эффективнее, и предоставляет удобный метод `readLine()` для чтения данных построчно.

### Как это работает

1. `System.in` предоставляет низкоуровневый доступ к стандартному вводу в форме байтов.
2. `InputStreamReader` обрабатывает эти байты и преобразует их в символы.
3. `BufferedReader` берет эти символы, буферизует их и предоставляет высокоуровневые методы для удобного чтения строк.

### Зачем использовать декораторы

Использование декораторов в Java идеально подходит для создания гибких структур, где объекты могут быть снабжены дополнительным поведением во время выполнения. Это особенно полезно в библиотеках, где пользователи могут не знать заранее, какие именно возможности им потребуются.

Такой подход помогает следовать принципу открытости/закрытости, согласно которому классы должны быть открыты для расширения, но закрыты для модификации. Это позволяет строить системы, которые легко модифицируются и расширяются без изменения существующего кода.

[[JAVA]]