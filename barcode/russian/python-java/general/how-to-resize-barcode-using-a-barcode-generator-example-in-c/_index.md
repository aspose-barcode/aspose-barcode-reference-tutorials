---
category: general
date: 2026-10-08
description: Узнайте, как изменить размер изображений штрихкода с помощью примера
  генератора штрихкодов на C#, изменив высоту полосы с 30 px до 60 px всего в несколько
  строк кода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: ru
lastmod: 2026-10-08
og_description: Как быстро изменить размер штрихкода с помощью примера генератора
  штрихкодов на C#. Регулируйте высоту полос, сохраняйте PNG‑файлы и избегайте распространённых
  ошибок.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Как изменить размер штрих‑кода в C# – пошаговый пример генератора
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Как изменить размер штрихкода с помощью примера генератора штрихкодов на C#
url: /ru/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как изменить размер штрихкода с помощью примера генератора штрихкодов на C#

Если вам нужно **изменить размер штрихкода** в проекте .NET, это руководство покажет полное решение. Вы увидите лаконичный **barcode generator example C#**, который меняет высоту полос с 30 px до 60 px и сохраняет каждую версию как PNG‑файл.

Изменение размера штрихкода часто требуется, когда одни и те же данные должны отображаться на чеках, этикетках или страницах продукта в разных визуальных масштабах. Вместо редактирования растрового изображения во внешнем редакторе вы можете программно изменить размеры штрихкода, сохранив целостность данных.

В этом руководстве вы:

* Настроите генератор штрихкода DataBar Omni‑Directional.  
* Измените параметры X‑dimension и высоты полос.  
* Сохраните два изображения с разными высотами.  
* Поймёте, почему изменение высоты полос работает и на какие крайние случаи следует обратить внимание.

> **Prerequisite** – У вас есть среда разработки .NET (Visual Studio 2022 или новее) и библиотека штрихкодов, предоставляющая `BarcodeGenerator`, `EncodeTypes` и `BarCodeImageFormat`. Код работает с последней версией библиотеки на октябрь 2026 года.

## Prerequisites for the barcode generator example C#

Прежде чем начать, убедитесь, что у вас есть:

