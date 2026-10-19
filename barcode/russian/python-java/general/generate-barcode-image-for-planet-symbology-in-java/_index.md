---
category: general
date: 2026-10-18
description: Создайте изображение штрихкода для символики Planet с использованием
  Java. Узнайте, как создать штрихкод Planet с пользовательскими размерами штрихкода
  и пустыми полосами.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: ru
lastmod: 2026-10-18
og_description: Создайте изображение штрихкода для символики Planet на Java. Этот
  учебник показывает, как создать штрихкод Planet с пользовательскими размерами и
  контурными полосами.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Создать изображение штрихкода для символики планет — руководство по Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Создать изображение штрихкода для символогии Planet в Java
url: /ru/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание изображения штрихкода для символьной системы Planet на Java

Если вам нужно **создать изображение штрихкода** для символьной системы Planet, это руководство проведёт вас через весь процесс. Независимо от того, разрабатываете ли вы систему автоматизации почтовых операций или кастомное решение для отслеживания, вы узнаете, как **создать штрихкод Planet** с **пользовательскими размерами штрихкода** и контурными (пустыми) полосами.

В примере используется библиотека Aspose.BarCode for Java, предоставляющая удобный API для всех основных стандартов штрихкодов. Дополнительные инструменты обработки изображений не требуются, и код работает на любой среде выполнения Java 8+.

## Требования

* Установлен Java 8 или новее (руководство тестировалось с JDK 17).
* Maven или Gradle для управления зависимостями.
* Базовое знакомство с синтаксисом Java и концепцией штрихкода.

Если вы новичок в Maven, вы можете создать простой проект с помощью `mvn archetype:generate` и добавить зависимость Aspose.BarCode, показанную ниже.

## Добавление зависимости Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Подсказка:** Зафиксируйте номер версии, чтобы избежать неожиданных несовместимых изменений при обновлении библиотеки.

## Шаг 1: Инициализация генератора штрихкода для символьной системы Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Почему этот шаг важен:**  
`EncodeTypes.PLANET` указывает библиотеке использовать спецификацию штрихкода Planet, которая обычно применяется в почтовых службах. Строка данных `"123456"` является полезной нагрузкой, которая появится в сгенерированном изображении.

## Шаг 2: Установка пользовательских размеров штрихкода (X‑размер)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Почему этот шаг важен:**  
*X‑размер* определяет ширину каждой отдельной полосы. Установив его в **4 пикселя**, вы получаете штрихкод, который легко читается большинством сканеров и при этом помещается на стандартную этикетку. Изменение этого значения — основной способ добиться **пользовательских размеров штрихкода**.

## Шаг 3: Использовать пустые (контурные) полосы вместо сплошных

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Почему этот шаг важен:**  
`setFilledBars(false)` указывает рендереру рисовать только контуры полос, оставляя внутреннюю часть прозрачной. Этот стиль часто требуется для почтовых штрихкодов, где фон может содержать другую печатную информацию.

## Шаг 4: Сохранить изображение штрихкода в формате PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Почему этот шаг важен:**  
Выбор `BarCodeImageFormat.Png` даёт вам без потерь изображение, сохраняющее чёткие края контурных полос. Путь к файлу может быть любой директории, в которую у вас есть права записи; в примере используется папка `output`, расположенная относительно корня проекта.

### Ожидаемый результат

Запуск программы создаёт файл, похожий на изображение ниже:

![Generated barcode image for Planet symbology](/images/planet-barcode.png){.align-center alt="Сгенерированное изображение штрихкода, показывающее штрихкод Planet с пустыми контурными полосами"}

Изображение показывает **штрихкод Planet** с тонкими, пустыми полосами, точно соответствующими установленным вами пользовательским размерам.

## Распространённые варианты и граничные случаи

| Ситуация | Корректировка |
|-----------|------------|
| **Разная длина данных** | Штрихкоды Planet поддерживают до 12 цифровых символов. Соответственно измените второй аргумент конструктора. |
| **Более высокое разрешение** | Увеличьте X‑размер (`setPixels`) или задайте `YDimension` для контроля высоты полос. |
| **Цветной штрихкод** | Используйте `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` для изменения цвета полос. |
| **Сохранение в SVG** | Замените `BarCodeImageFormat.Png` на `BarCodeImageFormat.Svg` для векторного вывода. |
| **Запуск на Android** | Используйте совместимую с Android версию Aspose.BarCode для Android и замените пути файловой системы на `Context.getFilesDir()`. |

> **Осторожно:** Установка X‑размера слишком низким (например, 1 пиксель) может сделать штрихкод нечитаемым на принтерах с низким разрешением. Всегда проверяйте с реальным сканером после изменения размеров.

## Полный исходный код для быстрого копирования

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Скопируйте код в файл с именем `PlanetBarcodeDemo.java`, разместите его в `src/main/java/com/example/barcode/`, выполните `mvn compile exec:java`, и вы увидите результат **создания изображения штрихкода** в папке `output`.

## Заключение

Теперь вы знаете, как **создать изображение штрихкода** для символьной системы Planet на Java, как **создать штрихкод Planet** с **пользовательскими размерами штрихкода**, и как переключиться с сплошных полос на пустые для более чистого визуального стиля. Полный пример демонстрирует каждый необходимый вызов API, от инициализации генератора до сохранения PNG‑файла.

**Следующие шаги** – изучите другие типы штрихкодов (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) и поэкспериментируйте с дополнительными параметрами изображения, такими как цвет фона, отступы и настройки DPI. Если необходимо встроить штрихкод в PDF, объедините этот код с Aspose.PDF for Java для бесшовного сквозного решения.

Удачной разработки!

## Что вам следует изучить дальше?

Следующие руководства охватывают тесно связанные темы, опирающиеся на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, помогающими освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как создать штрихкод Planet с заполненными и пустыми полосами](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Создание изображения штрихкода Planet – пошаговое руководство](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Как генерировать штрихкод на Java: создать точное изображение штрихкода](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}