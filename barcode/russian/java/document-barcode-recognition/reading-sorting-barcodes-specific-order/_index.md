---
date: 2026-04-08
description: Узнайте, как считывать штрихкоды и сортировать их в определённом порядке
  с помощью Aspose.BarCode для Java. Это пошаговое руководство показывает, как использовать
  Aspose, Java‑сканер штрихкодов и декодировать штрихкод Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: Считывание и сортировка штрих‑кодов в определённом порядке
second_title: Aspose.BarCode Java API
title: Как считывать штрихкоды в определённом порядке с помощью Java
url: /ru/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать штрихкоды в определённом порядке с помощью Java

## Введение

Если вам нужно **how to read barcodes** и затем упорядочить их в определённой последовательности, Aspose.BarCode for Java предоставляет чистый, высокопроизводительный способ сделать это. Во многих Java‑приложениях — системах учёта, решениях для доставки или POS‑терминалах — чтение нескольких штрихкодов и сортировка их по текстовому значению является частой задачей. Этот учебник проведёт вас через весь процесс, от настройки окружения до отображения отсортированных результатов, чтобы вы могли быстро и уверенно интегрировать работу со штрихкодами.

## Быстрые ответы
- **Какой библиотекой осуществляется чтение штрихкодов?** Aspose.BarCode for Java  
- **Какой тип штрихкода используется в примере?** CODE_128  
- **Нужна ли лицензия для разработки?** Временная лицензия работает для тестирования; полная лицензия требуется для продакшн.  
- **Можно ли сортировать по другим критериям?** Да — измените компаратор, чтобы сортировать по местоположению, уверенности и т.д.  
- **Какая версия Java требуется?** Java 8 или новее (любой JDK, поддерживающий библиотеку Aspose).

## Что означает “how to read barcodes” в Java?

Чтение штрихкодов означает декодирование визуального шаблона в исходную строку данных. Aspose.BarCode предоставляет класс `BarCodeReader`, который абстрагирует низкоуровневую обработку изображений, позволяя сосредоточиться на бизнес‑логике, такой как сортировка или проверка.

## Почему использовать Aspose.BarCode for Java?

- **Надёжное декодирование** – поддерживает более 50 символогий, включая Code 128, QR, DataMatrix и др.  
- **Высокая точность** – оптимизированные алгоритмы снижают количество ошибок чтения, даже на изображениях низкого разрешения.  
- **Простой API** – несколько строк кода переводят изображение в текст.  
- **Кроссплатформенность** – работает в любой среде Java, от настольных приложений до серверов.

## Предварительные требования

Прежде чем погрузиться в код, убедитесь, что у вас есть следующие требования:

- Java Development Kit (JDK): Aspose.BarCode for Java требует работающий JDK. Вы можете скачать последнюю версию [здесь](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.BarCode Library: Убедитесь, что у вас есть библиотека Aspose.BarCode. Вы можете получить её по [ссылке для скачивания](https://releases.aspose.com/barcode/java/).

## Импорт пакетов

Начните с импорта необходимых пакетов в ваш Java‑проект. Эти пакеты предоставляют основные классы и методы для работы со штрихкодами.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Теперь разберём код пошагово:

## Шаг 1: Настройка каталога ресурсов

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на фактический путь к вашему каталогу документов.

## Шаг 2: Указание пути к изображению штрихкода и инициализация считывателя

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Шаг 3: Чтение штрихкодов и сохранение результатов

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Шаг 4: Определение компаратора для сортировки

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Шаг 5: Сортировка штрихкодов

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Шаг 6: Отображение отсортированных штрихкодов

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Распространённые ошибки и советы

- **Неправильный путь к изображению** – проверьте, что `dataDir` заканчивается разделителем файлов (`/` или `\\`), чтобы полный путь был корректным.  
- **Неподдерживаемый тип штрихкода** – если требуется декодировать другую символогию, измените `DecodeType.CODE_128` на соответствующее значение enum (например, `DecodeType.QR`).  
- **Сортировка по числовому значению** – компаратор по умолчанию сортирует лексикографически. Для числовой сортировки преобразуйте `CodeText` в целое число внутри компаратора.  
- **Очистка ресурсов** – `BarCodeReader` реализует `Closeable`. В продакшн‑коде оберните его в блок try‑with‑resources, чтобы гарантировать освобождение базового потока.

## Часто задаваемые вопросы

### В: Где я могу найти документацию Aspose.BarCode for Java?
Документация доступна [здесь](https://reference.aspose.com/barcode/java/).

### В: Как я могу скачать Aspose.BarCode for Java?
Вы можете скачать её по [ссылке для скачивания](https://releases.aspose.com/barcode/java/).

### В: Доступна ли бесплатная пробная версия?
Да, вы можете ознакомиться с бесплатной пробной версией [здесь](https://releases.aspose.com/).

### В: Как получить информацию о временной лицензии?
Временные лицензии можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### В: Где я могу получить поддержку или задать вопросы?
Посетите форум поддержки [здесь](https://forum.aspose.com/c/barcode/13).

---

**Последнее обновление:** 2026-04-08  
**Тестировано с:** Aspose.BarCode 24.10 for Java  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}