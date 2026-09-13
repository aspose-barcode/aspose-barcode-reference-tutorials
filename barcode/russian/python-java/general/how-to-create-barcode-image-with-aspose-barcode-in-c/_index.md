---
category: general
date: 2026-09-13
description: Создайте изображение штрихкода с помощью Aspose.Barcode на C#. Узнайте,
  как генерировать PNG‑изображения штрихкода, задавать пользовательские размеры штрихкода
  и эффективно сохранять файлы штрихкода.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate barcode png
- how to save barcode
- aspose barcode generator
- custom barcode dimensions
language: ru
lastmod: 2026-09-13
og_description: Создайте изображение штрихкода с помощью Aspose.Barcode на C#. Это
  руководство показывает, как генерировать PNG‑изображения штрихкода, управлять пользовательскими
  размерами и сохранять файлы штрихкода.
og_image_alt: Screenshot of a barcode image created with Aspose.Barcode in C#
og_title: Создайте изображение штрих‑кода с помощью Aspose.Barcode – пошаговое руководство
  по C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create barcode image using Aspose.Barcode in C#. Learn to generate
    barcode PNG, set custom barcode dimensions, and save barcode files efficiently.
  headline: How to create barcode image with Aspose.Barcode in C#
  type: TechArticle
- description: Create barcode image using Aspose.Barcode in C#. Learn to generate
    barcode PNG, set custom barcode dimensions, and save barcode files efficiently.
  name: How to create barcode image with Aspose.Barcode in C#
  steps:
  - name: Initialise the Aspose barcode generator
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.Generation;'
  - name: Set common barcode parameters (pixel‑size of the smallest bar)
    text: '```csharp // Set the X‑dimension – the width of the narrowest bar element,
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;'
  - name: Generate barcode PNG with a 30 px height
    text: '```csharp // Configure a 30 px high barcode. barcodeGenerator.Parameters.Barcode.BarHeight.Pixels
      = 30;'
  - name: Change the height to 60 px and save a second image
    text: '```csharp // Adjust the bar height to 60 px for a larger visual representation.
      barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;'
  - name: Full, runnable example
    text: Below is a complete console application that puts all the steps together.
      Copy the code into a new `.csproj` project and run it.
  type: HowTo
tags:
- Aspose.Barcode
- C#
- barcode generation
- PNG
- custom dimensions
title: Как создать изображение штрихкода с помощью Aspose.Barcode на C#
url: /ru/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать изображение штрихкода с Aspose.Barcode на C#

Если вам нужно **создать изображение штрихкода** в .NET‑приложении, Aspose.Barcode делает это простым. В этом руководстве показано, как **создать PNG‑изображение штрихкода**, настроить размеры штрихкода и правильно **сохранить файлы штрихкода** на диск.

Вы научитесь:

* Инициализировать **генератор штрихкодов Aspose** для символа DataBar Omni‑directional.  
* Настроить X‑dimension и высоту полосы, чтобы удовлетворить требование **пользовательских размеров штрихкода**.  
* Экспортировать результат в PNG‑файл, охватывая шаг **как сохранить штрихкод** для высот 30 px и 60 px.  

Внешние инструменты не требуются — достаточно пакета Aspose.Barcode for .NET NuGet и среды выполнения .NET 6+.

---

## Что вам понадобится перед началом

