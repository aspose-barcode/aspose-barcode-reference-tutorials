---
date: 2026-04-29
description: Узнайте, как считывать штрихкоды на Java с помощью Aspose.BarCode. Этот
  учебник показывает пример считывателя штрихкодов для получения и распознавания изображений
  штрихкодов из базы данных.
keywords:
- read barcode java
- barcode reader example
- java barcode library
- read barcode image
- recognize barcode image
linktitle: Получение и распознавание штрих‑кода
second_title: Aspose.BarCode Java API
title: Чтение штрихкодов Java – получение и распознавание штрихкодов с помощью Aspose
url: /ru/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение штрихкодов Java – Получение и распознавание штрихкодов

## Введение

Если вам нужно быстро **read barcode java** в приложениях, Aspose.BarCode for Java предлагает простой, высокопроизводительный способ извлекать изображения штрихкодов из базы данных и распознавать их всего в несколько строк кода. В этом руководстве мы пройдём полный реальный пример, показывающий, как подключиться к базе данных, извлечь изображение штрихкода и использовать считыватель Aspose для его декодирования. К концу у вас будет переиспользуемый фрагмент, который можно вставить в любой Java‑проект.

## Быстрые ответы
- **Что делает библиотека?** Она читает изображения штрихкодов (например, Code 39) напрямую из файлов или потоков.  
- **Какой основной ключевой запрос?** read barcode java  
- **Нужна ли лицензия для тестирования?** Доступна временная лицензия для оценки.  
- **Какой тип базы данных показан?** В примере используется MySQL, но код работает с любой базой данных, совместимой с JDBC.  
- **Сколько времени занимает внедрение?** Около 10‑15 минут для базовой интеграции.

## Что такое “read barcode java”?
Чтение штрихкода в Java означает загрузку изображения, содержащего шаблон штрихкода, и использование декодирующего движка для преобразования этого шаблона в исходную строку данных. Aspose.BarCode предоставляет надёжный декодер, поддерживающий десятки символогий, включая Code 39, QR и DataMatrix.

## Почему стоит использовать Java‑библиотеку штрихкодов от Aspose?
- **Широкая поддержка символогий** – более 150 типов штрихкодов из коробки.  
- **Отсутствие внешних зависимостей** – чистый Java, работает на любой платформе с JDK 8+.  
- **Высокая точность** – оптимизированные алгоритмы снижают количество ошибок чтения, даже на изображениях низкого качества.  
- **Простой API** – несколько строк кода преобразуют необработанное изображение в читаемый текст.

## Требования
- Базовые знания программирования на Java.  
- Библиотека Aspose.BarCode for Java (скачайте её **[здесь](https://releases.aspose.com/barcode/java/)**).  
- Доступ к базе данных, в которой изображения штрихкодов хранятся как BLOB.  
- Установленный JDK 8 или новее на вашей машине разработки.

## Импорт пакетов

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## Шаг 1: Установить соединение с базой данных

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

// Open a connection to the database
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## Шаг 2: Выполнить SQL‑запрос

```java
// Create a statement to execute the SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## Шаг 3: Получить и создать изображения

```java
while (rs.next()) {
    // Read BLOB field and create an image from it
    String len1 = rs.getString("BarCodeImage");
    int len = len1.length();
    byte[] b = new byte[len];
    InputStream in = rs.getBinaryStream("BarCodeImage");

    int index = in.read(b, 0, len);
    OutputStream outImgBarCode = new FileOutputStream(strBarCodeImage);

    while (index != -1) {
        // Write bytes to file
        outImgBarCode.write(b, 0, index);
        // Read next bytes
        index = in.read(b, 0, len);
    }
    outImgBarCode.close();
```

## Шаг 4: Считать штрихкод с изображения

```java
// Read the barcode from the image
BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_STANDARD);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}

nCount++;
}

System.out.println(nCount + " records found.");
con.close();
} catch (Exception ex) {
System.out.println(ex.getMessage());
}
```

## Распространённые проблемы и решения
- **NullPointerException при чтении BLOB** – Убедитесь, что имя столбца точно совпадает и что BLOB действительно содержит данные.  
- **Неподдерживаемый тип штрихкода** – Проверьте, что `DecodeType` соответствует символогии, хранящейся в изображении; для QR‑кодов используйте `DecodeType.QR`.  
- **Ошибки прав доступа к пути файла** – Путь `strBarCodeImage` должен быть доступен для записи процессом Java; при необходимости используйте временный каталог.  

## Часто задаваемые вопросы

**В: Совместима ли Aspose.BarCode со всеми типами штрихкодов?**  
A: Да, она поддерживает широкий спектр символогий штрихкодов, включая CODE_39_STANDARD, QR Code, DataMatrix и многие другие. Обратитесь к документации продукта для полного списка.

**В: Могу ли я использовать Aspose.BarCode с разными базами данных?**  
A: Конечно. В примере используется MySQL, но вы можете переключиться на PostgreSQL, SQL Server или любую базу данных, совместимую с JDBC, изменив класс драйвера и строку подключения.

**В: Как обрабатывать ошибки при распознавании штрихкода?**  
A: Оберните логику чтения в блок try‑catch (как показано) и записывайте сообщение исключения в журнал. Рассмотрите возможность повторных попыток при временных ошибках ввода‑вывода и проверьте, что файл изображения существует перед декодированием.

**В: Подходит ли библиотека для крупномасштабных приложений?**  
A: Да. Aspose.BarCode разработана для сценариев с высокой пропускной способностью; при необходимости можно переиспользовать один экземпляр `BarCodeReader` в нескольких потоках.

**В: Где можно получить временную лицензию для тестирования?**  
A: Вы можете получить временную лицензию **[здесь](https://purchase.aspose.com/temporary-license/)** для целей оценки.

---

**Последнее обновление:** 2026-04-29  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}