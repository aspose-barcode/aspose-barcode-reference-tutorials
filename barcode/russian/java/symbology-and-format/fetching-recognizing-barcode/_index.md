---
date: 2025-12-25
description: Легко интегрируйте Aspose.BarCode для Java — получайте и распознавайте
  штрихкоды из базы данных. Узнайте, как считывать штрихкоды в Java с полным примером.
linktitle: Fetching and Recognizing Barcode
second_title: Aspose.BarCode Java API
title: Чтение штрихкода Java – Получение и распознавание штрихкодов
url: /ru/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Чтение штрихкода Java – Получение и распознавание штрихкодов

## Introduction

Ищете способ **read barcode java** в вашем приложении без борьбы с низкоуровневой обработкой изображений? Aspose.BarCode for Java предлагает мощный, простой в использовании API, который позволяет получать изображения штрихкодов из базы данных и распознавать их всего в несколько строк кода. В этом пошаговом руководстве мы пройдем всё необходимое — от настройки окружения до декодирования штрихкода CODE‑39, чтобы вы могли быстро и уверенно интегрировать распознавание штрихкодов.

## Quick Answers
- **Какую библиотеку использовать?** Aspose.BarCode for Java предоставляет самые полные возможности чтения штрихкодов.
- **Какой тип штрихкода демонстрируется?** Пример сосредоточен на CODE‑39 Standard, но API поддерживает десятки символогий.
- **Нужна ли лицензия для разработки?** Доступна временная оценочная лицензия; полная лицензия требуется для использования в продакшене.
- **Каковы основные предпосылки?** Java JDK, Aspose.BarCode for Java и база данных, хранящая изображения штрихкодов в виде BLOB.
- **Сколько времени занимает реализация?** Около 15‑20 минут, чтобы получить работающий прототип.

## Prerequisites

Прежде чем погрузиться в руководство, убедитесь, что у вас есть следующие предпосылки:

- Базовое понимание программирования на Java.
- Библиотека Aspose.BarCode for Java установлена. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).
- Доступ к базе данных, где изображения штрихкодов хранятся в формате BLOB.
- Java Development Kit (JDK) установлен на вашем компьютере.

## Import Packages

Чтобы начать, импортируйте необходимые пакеты для вашего проекта Java. Убедитесь, что библиотека Aspose.BarCode включена в зависимости вашего проекта.

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

Следуя этим шагам, вы сможете бесшовно интегрировать Aspose.BarCode в ваше Java‑приложение, обеспечивая эффективные операции **read barcode java** с базой данных.

## Заключение

В заключение, Aspose.BarCode for Java упрощает процесс получения и распознавания штрихкодов, делая его идеальным выбором для разработчиков, ищущих надёжное и эффективное решение. Следуя этому руководству, вы сможете без труда реализовать распознавание штрихкодов в ваших Java‑приложениях.

## Часто задаваемые вопросы

### Совместим ли Aspose.BarCode со всеми типами штрихкодов?

Да, Aspose.BarCode поддерживает широкий спектр типов штрихкодов, включая CODE_39_STANDARD, QR Code и другие. См. документацию для полного списка.

### Могу ли я использовать Aspose.BarCode с различными базами данных?

Конечно, Aspose.BarCode разработан для работы с различными базами данных. Убедитесь, что вы адаптировали детали соединения с базой данных соответствующим образом.

### Как обрабатывать ошибки во время распознавания штрихкода?

Обработка исключений имеет решающее значение. Убедитесь, что реализовали надёжную обработку ошибок для решения любых непредвиденных проблем во время распознавания штрихкода.

### Подходит ли Aspose.BarCode для крупномасштабных приложений?

Да, Aspose.BarCode разработан для обработки крупномасштабных приложений, обеспечивая высокую производительность и надёжность.

### Доступны ли временные лицензии для тестирования?

Да, вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/) для тестирования и оценки.

## Дополнительные часто задаваемые вопросы

**В: Какие другие символогии я могу декодировать тем же кодом?**  
О: Просто измените перечисление `DecodeType` (например, `DecodeType.QR`, `DecodeType.CODE_128`), чтобы считывать другие поддерживаемые типы штрихкодов.

**В: Могу ли я считывать штрихкоды напрямую из `ResultSet`, не записывая их в файл?**  
О: Да, вы можете передать `InputStream` или `byte[]` в конструктор `BarCodeReader`, чтобы избежать промежуточных файлов.

**В: Как улучшить скорость распознавания для тысяч записей?**  
О: Переиспользуйте один экземпляр `BarCodeReader`, обрабатывайте изображения пакетно и рассмотрите возможность отключения ненужных проверок символогий.

**В: Есть ли способ считывать несколько штрихкодов с одного изображения?**  
О: Метод `readBarCodes()` возвращает все обнаруженные штрихкоды в предоставленном изображении, поэтому вы можете перебрать результаты, как показано.

---

**Последнее обновление:** 2025-12-25  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}