| Prerequisite | Reason |
|--------------|--------|
| Visual Studio 2022 (или любой C# IDE) | Для компиляции и запуска примера консольного приложения |
| .NET 6 SDK или новее | Предоставляет среду выполнения для кода |
| Aspose.Barcode for .NET NuGet package | Библиотека, содержащая `BarcodeGenerator` |
| Разрешение на запись в папку на диске | Требуется для **как сохранить штрихкод** изображений |

Install the NuGet package with the following command:

```bash
dotnet add package Aspose.Barcode
```

---

## Как создать изображение штрихкода с Aspose.Barcode

В следующих разделах рассматриваются каждый шаг, объясняя **почему** код написан именно так, а не только **что** он делает.

### Шаг 1: Инициализация генератора штрихкодов Aspose

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Create a DataBar Omni‑directional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

// Why this matters:
// * `EncodeTypes.DatabarOmniDirectional` selects the specific symbology.
// * The string "(01)12345678901231" follows GS1 Application Identifier (01) for GTIN.
// * Instantiating `BarcodeGenerator` prepares all subsequent parameter settings.
```

### Шаг 2: Установка общих параметров штрихкода (размер в пикселях самой узкой полосы)

```csharp
// Set the X‑dimension – the width of the narrowest bar element, in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Why this matters:
// The X‑dimension controls overall visual density. A value of 2 px is a good default for screen display.
```

### Шаг 3: Генерация PNG‑штрихкода с высотой 30 px

```csharp
// Configure a 30 px high barcode.
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the barcode as a PNG image.
string output30 = @"C:\Barcodes\DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
```

**Как это удовлетворяет “generate barcode png”**:  
`BarCodeImageFormat.Png` сообщает Aspose отрисовать штрихкод в виде без потерь PNG‑файла, что идеально подходит для дальнейшей обработки или печати.

### Шаг 4: Изменить высоту до 60 px и сохранить второе изображение

```csharp
// Adjust the bar height to 60 px for a larger visual representation.
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image.
string output60 = @"C:\Barcodes\DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
```

**Как это покрывает “how to save barcode”**:  
Метод `Save` записывает изображение в файловую систему по указанному пути. Вы можете повторить вызов с разными параметрами, чтобы создать несколько изображений из одного экземпляра генератора.

### Полный, исполняемый пример

Ниже представлено полное консольное приложение, объединяющее все шаги. Скопируйте код в новый проект `.csproj` и запустите его.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for a DataBar Omni‑directional barcode.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (width of the smallest bar).
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create a 30 px high PNG.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"C:\Barcodes\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // 4️⃣ Create a 60 px high PNG.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"C:\Barcodes\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

**Expected output** (console):

```
Saved 30 px barcode to C:\Barcodes\DatabarBarHeight30Pixels.png
Saved 60 px barcode to C:\Barcodes\DatabarBarHeight60Pixels.png
```

После выполнения вы найдете два PNG‑файла в `C:\Barcodes`. Оба файла содержат корректный символ DataBar Omni‑directional, отличающийся только высотой полосы.

---

## Генерация PNG‑штрихкода с пользовательскими размерами (расширенно)

Возможно, вам понадобится более точный контроль над визуальными размерами штрихкода, особенно при интеграции его в PDF‑документы или печатные этикетки. Aspose.Barcode предоставляет множество параметров:

| Parameter | Typical use |
|-----------|--------------|
| `XDimension.Pixels` | Контролирует ширину самой узкой полосы. |
| `BarHeight.Pixels` | Устанавливает общую высоту полосы. |
| `Margins` | Добавляет пустое пространство вокруг штрихкода. |
| `Resolution` | Определяет DPI для растровых изображений (влияет на качество PNG). |

Example of setting a 300 dpi resolution and 5 px margins:

```csharp
generator.Parameters.ImageResolution = 300; // 300 DPI
generator.Parameters.Barcode.Margins.All = 5; // 5 px on every side
```

Эти настройки полезны, когда штрихкод должен соответствовать строгим требованиям к печати.

---

## Как сохранять файлы штрихкода в разных форматах

Хотя PNG часто используется для веб‑ и UI‑сценариев, Aspose.Barcode также может выводить **JPEG**, **BMP**, **TIFF** и **SVG**. Переключение форматов требует лишь изменения перечисления `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\barcode.svg", BarCodeImageFormat.Svg);
```

Та же логика **как сохранить штрихкод** применяется независимо от формата, позволяя повторно использовать один и тот же экземпляр генератора.

---

## Распространённые подводные камни и профессиональные советы

* **Не переиспользуйте один и тот же генератор без сброса размеров** — изменение `BarHeight.Pixels` после вызова `Save` работает, но если также требуется изменить `XDimension.Pixels`, сбросьте их перед следующим сохранением, чтобы избежать нежелательного масштабирования.
* **Путь к файлу должен быть абсолютным или иметь разрешение на запись** — относительные пути разрешаются относительно рабочей директории, которая может отличать запуск из Visual Studio и из скомпилированного exe.
* **Проверьте возвращаемое значение `Save`** — он бросает `ArgumentException`, если путь недействителен, поэтому оберните вызовы в `try / catch` для продакшн‑кода.

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Заключение

Теперь вы знаете, как **создавать файлы изображений штрихкода** с помощью Aspose.Barcode, **генерировать PNG‑штрихкоды** с точными **пользовательскими размерами штрихкода**, и правильно **как сохранять файлы штрихкода** разных размеров. Регулируя `XDimension` и `BarHeight`, вы сможете удовлетворить точные визуальные требования любого процесса маркировки или печати.

Далее изучайте связанные темы, такие как **встраивание изображений штрихкода в PDF‑документы**, **пакетная генерация нескольких штрихкодов** или **использование других символогий**, например QR Code или Code 128. Каждый из этих сценариев опирается на те же базовые принципы, рассмотренные здесь.

Приятного кодинга и наслаждайтесь гибкостью, которую предоставляет **генератор** Aspose.Barcode!

## Что вам стоит изучить дальше?

Следующие руководства охватывают тесно связанные темы, которые опираются на техники, продемонстрированные в этом руководстве. Каждый ресурс включает полностью работающие примеры кода с пошаговыми объяснениями, чтобы помочь вам освоить дополнительные возможности API и исследовать альтернативные подходы к реализации в ваших проектах.

- [Как сгенерировать изображение штрихкода с настройкой дополнительного пространства с помощью Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Создать изображение штрихкода DotCode — строки и столбцы (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Как сгенерировать Aztec‑штрихкод с пользовательским соотношением сторон с помощью Aspose.BarCode для .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}