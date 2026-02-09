---
date: 2026-02-09
description: Узнайте, как генерировать штрихкоды на одном изображении в Java с помощью
  Aspose.BarCode, мощной библиотеки для генерации штрихкодов на Java. Это руководство
  охватывает интеграцию и генерацию нескольких штрихкодов.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Как сгенерировать штрихкоды на одном изображении в Java
url: /ru/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание нескольких штрих‑кодов на одном изображении в Java с Aspose.BarCode

## Введение

Если вы ищете надёжный способ **how to generate barcodes** в Java‑приложении, вы попали по адресу. С Aspose.BarCode for Java вы можете разместить несколько разных типов штрих‑кодов на одном изображении всего в несколько строк кода. Этот учебник проведёт вас через весь процесс — от настройки проекта до сохранения объединённого изображения — чтобы вы могли сразу начать использовать генерацию штрих‑кодов в своих решениях.

## Быстрые ответы
- **Какую библиотеку использовать?** Aspose.BarCode for Java предоставляет самый полный набор символогий.  
- **Могу ли я генерировать разные типы штрих‑кодов вместе?** Да, вы можете смешивать CODE_39, QR, AZTEC и другие на едином холсте.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется коммерческая лицензия.  
- **Какая версия Java поддерживается?** Java 8 и новее полностью совместимы.  
- **Можно ли настроить формат вывода?** Вы можете экспортировать объединённое изображение в PNG, JPEG, BMP и т.д.

## Что означает “how to generate barcodes” в Java?

Генерация штрих‑кодов означает преобразование строки данных в визуальный шаблон, который могут считывать сканеры. Aspose.BarCode автоматически обрабатывает шаги кодирования, рендеринга и создания изображения, позволяя вам сосредоточиться на бизнес‑логике, а не на низкоуровневой обработке изображений.

## Зачем генерировать несколько штрих‑кодов на одном изображении?

- **Экономия места** — объедините идентификаторы продукта, партии и доставки на одной этикетке.  
- **Многоступенчатые сканирования** — внедрите QR, Data Matrix и Code 128 для разных сканирующих станций.  
- **Упрощённый учёт активов** — отображайте SKU, данные RFID‑метки и серийные номера вместе для быстрой проверки.  

## Требования

Прежде чем приступать к учебнику, убедитесь, что у вас есть следующие требования:

- Базовые знания программирования на Java.  
- Установленный Java Development Kit (JDK) на вашей системе.  
- Библиотека Aspose.BarCode for Java загружена и настроена. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).  
- Интегрированная среда разработки (IDE), например Eclipse или IntelliJ IDEA.

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

## Шаг 1: Установите каталог ресурсов

Определите путь к каталогу ресурсов, где будут сохраняться сгенерированные штрих‑коды. Этот каталог важен для организации и управления вашими изображениями штрих‑кодов.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Шаг 2: Создайте коллекцию штрих‑кодов

Инициализируйте `HashMap` для хранения данных штрих‑кодов. Каждая запись в коллекции представляет штрих‑код с соответствующим типом кодирования.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Шаг 3: Сгенерируйте изображения штрих‑кодов

Итерируйте по коллекции и генерируйте изображения штрих‑кодов с помощью библиотеки Aspose.BarCode. Сохраните изображения в `ArrayList` для дальнейшей обработки.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Шаг 4: Создайте объединённое изображение

Определите максимальную ширину и общую высоту изображений штрих‑кодов. Создайте `BufferedImage`, чтобы объединить отдельные изображения штрих‑кодов в одно итоговое изображение.

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

## Шаг 5: Сохраните результат

Сохраните окончательное объединённое изображение в указанное место файла.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Как сгенерировать QR‑код в стиле Java?

Если вам нужен пример **generate qr code java**, просто замените запись в коллекции на `EncodeTypes.QR`. Тот же цикл сгенерирует QR‑код высокого разрешения, который может хранить URL‑адреса, контактную информацию или любые буквенно‑цифровые данные.

## Как сгенерировать штрих‑код Code 128 в Java?

Приведённый выше фрагмент уже демонстрирует **generate code 128 barcode** с использованием `EncodeTypes.CODE_128`. Code 128 идеален для логистики, так как поддерживает полный набор ASCII и обеспечивает компактное кодирование.

## Использование библиотеки генерации штрих‑кодов Java помимо Aspose

Хотя Aspose.BarCode является полнофункциональной **java barcode generation library**, вы также можете рассмотреть открытые альтернативы, такие как ZXing или Barcode4J, для лёгких сценариев. Тем не менее, Aspose предоставляет встроенную поддержку вывода высокого разрешения, множества символогий и простого комбинирования изображений — всё в одном пакете.

## Распространённые сценарии использования генерации нескольких штрих‑кодов

- **Этикетки упаковки** — объедините коды продукта, партии и доставки на одной этикетке.  
- **Билеты на мероприятия** — внедрите QR, Data Matrix и идентификаторы Code 128 для разных сканирующих станций.  
- **Управление запасами** — отображайте SKU, данные RFID‑метки и серийные номера вместе для быстрой проверки.

## Устранение проблем и советы

- **Проблемы с размером изображения** — отрегулируйте переменную `offset`, чтобы увеличить или уменьшить расстояние между штрих‑кодами.  
- **Неподдерживаемая симвология** — проверьте, поддерживает ли ваша версия Aspose.BarCode нужный тип штрих‑кода.  
- **Производительность** — переиспользуйте один объект `Graphics`, если генерируете много изображений в цикле.  
- **Управление памятью** — при работе с большим количеством штрих‑кодов рассмотрите возможность временного сохранения каждого изображения на диск, чтобы избежать чрезмерного использования кучи.

## Часто задаваемые вопросы

### Q1: Могу ли я настроить внешний вид отдельных штрих‑кодов в сгенерированном изображении?

A1: Да, Aspose.BarCode предоставляет обширные возможности настройки внешнего вида штрих‑кода, позволяя адаптировать стиль каждого штрих‑кода под ваши предпочтения.

### Q2: Совместим ли Aspose.BarCode с различными символогиями штрих‑кодов?

A2: Абсолютно! Aspose.BarCode поддерживает широкий спектр символогий, включая CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 и AZTEC, как показано в этом учебнике.

### Q3: Как интегрировать Aspose.BarCode в мой Java‑проект?

A3: Просто скачайте библиотеку Aspose.BarCode for Java [здесь](https://releases.aspose.com/barcode/java/) и следуйте инструкциям по установке, приведённым в документации.

### Q4: Могу ли я использовать Aspose.BarCode в коммерческих приложениях?

A4: Да, вы можете получить лицензию [здесь](https://purchase.aspose.com/buy) для использования Aspose.BarCode в коммерческих целях.

### Q5: Есть ли доступные пробные варианты для Aspose.BarCode?

A5: Конечно! Вы можете изучить возможности Aspose.BarCode, получив бесплатную пробную лицензию [здесь](https://releases.aspose.com/).

**Дополнительные вопросы**

**Q: Как сгенерировать QR‑код конкретно в Java?**  
A: Используйте `EncodeTypes.QR` при создании экземпляра `BarcodeGenerator`, как показано в примере коллекции.

**Q: Поддерживает ли Aspose.BarCode вывод высокого разрешения для печати?**  
A: Да, вы можете указать DPI при сохранении изображения, чтобы соответствовать требованиям к качеству печати.

---

**Последнее обновление:** 2026-02-09  
**Тестировано с:** Aspose.BarCode for Java 24.11  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}