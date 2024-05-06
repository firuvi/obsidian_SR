
## Sistem.in

`System.in` объект считываeт данные с клавиатуры по одному символу за раз (не удобно).

`Scanner` (`java.util.Scanner`) класс считывает данные из: консоли, файла, интернета. Передаём объекту `System.in` в качестве параметра – источника данных. Объект типа `Scanner` сам разберется, что с ним делать.

| **Scanner console = new Scanner(System.in);<br><br>String name = console.nextLine();<br><br>int age = console.nextInt();** | Создаем объект класса Scanner.<br><br>Читаем с клавиатуры строку текста.<br><br>Читаем с клавиатуры число. |
| -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
Пользователь может ввести ==несколько чисел== в одной строке, разделив их пробелами: такая ситуация будет корректно обработана методами класса Scanner. Однако числа будут считаны программой только после того, как пользователь нажмет Enter.

В приведенном выше примере наша переменная console типа Scanner хранила у себя внутри ссылку на объект типа Scanner.

| **nextByte()**    | Считывает данные и преобразует их в тип byte                  |
| ------------- | ------------------------------------------------------------- |
| **nextShort()**   | Считывает данные и преобразует их в тип short                 |
| **nextInt()**     | Считывает данные и преобразует их в тип int                   |
| **nextLong()**    | Считывает данные и преобразует их в тип long                  |
| **nextFloat()**   | Считывает данные и преобразует их в тип float                 |
| **nextDouble()**  | Считывает данные и преобразует их в тип double                |
| **nextBoolean()** | Считывает данные и преобразует их в тип boolean               |
| **next()**        | Считывает одно «слово». Слова разделяются пробелами или enter |
| **nextLine()**    | Считывает целую строку                                        |

Есть еще методы, которые позволяют проверить тип еще не считанных данных (чтобы знать, каким методом их считывать).

| **hasNextByte()**    | Там тип byte? Его можно будет преобразовать к byte?       |
| ---------------- | --------------------------------------------------------- |
| **hasNextShort()**   | Там тип short? Его можно будет преобразовать к short?     |
| **hasNextInt()**     | Там тип int? Его можно будет преобразовать к int?         |
| **hasNextLong()**    | Там тип long? Его можно будет преобразовать к long?       |
| **hasNextFloat()**   | Там тип float? Его можно будет преобразовать к float?     |
| **hasNextDouble()**  | Там тип double? Его можно будет преобразовать к double?   |
| **hasNextBoolean()** | Там тип boolean? Его можно будет преобразовать к boolean? |
| **hasNext()**        | Там есть еще одно слово?                                  |
| **hasNextLine()**    | Там есть еще одна строка?                                 |

Мы можем использовать метод `nextLine()` несколько раз и вывести весь кусок многострочного текста. Каждый раз наш сканер будет делать один шаг вперед и считывать следующую строку.
## Scanner Class
### Метод `useDelimeter()`

``` Java

public class Main {
   public static void main(String[] args) {
       Scanner scan = new Scanner("На голой ветке'" +
               "Ворон сидит одиноко.'" +
               "Осенний вечер." +
               "''***''" +
               "В небе такая луна,'" +
               "Словно дерево спилено под корень:'" +
               "Белеет свежий срез." +
               "''***''" +
               "Как разлилась река!'" +
               "Цапля бредет на коротких ножках,'" +
               "По колено в воде.");
       scan.useDelimiter("'");
       while (scan.hasNext()) {
           System.out.println(scan.next());
       }
       scan.close();
   }
}
``` 

Мы используем в качестве разделителя строк метод useDelimeter() класса Scanner: он отвечает за деление входящих данных на части. В нашем случае для разделения строк в качестве аргумента передаётся и используется одиночная кавычка ("'"). Следующий за этой кавычкой текст отображается на новой строке, так как в цикле while мы используем метод println() класса System для считывания данных.

### Метод `nextLine()`

``` Java

public class Main {

   public static void main(String[] args) {

       Scanner scanner = new Scanner("Люблю тебя, Петра творенье,\n" +
               "Люблю твой строгий, стройный вид,\n" +
               "Невы державное теченье,\n" +
               "Береговой ее гранит");
       String s = scanner.nextLine();
       System.out.println(s);
   }
}
```

