---
date: 2025-12-19
description: Узнайте, как считывать штрихкоды с помощью Aspose.BarCode для Java, сортировать
  их в определённом порядке и посмотреть полный пример обнаружения штрихкодов на Java.
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: Как считывать штрихкоды и сортировать их в определённом порядке на Java
url: /ru/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как считывать штрихкоды и сортировать их в определённом порядке на Java

## Введение

В современных Java‑приложениях **how to read barcodes** эффективно — частый вопрос. Независимо от того, обрабатываете ли вы списки инвентаря, транспортные этикетки или билеты на мероприятия, надёжное решение для штрихкодов может сэкономить часы ручной работы. В этом руководстве мы покажем, как считывать штрихкоды и сортировать их в определённом порядке с помощью **Aspose.BarCode for Java**. Вы получите полностью готовый пример, демонстрирующий обнаружение штрихкода, извлечение текста кода и пользовательскую логику сортировки.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.BarCode for Java
- **Можно ли сортировать штрихкоды после их чтения?** Да — просто сохраните результаты и примените компаратор
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшна
- **Какая версия Java поддерживается?** Java 8 и новее
- **Это пример обнаружения штрихкодов на Java?** Абсолютно — код читает штрихкоды CODE_128 и сортирует их

## Что означает “how to read barcodes” в Java?
Считывание штрихкодов означает декодирование визуального шаблона изображения штрихкода в его базовое текстовое значение. Aspose.BarCode предоставляет высокопроизводительный **barcode reading aspose** движок, поддерживающий десятки символогий, включая CODE_128, QR, DataMatrix и другие.

## Почему использовать Aspose.BarCode для barcode reading aspose?
- **Высокая точность** — работает даже с изображениями низкого разрешения
- **Простой API** — несколько строк кода переводят вас от изображения к тексту
- **Кроссплатформенный** — работает в любой JVM‑совместимой среде
- **Встроенная поддержка сортировки** — вы можете легко комбинировать чтение с коллекциями Java

## Предварительные требования

Перед тем как погрузиться в код, убедитесь, что у вас есть следующие требования:

- Java Development Kit (JDK): Aspose.BarCode for Java требует работающий JDK. Вы можете скачать последнюю версию [здесь](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.BarCode Library: Убедитесь, что у вас есть библиотека Aspose.BarCode. Вы можете получить её по [ссылке для загрузки](https://releases.aspose.com/barcode/java/).

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

Замените `"Your Document Directory"` реальным путём к вашему каталогу документов.

## Шаг 2: Укажите путь к изображению штрихкода и инициализируйте считыватель

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

## Распространённые проблемы и решения

| Проблема | Почему происходит | Решение |
|----------|-------------------|---------|
| **Штрихкоды не обнаружены** | Неправильный `DecodeType` или изображение низкого качества | Убедитесь, что изображение содержит штрихкод CODE_128 и используйте соответствующий `DecodeType`. Можно также попробовать `DecodeType.ALL` для автоматического обнаружения. |
| **Неправильный порядок сортировки** | Компаратор сравнивает строки лексикографически | Если нужна числовая сортировка, преобразуйте `CodeText` в `int` перед сравнением. |
| **Null pointer в `BarCodeRegion`** | Путь к изображению неверен или файл не найден | Убедитесь, что `path` указывает на действительный PNG‑файл и что файл доступен для чтения JVM. |

## Часто задаваемые вопросы

**Q: Где можно найти документацию Aspose.BarCode for Java?**  
A: Документация доступна [здесь](https://reference.aspose.com/barcode/java/).

**Q: Как скачать Aspose.BarCode for Java?**  
A: Вы можете скачать её по [ссылке для загрузки](https://releases.aspose.com/barcode/java/).

**Q: Есть ли бесплатная пробная версия?**  
A: Да, бесплатную пробную версию можно изучить [здесь](https://releases.aspose.com/).

**Q: Как получить информацию о временной лицензии?**  
A: Временные лицензии можно получить [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где можно получить поддержку или задать вопросы?**  
A: Посетите форум поддержки [здесь](https://forum.aspose.com/c/barcode/13).

## Дополнительные FAQ (AI‑оптимизированные)

**Q: Можно ли использовать этот код с другими типами штрихкодов?**  
A: Абсолютно. Измените `DecodeType.CODE_128` на любую поддерживаемую символогию, например `DecodeType.QR` или `DecodeType.DATA_MATRIX`.

**Q: Поддерживает ли Aspose.BarCode пакетную обработку нескольких изображений?**  
A: Да. Пройдитесь по коллекции путей к файлам и переиспользуйте ту же логику `BarCodeReader` для каждого изображения.

**Q: Как улучшить производительность при работе с большим набором изображений?**  
A: Переиспользуйте экземпляр `BarCodeReader`, где это возможно, и обрабатывайте изображения параллельно, используя `ExecutorService` в Java.

## Заключение

В этом руководстве мы продемонстрировали **how to read barcodes** с помощью Aspose.BarCode for Java, сохранили каждый результат и отсортировали список в пользовательском порядке. Следуя пошаговому руководству, вы сможете интегрировать надёжное обнаружение и сортировку штрихкодов в любое Java‑приложение — будь то управление запасами, логистика или билетные системы.

---

**Last Updated:** 2025-12-19  
**Tested With:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}