---
date: 2026-10-19
description: Узнайте, как создать QR code java и сгенерировать несколько barcodes
  на одном изображении с помощью Aspose.BarCode for Java. Включает setup, code и troubleshooting.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Генерация нескольких barcodes на одном изображении
og_description: Создайте QR code java и объедините несколько barcode types в одно
  изображение с помощью Aspose.BarCode for Java. Следуйте step‑by‑step guide, просмотрите
  code snippets и узнайте troubleshooting tips.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Создать QR code java – сгенерировать несколько barcodes на одном изображении
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Создать QR code java – сгенерировать несколько barcodes на одном изображении
url: /ru/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать QR‑код Java – генерировать несколько штрихкодов на одном изображении

## Введение

В этом руководстве вы узнаете **как создать QR‑код Java** и объедините несколько разных типов штрихкодов на одном холсте с помощью **Aspose.BarCode for Java**. Независимо от того, нужен ли вам компактный QR‑ярлык, штрихкод продукта или комбинация 2‑D и линейных символогий, это руководство проведёт вас через каждый шаг — от настройки проекта до сохранения окончательного комбинированного изображения — чтобы вы могли сразу начать интегрировать генерацию штрихкодов в свои Java‑приложения.

## Быстрые ответы
- **Какую библиотеку следует использовать?** Aspose.BarCode for Java предоставляет самый полный набор символогий.  
- **Могу ли я генерировать разные типы штрихкодов вместе?** Да, вы можете смешивать CODE_39, QR, AZTEC и другие на одном холсте.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшна.  
- **Какая версия Java поддерживается?** Java 8 и новее полностью совместимы.  
- **Можно ли настроить формат вывода?** Вы можете экспортировать комбинированное изображение в PNG, JPEG, BMP или TIFF.  

## Что такое create QR code java?

`create QR code java` относится к процессу преобразования текстовой строки в двумерную матрицу, которую могут сканировать смартфоны или считыватели штрихкодов. Aspose.BarCode for Java выполняет кодирование и отрисовку, позволяя вам сосредоточиться на бизнес‑логике, а не на работе с пиксельным изображением.

## Почему использовать Aspose.BarCode Java для генерации штрихкодов Java?

Aspose.BarCode поддерживает **более 50 символогий штрихкодов** — включая QR, Data Matrix, Code 128, AZTEC и традиционные линейные коды — что делает её самой универсальной Java‑библиотекой для штрихкодов. Она рендерит **анти‑алиасные изображения с разрешением до 1200 dpi**, гарантируя чёткое сканирование на экране и при печати. API требует только JVM и предоставляет плавную модель конфигурации для настройки размера, цвета, отступов и коррекции ошибок всего в нескольких строках кода.

## Требования

- Твердое понимание основ Java.  
- Установленный JDK 8 или новее, настроенный в PATH.  
- JAR‑файл Aspose.BarCode for Java (скачайте со страницы официального скачивания Aspose.BarCode for Java).  
- IDE, например IntelliJ IDEA или Eclipse, для редактирования и запуска примера.  

## Импорт пространств имён

Импортированные инструкции вводят классы Aspose.BarCode, такие как `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`, в область видимости, позволяя обращаться к ним без полностью квалифицированных имён.  
`BarcodeGenerator` — основной класс, используемый для настройки и генерации изображений штрихкодов.  
`EncodeTypes` — перечисление в Aspose.BarCode, определяющее символогию штрихкода для генерации.  
`BarCodeImageFormat` определяет формат выходного изображения для сгенерированного штрихкода.

## Шаг 1: установить каталог ресурсов

**resource directory** — это папка в вашей файловой системе, куда будут записываться все сгенерированные изображения штрихкодов. Определив её один раз, вы упорядочите проект и упростите очистку старых файлов.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Шаг 2: создать коллекцию штрихкодов

`HashMap<String, EncodeTypes>` хранит строку данных каждого штрихкода вместе с символогией, которую вы хотите использовать. `HashMap` — это коллекция Java, сопоставляющая ключи со значениями. Эта коллекция управляет последующим циклом генерации. `EncodeTypes` — перечисление, указывающее, какой тип штрихкода генерировать.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Шаг 3: генерировать изображения штрихкодов