Метод `nextLine()` обращается к источнику данных (нашему тексту с четверостишием), находит там следующую строку, которую он еще не считывал (в нашем случае — первую) и возвращает ее. 

**Вывод в консоль:**

```
Люблю тебя, Петра творенье,
>_
```

Мы можем использовать метод `nextLine()` ==несколько раз== и вывести весь кусок поэмы:

``` Java

public class Main {

   public static void main(String[] args) {

       Scanner scanner = new Scanner("Люблю тебя, Петра творенье,\n" +
               "Люблю твой строгий, стройный вид,\n" +
               "Невы державное теченье,\n" +
               "Береговой ее гранит");
       String s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
       s = scanner.nextLine();
       System.out.println(s);
   }
}
```

**Вывод в консоль:**

```
Люблю тебя, Петра творенье,
Люблю твой строгий, стройный вид,
Невы державное теченье,
Береговой ее гранит
>_
```

### Метод `nextInt()`

``` Java

public class Main {
   public static void main(String[] args) {
       Scanner sc = new Scanner(System.in);
       System.out.println("Введите число:");
       int number = sc.nextInt();
       System.out.println("Спасибо! Вы ввели число " + number);
   }
}
```

Cчитывает и возвращает введенное число. В нашей программе он используется для того, чтобы присвоить значение переменной `number`.
### Методы проверки соответствия типов `hasNextтип_данных()`

`hasNextInt()` — метод проверяет, является ли следующая порция введенных данных числом, или нет (возвращает, соответственно, true или false).

`hasNextLine()` — проверяет, является ли следующая порция данных строкой.

```Java

hasNextByte()
hasNextShort()
hasNextLong()
hasNextFloat()
hasNextDouble()
```

Эти методы делают то же для остальных типов данных.

Пример использования

``` Java
public class Main {

   public static void main(String[] args) {

       Scanner sc = new Scanner(System.in);
       System.out.println("Введите число:");

       if (sc.hasNextInt()) {
           int number = sc.nextInt();
           System.out.println("Спасибо! Вы ввели число " + number);
       } else {
           System.out.println("Извините, но это явно не число. Перезапустите программу и попробуйте снова!");
       }

   }
}
```

Теперь наша программа проверяет, является ли следующий введенный символ числом или нет. И только в случае, если является, выводит подтверждение. Если же ввод не прошел проверку, программа это замечает и просит попробовать снова. По сути, ты можешь общаться с объектом Scanner и заранее узнавать, какой тип данных тебе ожидать. “Эй, сканер, что там дальше будет? Число, строка, или еще что? Число? А какое — `int`, `short`, `long`?” Такая гибкость дает тебе возможность выстраивать логику своей программы в зависимости от поведения пользователя.


### Класс FileOutputStream

Главное назначение класса FileOutputStream — запись байтов в файл.

FileOutputStream является одной из реализаций абстрактного класса OutputStream.

В конструкторе объекты этого класса принимают либо путь к целевому файлу (в который и нужно записать байты), либо объект класса File.

Рассмотрим оба примера:

``` Java

public class Main {
   public static void main(String[] args) throws IOException {


       File file = new File("C:\\Users\\Username\\Desktop\\test.txt");
       FileOutputStream fileOutputStream = new FileOutputStream(file);

       String greetings = "Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!";

       fileOutputStream.write(greetings.getBytes());

       fileOutputStream.close();
   }
}
```

При создании объекта File мы указали в конструкторе путь, где он должен будет находиться. Создавать его заранее нет необходимости: если он не существует, программа создаст его сама.

Можно обойтись и без создания лишнего объекта, и просто передать строку с адресом:

``` Java

public class Main {

   public static void main(String[] args) throws IOException {


       FileOutputStream fileOutputStream = new FileOutputStream("C:\\Users\\Username\\Desktop\\test.txt");

       String greetings = "Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!";

       fileOutputStream.write(greetings.getBytes());

       fileOutputStream.close();
   }
}
```

**Результат** в обоих случаях будет одинаковым. Мы можем открыть наш файл и увидеть там:

>Привет! Добро пожаловать на JavaRush — лучший сайт для тех, кто хочет стать программистом!

Однако есть здесь один нюанс. Попробуй запустить код из примера выше несколько раз подряд, а потом загляни в файл, и ответь на вопрос: сколько записанных в него строк ты видишь?