| Item | Reason |
|------|--------|
| .NET 6.0 SDK или новее | Предоставляет среду выполнения и языковые возможности, используемые в примере. |
| Библиотека штрихкодов (например, Aspose.BarCode, Dynamsoft или любая библиотека, раскрывающая `BarcodeGenerator`) | Содержит перечисление `EncodeTypes.DatabarOmniDirectional` и методы экспорта изображений. |
| Папка, в которую можно записывать (например, `C:\Temp\Barcodes\`) | Пример сохраняет PNG‑файлы в этом месте. |
| Базовые знания C# | Руководство предполагает знакомство с классами, свойствами и интерполяцией строк. |

Установите библиотеку через NuGet, если вы ещё этого не сделали:

```bash
dotnet add package Aspose.BarCode
```

Замените имя пакета на то, которое вы действительно используете; показанный ниже API‑интерфейс типичен для большинства SDK штрихкодов.

## How to resize barcode – step 1: create the generator

Первый шаг – создать экземпляр `BarcodeGenerator` с нужной символьной системой и данными. В этом примере мы генерируем штрихкод **DataBar Omni‑Directional**, который кодирует значение GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Why this matters:** Перечисление `EncodeTypes.DatabarOmniDirectional` сообщает библиотеке, какой стандарт штрихкода использовать. Строка данных следует GS1 Application Identifier `(01)` для 14‑значного GTIN, что обеспечивает соответствие глобальным торговым стандартам.

## How to resize barcode – step 2: define the module width and initial bar height

Визуальный размер штрихкода зависит от двух параметров:

* **X‑dimension** – ширина самой маленькой полосы (модуля). Измеряется в пикселях или миллиметрах.  
* **Bar height** – вертикальная длина полос.

Установка этих значений до сохранения гарантирует, что полученное изображение будет соответствовать требуемым размерам.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explanation:** X‑dimension в 2 px даёт компактный штрихкод, который всё равно надёжно сканируется. Высота 30 px – обычный дефолт для небольших этикеток. Вы можете менять X‑dimension независимо от высоты, если нужен более плотный или более разреженный узор.

## How to resize barcode – step 3: save the first image (30 px height)

Теперь экспортируем штрихкод в PNG‑файл. Метод `Save` принимает путь к файлу и перечисление формата изображения.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Result:** `DatabarBarHeight30Pixels.png` содержит штрихкод высотой 30 px. Откройте файл в любом просмотрщике изображений, чтобы проверить размеры.

## How to resize barcode – step 4: change the bar height to 60 px

Чтобы создать большую версию, просто измените свойство `BarHeight`. Генератор использует те же данные и X‑dimension, поэтому узор штрихкода остаётся идентичным — меняется только визуальный размер.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Why this works:** Движок рендеринга штрихкода рассчитывает геометрию каждой полосы «по запросу». Обновление свойства высоты перед следующим вызовом `Save` инициирует новую растеризацию с новыми размерами.

## How to resize barcode – step 5: save the second image (60 px height)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Теперь у вас есть два PNG‑файла: один маленький (30 px), другой больший (60 px), готовые к использованию на этикетках разных размеров.

## Full source code for the barcode generator example C#

Ниже приведена полная, готовая к запуску программа. Скопируйте её в новый консольный проект, чтобы сразу протестировать.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Expected output in the console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

После выполнения откройте оба PNG‑файла, чтобы увидеть визуальную разницу. Оба штрихкода кодируют одно и то же значение GTIN‑14 и будут сканироваться одинаково, независимо от высоты.

## Why adjusting bar height is safe for scanning

Сканеры штрихкодов читают узор светлых и тёмных модулей, а не абсолютное количество пикселей. Пока **X‑dimension** остаётся в пределах допуска сканера (обычно 0,5 mm‑2 mm в физических единицах), изменение высоты не влияет на читаемость. Библиотека автоматически масштабирует модули, сохраняя требуемые зоны тишины и выравнивающие паттерны.

## Common pitfalls and how to avoid them

| Pitfall | How to fix |
|---------|------------|
| **Output folder does not exist** | Вызовите `Directory.CreateDirectory(outputPath)` перед сохранением. |
| **Incorrect X‑dimension causing blurry scans** | Держите `XDimension.Pixels` между 1 px и 4 px для большинства принтеров; протестируйте на физическом сканере. |
| **Using a raster format for very large barcodes** | Переключитесь на `BarCodeImageFormat.Svg` для бесконечной масштабируемости без пикселизации. |
| **Forgetting to reset `BarHeight` before the second save** | Убедитесь, что новое значение высоты присвоено **до** повторного вызова `Save`. |

## Pro tip: generate multiple sizes in a loop

Если нужен диапазон высот (например, 30 px, 45 px, 60 px), простой цикл `foreach` уменьшит дублирование кода:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Такой подход хорошо масштабируется для пакетной обработки каталогов продуктов.

## Edge cases: different image formats and DPI settings

* **SVG output** – Используйте `BarCodeImageFormat.Svg` для получения векторного файла, который можно масштабировать без потери качества.  
* **High‑DPI PNG** – Установите `generator.Parameters.Image.DpiX` и `DpiY` в 300 или 600 для изображений, готовых к печати; высота полос всё равно измеряется в пикселях, поэтому увеличьте её пропорционально.  
* **Non‑standard symbologies** – Некоторые типы штрихкодов (например, QR Code) имеют отдельное свойство `Size` вместо `BarHeight`. Обратитесь к документации библиотеки для таких случаев.

## Testing the resized barcode

1. Откройте каждый PNG в просмотрщике изображений и проверьте пиксельные размеры (например, 150 × 30 px vs. 150 × 60 px).  
2. Распечатайте изображения в масштабе 100 %.  
3. Сканируйте их ручным сканером штрихкода или мобильным приложением. Декодированные данные должны совпадать.

## What Should You Learn Next?

Следующие руководства охватывают тесно связанные темы, расширяющие техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью рабочие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в собственных проектах.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}