Цикл генерации проходит по `HashMap`, создает `BarcodeGenerator` для каждой записи и вызывает `generateBarCodeImage()`, чтобы получить `BufferedImage`. `generateBarCodeImage()` создает `BufferedImage`, содержащий отрисованный штрихкод. `BufferedImage` — класс Java, представляющий изображение в памяти. Все изображения добавляются в `ArrayList<BufferedImage>` для последующего объединения. `ArrayList` — реализует изменяемый список в Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Шаг 4: создать комбинированное изображение

Сначала алгоритм вычисляет **максимальную ширину** среди всех изображений штрихкодов и **общую высоту**, необходимую для вертикального размещения их с возможными отступами. Затем он создает `BufferedImage` нужного размера и рисует каждый штрихкод на холсте с помощью объекта `Graphics2D`. `Graphics2D` — класс Java, предоставляющий возможности 2D‑рендеринга для рисования фигур и изображений.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Шаг 5: сохранить результат

Наконец, составное изображение записывается на диск с помощью `ImageIO.write`, используя указанный вами формат (PNG, JPEG, BMP или TIFF). `ImageIO.write` сохраняет `BufferedImage` в файл в выбранном формате. Путь к файлу относителен каталогу ресурсов, определённому ранее.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Распространённые сценарии использования для генерации нескольких штрихкодов

- **Этикетки упаковки** – объединить коды продукта, партии и доставки на одной этикетке, чтобы снизить затраты на печать.  
- **Билеты на мероприятия** – внедрить QR, Data Matrix и идентификаторы Code 128 для разных станций сканирования на площадке.  
- **Управление запасами** – отображать SKU, данные RFID‑метки и серийные номера вместе для быстрой проверки и отслеживаемости.

## Устранение неполадок и советы

- **Проблемы с размером изображения** – отрегулируйте переменную `offset`, чтобы увеличить или уменьшить расстояние между штрихкодами.  
- **Неподдерживаемая симвология** – убедитесь, что ваша версия Aspose.BarCode поддерживает нужный тип штрихкода; новые релизы добавляют дополнительные 2‑D коды.  
- **Производительность** – переиспользуйте один объект `Graphics2D` при генерации множества изображений в цикле, чтобы минимизировать накладные расходы на создание объектов.

## Часто задаваемые вопросы

**Q: Могу ли я настроить внешний вид отдельных штрихкодов в сгенерированном изображении?**  
A: Да. Используйте свойства `BarcodeGenerator`, такие как `setBarColor`, `setBackgroundColor` и `setXDimension`, чтобы стилизовать каждый штрихкод независимо перед добавлением его на холст.

**Q: Совместим ли Aspose.BarCode с различными символогиями штрихкодов?**  
A: Абсолютно. Библиотека поддерживает более 50 символогий, включая CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 и AZTEC, как показано в этом руководстве.

**Q: Как интегрировать Aspose.BarCode в мой Java‑проект?**  
A: Скачайте JAR со страницы загрузки библиотеки Aspose.BarCode for Java, добавьте его в classpath проекта и импортируйте необходимые пространства имён, как показано в разделе «Импорт пространств имён».

**Q: Могу ли я использовать Aspose.BarCode в коммерческих приложениях?**  
A: Да. Приобретите лицензию на странице покупки лицензии Aspose.BarCode, чтобы снять ограничения пробной версии и получить полную поддержку в продакшне.

**Q: Есть ли варианты пробной версии Aspose.BarCode?**  
A: Конечно. Бесплатная пробная лицензия доступна со страницы бесплатного скачивания Aspose.BarCode, предоставляя полный доступ к API для оценки.

**Q: Как сгенерировать QR‑код высокого разрешения для печати?**  
A: Установите свойство `setResolutionDpi` у `BarcodeGenerator` перед вызовом `generateBarCodeImage()`, затем сохраните результат в без потерь формате, например PNG.

**Q: Что делать, если комбинированное изображение обрезано?**  
A: Убедитесь, что расчёты `offset` и размеров холста правильно учитывают высоту всех штрихкодов; увеличение высоты холста или уменьшение размеров отдельных штрихкодов решает большинство проблем обрезки.

---

**Последнее обновление:** 2026-10-19  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Связанные руководства

- [Как создать изображение штрихкода Java – добавить границу с Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Как генерировать штрихкод Java: сохранять в потоки с Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Как генерировать штрихкод Java и печатать штрихкод с Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}