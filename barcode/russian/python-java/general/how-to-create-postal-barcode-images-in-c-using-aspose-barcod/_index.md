---
category: general
date: 2026-10-21
description: Узнайте, как создавать изображения почтовых штрих‑кодов в C# с помощью
  Aspose.BarCode — генерировать штрих‑коды Planet и RM4SCC, управлять заполненными
  полосами и сохранять файлы PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: ru
lastmod: 2026-10-21
og_description: Создавайте изображения почтовых штрих‑кодов в C# с помощью Aspose.BarCode.
  В этом руководстве показано, как генерировать штрих‑коды Planet и RM4SCC, переключать
  заполненные полосы и сохранять файлы PNG.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Создание изображений почтовых штрих‑кодов в C# – пошаговое руководство
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Как создать изображения почтовых штрихкодов в C# с использованием Aspose.BarCode
url: /ru/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создавать изображения почтовых штрих‑кодов в C# с помощью Aspose.BarCode

Если вам нужно **создавать почтовый штрих‑код** в проекте .NET, это руководство покажет готовое, полностью рабочее решение. Вы увидите, как генерировать штрих‑коды Planet и RM4SCC, переключаться между заполненными и пустыми полосами и сохранять результаты в виде PNG‑файлов — всё это с помощью нескольких строк кода на C#.

Надёжная генерация почтовых штрих‑кодов важна для автоматизации рассылки, массовой печати этикеток и интеграции с логистическими платформами. К концу этого урока у вас будет переиспользуемый фрагмент кода, который можно скопировать в любое консольное или веб‑приложение на C#.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports .NET)  
* An active **Aspose.BarCode** NuGet package (`Install-Package Aspose.BarCode`)  

These tools are sufficient to compile and run the example without additional dependencies.

## Пошаговое руководство по **созданию почтового штрих‑кода** изображений

The process consists of four logical steps:

1. Prepare the output folder.  
2. Generate a Planet barcode with filled bars (the default appearance).  
3. Generate a Planet barcode with empty bars.  
4. Generate an RM4SCC barcode with filled bars.

Each step is explained below, and the full source code appears after the explanations.

### 1. Prepare the output folder

The barcode images need a writable directory. The code creates the folder if it does not exist, preventing a runtime `DirectoryNotFoundException`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Почему это важно*: Отсутствующая директория останавливает программу до генерации любого штрих‑кода. Использование `Directory.CreateDirectory` безопасно, так как ничего не делает, если папка уже существует.

### 2. Generate a Planet barcode with filled bars

Planet barcodes are used by many postal services for domestic mail. The default `FilledBars` setting renders solid bars, which is the most common visual style.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Explanation*:  
* `EncodeTypes.Planet` tells Aspose.BarCode to use the Planet standard.  
* The data string `"123456"` is a valid Planet payload (6 numeric characters).  
* `XDimension.Pixels = 4` yields a bar width of 4 px, which balances readability and file size.  
* `Save` writes the image as PNG, a loss‑less format suitable for further processing.

### 3. Generate a Planet barcode with empty bars

Some postal specifications require **empty** (hollow) bars. You can toggle this behavior via the `FilledBars` property.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Tip*: When switching between filled and empty bars, keep the `XDimension` value unchanged to maintain consistent sizing across images.

### 4. Generate an RM4SCC barcode with filled bars

RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like Planet, the default appearance uses solid bars.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Why RM4SCC*: The RM4SCC format encodes a 6‑digit numeric string plus a checksum, making it ideal for UK mailing services.

### Full source code in one block

Copy the following snippet into a new C# console project. It compiles with .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Expected output

Running the program prints a confirmation line and creates three files:

* `PostalPlanetFilledBars.png` – solid‑bar Planet barcode  
* `PostalPlanetEmptyBars.png` – hollow‑bar Planet barcode  
* `PostalRM4SCCFilledBars.png` – solid‑bar RM4SCC barcode  

Each image is 4 px per bar wide, suitable for screen preview or print‑ready PDF embedding.

## Common questions and edge‑case handling

| Question | Answer |
|----------|--------|
| **What if the data string is invalid?** | Aspose.BarCode throws `ArgumentException`. Validate the input length (Planet = 6 numeric, RM4SCC = 6 numeric) before creating the generator. |
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Gif`, `Bmp`, or `Tiff` as needed. |
| **How do I adjust bar height?** | Use `planetFilled.Parameters.Barcode.BarHeight` (default is 50 px). |
| **Is it safe to use this code in a web API?** | Absolutely. The generator is thread‑safe for read‑only operations, but instantiate a new `BarcodeGenerator` per request to avoid shared state. |
| **What about other postal standards?** | Aspose.BarCode also supports `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail`, etc. The same pattern applies—just change the `EncodeTypes` value. |

## Conclusion

You now know how to **create postal barcode** images in C# with Aspose.BarCode, covering both Planet and RM4SCC formats and demonstrating how to toggle filled versus empty bars. The complete, runnable example can be dropped into any .NET project, giving you immediate visual output.

### Next steps

* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.  
* **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor` to match your branding.  
* **Integrate into a web service** – expose the generation logic via ASP.NET Core endpoints for on‑demand barcode creation.  

By mastering these techniques you’ll be able to **generate planet barcode** images and answer “**how to generate barcode C#**” queries with confidence, whether you’re building a desktop mailing tool or a cloud‑based shipping API. Happy coding!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}