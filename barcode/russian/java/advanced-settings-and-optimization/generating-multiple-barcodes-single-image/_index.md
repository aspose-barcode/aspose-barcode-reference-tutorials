---
date: 2025-12-10
description: Узнайте, как генерировать штрихкоды на одном изображении в Java с помощью
  Aspose.BarCode. Это руководство охватывает интеграцию Aspose Barcode Java и создание
  нескольких штрихкодов.
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

## Introduction

Если вы ищете надёжный способ **как генерировать штрих‑коды** в Java‑приложении, вы попали по адресу. С Aspose.BarCode for Java вы можете разместить несколько разных типов штрих‑кодов на одном изображении всего в несколько строк кода. Этот учебник проведёт вас через весь процесс — от настройки проекта до сохранения объединённого изображения — чтобы вы могли сразу начать использовать генерацию штрих‑кодов в своих решениях.

## Quick Answers
- **Какую библиотеку использовать?** Aspose.BarCode for Java предоставляет самый полный набор символогий.  
- **Могу ли я генерировать разные типы штрих‑кодов вместе?** Да, вы можете смешивать CODE_39, QR, AZTEC и другие на одном холсте.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; коммерческая лицензия требуется для продакшна.  
- **Какая версия Java поддерживается?** Java 8 и новее полностью совместимы.  
- **Можно ли настроить формат вывода?** Вы можете экспортировать объединённое изображение в PNG, JPEG, BMP и др.

## What is “how to generate barcodes” in Java?
Генерация штрих‑кодов означает преобразование строки данных в визуальный шаблон, который могут считывать сканеры. Aspose.BarCode автоматически обрабатывает кодирование, рендеринг и создание изображения, позволяя вам сосредоточиться на бизнес‑логике, а не на низкоуровневой обработке изображений.

## Why use Aspose.BarCode for Java barcode generation?
- **Широкая поддержка символогий** — от классических линейных кодов до современных 2‑D матриц.  
- **Высококачественный рендеринг** — сглаженный вывод, работающий на любом устройстве.  
- **Простой API** — создавайте, настраивайте и комбинируйте штрих‑коды всего несколькими вызовами методов.  
- **Отсутствие внешних зависимостей** — всё работает на JVM без нативных библиотек.

## Prerequisites

Перед тем как приступить к учебнику, убедитесь, что у вас есть следующие требования:

- Базовые знания программирования на Java.  
- Установленный Java Development Kit (JDK).  
- Библиотека Aspose.BarCode for Java загружена и настроена. Вы можете скачать её [здесь](https://releases.aspose.com/barcode/java/).  
- Интегрированная среда разработки (IDE), например Eclipse или IntelliJ IDEA.

## Import Namespaces

В вашем Java‑проекте импортируйте необходимые пространства имён для доступа к функционалу Aspose.BarCode. Добавьте следующие операторы импорта в начале вашего Java‑класса:

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

## Step 1: Set the Resource Directory

### Шаг 1: Установите каталог ресурсов

Определите путь к каталогу ресурсов, где будут сохраняться сгенерированные штрих‑коды. Этот каталог важен для организации и управления вашими изображениями штрих‑кодов.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Step 2: Create a Collection of Barcodes

### Шаг 2: Создайте коллекцию штрих‑кодов

Инициализируйте `HashMap` для хранения данных штрих‑кода. Каждая запись в коллекции представляет штрих‑код с соответствующим типом кодирования.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Step 3: Generate Barcode Images

### Шаг 3: Сгенерируйте изображения штрих‑кодов

Итерируйте по коллекции и генерируйте изображения штрих‑кодов с помощью библиотеки Aspose.BarCode. Сохраняйте изображения в `ArrayList` для дальнейшей обработки.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Step 4: Create a Combined Image

### Шаг 4: Создайте объединённое изображение

Определите максимальную ширину и общую высоту изображений штрих‑кодов. Создайте `BufferedImage` для объединения отдельных изображений штрих‑кодов в одно итоговое изображение.

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

## Step 5: Save the Result

### Шаг 5: Сохраните результат

Сохраните окончательное объединённое изображение в указанное место файла.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Common Use Cases for Generating Multiple Barcodes

### Общие сценарии использования генерации нескольких штрих‑кодов

- **Этикетки упаковки** — объединяйте коды продукта, партии и доставки на одной этикетке.  
- **Билеты на мероприятия** — внедряйте QR, Data Matrix и Code 128 идентификаторы для разных пунктов сканирования.  
- **Управление запасами** — отображайте SKU, данные RFID‑метки и серийные номера вместе для быстрой проверки.

## Troubleshooting & Tips

### Устранение неполадок и советы

- **Проблемы с размером изображения** — отрегулируйте переменную `offset`, чтобы увеличить или уменьшить расстояние между штрих‑кодами.  
- **Неподдерживаемая симвология** — проверьте, поддерживает ли ваша версия Aspose.BarCode требуемый тип штрих‑кода.  
- **Производительность** — переиспользуйте один объект `Graphics`, если генерируете много изображений в цикле.

## FAQ's

### Q1: Can I customize the appearance of individual barcodes in the generated image?

**Вопрос:** Могу ли я настроить внешний вид отдельных штрих‑кодов в сгенерированном изображении?  
**Ответ:** Да, Aspose.BarCode предоставляет обширные возможности настройки внешнего вида штрих‑кода, позволяя адаптировать стиль каждого штрих‑кода под ваши предпочтения.

### Q2: Is Aspose.BarCode compatible with different barcode symbologies?

**Вопрос:** Совместим ли Aspose.BarCode с различными символогиями штрих‑кодов?  
**Ответ:** Абсолютно! Aspose.BarCode поддерживает широкий спектр символогий, включая CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 и AZTEC, как показано в этом учебнике.

### Q3: How can I integrate Aspose.BarCode into my Java project?

**Вопрос:** Как интегрировать Aspose.BarCode в мой Java‑проект?  
**Ответ:** Просто скачайте библиотеку Aspose.BarCode for Java с [здесь](https://releases.aspose.com/barcode/java/) и следуйте инструкциям по установке, приведённым в документации.

### Q4: Can I use Aspose.BarCode for commercial applications?

**Вопрос:** Могу ли я использовать Aspose.BarCode в коммерческих приложениях?  
**Ответ:** Да, вы можете получить лицензию [здесь](https://purchase.aspose.com/buy) для использования Aspose.BarCode в коммерческих целях.

### Q5: Are there any trial options available for Aspose.BarCode?

**Вопрос:** Есть ли варианты пробной версии Aspose.BarCode?  
**Ответ:** Конечно! Вы можете изучить возможности Aspose.BarCode, получив бесплатную пробную лицензию [здесь](https://releases.aspose.com/).

**Additional Questions**

**Вопрос:** Как сгенерировать QR‑код специально в Java?  
**Ответ:** Используйте `EncodeTypes.QR` при создании экземпляра `BarcodeGenerator`, как показано в примере коллекции.

**Вопрос:** Поддерживает ли Aspose.BarCode вывод высокого разрешения для печати?  
**Ответ:** Да, вы можете указать DPI при сохранении изображения, чтобы соответствовать требованиям к качеству печати.

---

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}