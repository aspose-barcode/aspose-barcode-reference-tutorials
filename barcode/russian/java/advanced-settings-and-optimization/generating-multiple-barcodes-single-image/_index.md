---
date: 2026-04-03
description: Узнайте, как создавать QR‑коды в Java и генерировать несколько штрихкодов
  на одном изображении с помощью Aspose.BarCode for Java. Включает настройку, код
  и устранение неполадок.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Создание нескольких штрихкодов на одном изображении
second_title: Aspose.BarCode Java API
title: Создать QR‑код в Java – Сгенерировать несколько штрихкодов на одном изображении
url: /ru/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание QR Code Java – Генерация нескольких штрихкодов на одном изображении

## Введение

В этом руководстве вы узнаете **how to create QR code java** и объедините несколько разных типов штрихкодов в одно изображение с помощью **Aspose.BarCode for Java**. Независимо от того, нужен ли вам компактный QR‑ярлык, штрихкод продукта или сочетание 2‑D и линейных символогий, это руководство проведёт вас через каждый шаг — от настройки проекта до сохранения окончательного объединённого изображения — чтобы вы могли сразу начать интегрировать генерацию штрихкодов в свои Java‑приложения.

## Быстрые ответы
- **What library should I use?** Какую библиотеку следует использовать?  
  Aspose.BarCode for Java предоставляет самый полный набор символогий.  
- **Can I generate different barcode types together?** Могу ли я генерировать разные типы штрихкодов вместе?  
  Да, вы можете смешивать CODE_39, QR, AZTEC и другие на одном холсте.  
- **Do I need a license for development?** Нужна ли лицензия для разработки?  
  Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Which Java version is supported?** Какая версия Java поддерживается?  
  Java 8 и новее полностью совместимы.  
- **Is the output format configurable?** Можно ли настроить формат вывода?  
  Вы можете экспортировать объединённое изображение в PNG, JPEG, BMP и т.д.  

## Что такое create QR code java?

Создание QR‑кода в Java означает преобразование текстовой строки в двумерную матрицу, которую могут сканировать смартфоны или счётчики штрихкодов. **Aspose.BarCode for Java** обрабатывает кодирование и рендеринг, позволяя сосредоточиться на бизнес‑логике вместо низкоуровневой обработки изображений.

## Почему использовать Aspose.BarCode Java для generate barcodes java?

- **Broad symbology support** – от классических линейных кодов до современных 2‑D матриц.  
- **High‑quality rendering** – сглаженный вывод, работающий на любом устройстве.  
- **Simple API** – создавайте, настраивайте и комбинируйте штрихкоды всего несколькими вызовами методов.  
- **No external dependencies** – всё работает на JVM без нативных библиотек.  

## Требования

Перед тем как приступить к руководству, убедитесь, что у вас есть следующее:

- Базовое понимание программирования на Java.  
- Установленный Java Development Kit (JDK) на вашей системе.  
- Библиотека Aspose.BarCode for Java скачана и настроена. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).  
- Интегрированная среда разработки (IDE), такая как Eclipse или IntelliJ IDEA.  

## Импорт пространств имён

В вашем Java‑проекте импортируйте необходимые пространства имён для доступа к функционалу Aspose.BarCode. Добавьте следующие инструкции импорта в начале вашего Java‑класса:

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

## Шаг 1: Установить каталог ресурсов

Определите путь к каталогу ресурсов, где будут сохраняться сгенерированные штрихкоды. Этот каталог важен для организации и управления вашими изображениями штрихкодов.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Шаг 2: Создать коллекцию штрихкодов

Инициализируйте `HashMap` для хранения данных штрихкодов. Каждая запись в коллекции представляет штрихкод с соответствующим типом кодирования.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Шаг 3: Сгенерировать изображения штрихкодов

Пройдитесь по коллекции и сгенерируйте изображения штрихкодов с помощью библиотеки Aspose.BarCode. Сохраните изображения в `ArrayList` для дальнейшей обработки.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Шаг 4: Создать объединённое изображение

Определите максимальную ширину и общую высоту изображений штрихкодов. Создайте `BufferedImage`, чтобы объединить отдельные изображения штрихкодов в одно итоговое изображение.

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

## Шаг 5: Сохранить результат

Сохраните окончательное объединённое изображение в указанное файловое расположение.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Общие сценарии использования для генерации нескольких штрихкодов

- **Packaging labels** – объединить коды продукта, партии и доставки на одной этикетке.  
- **Event tickets** – включить QR, Data Matrix и Code 128 для разных пунктов сканирования.  
- **Inventory management** – отображать SKU, данные RFID‑метки и серийные номера вместе для быстрой проверки.  

## Устранение неполадок и советы

- **Image size issues** – отрегулируйте переменную `offset`, чтобы увеличить или уменьшить расстояние между штрихкодами.  
- **Unsupported symbology** – проверьте, поддерживает ли ваша версия Aspose.BarCode нужный тип штрихкода.  
- **Performance** – переиспользуйте один объект `Graphics`, если генерируете много изображений в цикле.  

## Часто задаваемые вопросы

**Q1: Can I customize the appearance of individual barcodes in the generated image?**  
В: Могу ли я настроить внешний вид отдельных штрихкодов в сгенерированном изображении?  
A1: Да, Aspose.BarCode предоставляет обширные возможности настройки внешнего вида штрихкода, позволяя адаптировать стиль каждого штрихкода под ваши предпочтения.

**Q2: Is Aspose.BarCode compatible with different barcode symbologies?**  
В: Совместим ли Aspose.BarCode с различными символогиями штрихкодов?  
A2: Абсолютно! Aspose.BarCode поддерживает широкий спектр символогий, включая CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 и AZTEC, как показано в этом руководстве.

**Q3: How can I integrate Aspose.BarCode into my Java project?**  
В: Как интегрировать Aspose.BarCode в мой Java‑проект?  
A3: Просто скачайте библиотеку Aspose.BarCode for Java с [here](https://releases.aspose.com/barcode/java/) и следуйте инструкциям по установке, приведённым в документации.

**Q4: Can I use Aspose.BarCode for commercial applications?**  
В: Можно ли использовать Aspose.BarCode в коммерческих приложениях?  
A4: Да, вы можете получить лицензию [here](https://purchase.aspose.com/buy) для коммерческого использования Aspose.BarCode.

**Q5: Are there any trial options available for Aspose.BarCode?**  
В: Есть ли варианты пробной версии Aspose.BarCode?  
A5: Конечно! Вы можете изучить возможности Aspose.BarCode, получив бесплатную пробную лицензию [here](https://releases.aspose.com/).

**Q6: How do I generate a high‑resolution QR code for printing?**  
В: Как сгенерировать QR‑код высокого разрешения для печати?  
A6: Установите нужное DPI в `BarcodeGenerator` перед вызовом `generateBarCodeImage()`, затем сохраните изображение в без потерь формате, например PNG.

**Q7: What should I do if the combined image appears truncated?**  
В: Что делать, если объединённое изображение обрезано?  
A7: Убедитесь, что расчёты `offset` и размеров холста правильно учитывают высоту всех штрихкодов; увеличение высоты холста или уменьшение размеров отдельных штрихкодов решает большинство проблем с обрезкой.

---

**Последнее обновление:** 2026-04-03  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}