Всего одну. Но ведь ты запускал код несколько раз. Однако при этом данные, оказывается, всякий раз перезаписывались, заменяя старые.

Что делать, если требуется последовательная запись?

В конструктор FileOutputStream ты можешь передать дополнительный параметр — boolean append.

Если его значение true, данные будут до записаны в конец файла. Если false (а по умолчанию это значение и есть false), старые данные будут стерты, а новые записаны. 

Давай проверим и запустим наш измененный код трижды:

``` Java

public class Main {

   public static void main(String[] args) throws IOException {
   
   FileOutputStream fileOutputStream = new
   FileOutputStream("C:\\Users\\Username\\Desktop\\test.txt", true);
   
   String greetings = "Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!\r\n";

       fileOutputStream.write(greetings.getBytes());

       fileOutputStream.close();
   }
}
```

**Результат в файле:**

>Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!
>Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!
>Привет! Добро пожаловать на JavaRush - лучший сайт для тех, кто хочет стать программистом!

Ну и конечно, как и в случае с другими классами I/O, не забываем об освобождении ресурсов через метод close().

### Класс FileInputStream

У класса ==FileInputStream== назначение противоположное — чтение байтов из файла. Так же как FileOutputStream наследует OutputStream, этот класс происходит от абстрактного класса InputStream.

Запишем в наш текстовый «test.txt» несколько строк текста:

>So close no matter how far
>Couldn't be much more from the heart
>Forever trusting who we are
>And nothing else matters

Вот как будет выглядеть реализация чтения данных из файла при помощи FileInputStream:

``` Java

public class Main {

   public static void main(String[] args) throws IOException {

       FileInputStream fileInputStream = new FileInputStream("C:\\Users\\Username\\Desktop\\test.txt");

       int i;

       while((i=fileInputStream.read())!= -1){

           System.out.print((char)i);
       }
   }
}

```

Мы считываем из файла по одному байту, преобразуем считанные байты в символы и выводим их в консоль.

**Результат в консоли:**

```
So close no matter how far
Couldn't be much more from the heart
Forever trusting who we are
And nothing else matters
Класс BufferedInputStream
>_
```

Думаю, учитывая знания из прошлых лекций, ты легко сможешь сказать, зачем нужен класс BufferedInputStream и какие преимущества у него есть по сравнению с FileInputStream :)

Мы уже встречались с буферизированными потоками, поэтому попробуй предположить (или вспомнить), прежде чем продолжить чтение :)

Буферизированные потоки нужны прежде всего для оптимизации ввода-вывода.

Обращение к источнику данных, например, чтение из файла, — дорогостоящая в плане производительности операция. И каждый раз обращаться к файлу для чтения по одному байту расточительно.

Поэтому BufferedInputStream считывает данные не по одному байту, а блоками и временно хранит их в специальном буфере. Это позволяет нам оптимизировать работу программы за счет того, что мы уменьшаем количество обращений к файлу.


- [f] **Проверка BufferedInputStream на скорость**

#### С BufferedInputStream

```Java

public class Main {

   public static void main(String[] args) throws IOException {
   
   Date date = new Date();

       FileInputStream fileInputStream = new FileInputStream("C:\\Users\\Username\\Desktop\\textBook.rtf");

       BufferedInputStream bufferedInputStream = new BufferedInputStream(fileInputStream);

       int i;

       while((i = bufferedInputStream.read())!= -1){

           System.out.print((char)i);
       }

       Date date1 = new Date();

       System.out.println((date1.getTime() - date.getTime()));
   }
}

```

#### Без BufferedInputStream

``` Java

public class Main {

   public static void main(String[] args) throws IOException {

       Date date = new Date();

       FileInputStream fileInputStream = new FileInputStream("C:\\Users\\Username\\Desktop\\26951280.rtf");

       int i;

       while((i = fileInputStream.read())!= -1){

           System.out.print((char)i);
       }

       Date date1 = new Date();

       System.out.println((date1.getTime() - date.getTime()));
   }
}
```

При чтении файла размером 1,5 Мб на моем компьютере FileInputStream выполнил работу за ~3500 миллисекунд, а вот BufferedInputStream — за ==~1700 миллисекунд==. Как видишь, буферизированный поток оптимизировал работу программы в 2 раза! :)

[[Streams]]