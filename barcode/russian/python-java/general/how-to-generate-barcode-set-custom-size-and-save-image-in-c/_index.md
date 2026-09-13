---
category: general
date: 2026-09-13
description: Узнайте, как генерировать штрих‑код в C#, настраивать размер штрих‑кода
  и сохранять изображение штрих‑кода в формате PNG с помощью Aspose.BarCode. Полное
  пошаговое руководство.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: ru
lastmod: 2026-09-13
og_description: Как сгенерировать штрих‑код в C# с пользовательским размером и сохранить
  изображение штрих‑кода в формате PNG. Следуйте этому полному руководству по Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Как сгенерировать штрих‑код, задать пользовательский размер и сохранить
  изображение в C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Как сгенерировать штрих‑код, задать пользовательский размер и сохранить изображение
  в C#
url: /ru/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как генерировать штрихкоды пользовательского размера и сохранять изображение в C#

Если вам нужно **как генерировать штрихкод** в приложении .NET, этот учебник покажет полное решение. Вы увидите, как настроить **пользовательский размер штрихкода** и **сохранить изображение штрихкода** всего несколькими строками кода C#.

Генерация штрихкодов — распространённая задача для систем учёта, транспортных этикеток и точек продаж. К концу этого руководства у вас будет готовая программа, создающая два штрихкода DataBar‑Stacked‑Omnidirectional с разным соотношением сторон и сохраняющая их в файлы PNG на диск.

**Prerequisites**

- .NET 6.0 или новее (код также работает с .NET Framework 4.7+)
- Visual Studio 2022 или любой IDE для C#
- Aspose.BarCode for .NET (бесплатная пробная версия или лицензированный пакет NuGet)

---

## Как генерировать штрихкод с Aspose.BarCode

Библиотека Aspose.BarCode абстрагирует низкоуровневые детали стандартов штрихкодов, позволяя сосредоточиться на данных, которые нужно закодировать, и на визуальном виде, который требуется.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Почему важна каждая строка

| Шаг | Объяснение |
|------|-------------|
| **1️⃣ Create a generator** | Перечисление `EncodeTypes.DatabarStackedOmniDirectional` сообщает Aspose, какой тип штрихкода использовать. Строка `"(01)12345678901231"` следует формату данных GS1‑128, где `(01)` — идентификатор приложения для GTIN. |
| **2️⃣ Set X‑dimension** | `XDimension.Pixels` задаёт ширину одного модуля штрихкода (самой маленькой полоски). Изменение этого значения — основной способ получить **пользовательский размер штрихкода** без изменения закодированных данных. |
| **3️⃣ Set aspect ratio & save** | `DataBar.AspectRatio` контролирует соотношение высоты к ширине символов DataBar. Соотношение 15 даёт относительно короткий, широкий штрихкод, а 30 — более высокий. `Save` записывает визуальное представление в файл PNG, удовлетворяя требование **save barcode image**. |
| **4️⃣ Change aspect ratio & save again** | Повторное использование того же экземпляра генератора позволяет создавать несколько изображений с разными визуальными характеристиками, оставляя данные неизменными. |

---

## Настройка пользовательского размера штрихкода помимо X‑dimension

Хотя `XDimension.Pixels` задаёт ширину модуля, вы также можете точно настроить общие размеры штрихкода, комбинируя два свойства:

1. **`BarHeight`** — явная высота в пикселях.  
2. **`BarWidth`** — явная ширина в пикселях (перезаписывает X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** При печати штрихкодов всегда проверяйте сгенерированное изображение в конечном размере печати. Ширина модуля 2 px подходит для отображения на экране, но для печатных этикеток обычно требуется минимум 4 px, чтобы штрихкод оставался считываемым.

---

## Выбор правильного формата изображения для сохранения штрихкода

Aspose.BarCode поддерживает PNG, JPEG, BMP, GIF и TIFF. PNG — без потерь и сохраняет чёткие края, что делает его самым надёжным выбором для большинства приложений. Если нужен меньший файл для веба, JPEG с качеством 90 работает хорошо, но имейте в виду, что артефакты сжатия могут влиять на надёжность сканирования.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Полный, готовый к запуску пример

Ниже представлено автономное консольное приложение, которое вы можете скопировать, вставить и запустить. Оно демонстрирует **how to generate barcode**, изменение **custom barcode size** и **save barcode image** в двух разных форматах.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Ожидаемый вывод в консоли**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Четыре файла изображений появятся в каталоге программы


## Что изучать дальше?


Следующие учебники охватывают тесно связанные темы, построенные на техниках, продемонстрированных в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы в ваших проектах.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}