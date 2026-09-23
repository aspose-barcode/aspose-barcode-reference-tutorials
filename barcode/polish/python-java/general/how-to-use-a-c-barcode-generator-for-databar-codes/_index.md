---
category: general
date: 2026-09-23
description: Samouczek generatora kodów kreskowych w C# pokazuje, jak generować obrazy
  kodów kreskowych o niestandardowych proporcjach przy użyciu biblioteki Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: pl
lastmod: 2026-09-23
og_description: Przewodnik po generatorze kodów kreskowych w C# prowadzi Cię krok
  po kroku przez tworzenie obrazów kodów kreskowych, dostosowywanie proporcji i eksportowanie
  plików PNG przy użyciu Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Twórz wysokiej jakości kody kreskowe przy użyciu generatora kodów kreskowych
  w C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Jak używać generatora kodów kreskowych C# do kodów DataBar
url: /pl/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać generatora kodów kreskowych C# dla kodów DataBar

If you need a **c# barcode generator** that can produce DataBar stacked Omni‑Directional symbols, this guide gives you a complete, ready‑to‑run solution. You’ll see how to generate barcode images, control the X‑dimension, and change the aspect ratio without leaving the IDE.

Generating barcodes is a common requirement for inventory systems, shipping labels, and point‑of‑sale applications. By the end of this tutorial you can create PNG files with any aspect ratio you choose, and you’ll understand how to adapt the code for other barcode types.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolny edytor C#, którego preferujesz)  
* Odwołanie NuGet do **Aspose.BarCode** – biblioteki, która napędza klasę `BarcodeGenerator`  

You do not need a separate graphics library; Aspose.BarCode handles image encoding internally.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version of the library to your project file, making the `BarcodeGenerator` class available for use.

## Krok 2: Zdefiniuj folder wyjściowy

Choose a folder where the generated PNG files will be saved. Using an absolute or relative path works the same way, but a relative path keeps the project portable.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Creating the directory programmatically prevents runtime errors if the folder is missing.

## Krok 3: Utwórz instancję generatora kodów kreskowych C# z przykładowymi danymi

The `BarcodeGenerator` constructor requires two arguments: the barcode type and the data string. For a DataBar stacked Omni‑Directional symbol you use `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

The data string follows the GS1 Application Identifier format. The `EncodeTypes` enum contains over 150 barcode standards; you can switch to another type by changing the enum value.

## Krok 4: Ustaw wymiar X (rozmiar w pikselach) dla kodu kreskowego

The X‑dimension controls the width of the narrowest bar. A pixel value of 2 yields a crisp, high‑resolution image suitable for most screens.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Adjusting the X‑dimension is optional, but it gives you fine‑grained control over the visual density of the barcode.

## Krok 5: Wygeneruj kod kreskowy z współczynnikiem proporcji 15 i zapisz go jako PNG

The `AspectRatio` property belongs to the `DataBar` sub‑object. Changing this value stretches or compresses the barcode vertically while preserving the encoded data.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The `Save` method writes the barcode to the specified file path. The `BarCodeImageFormat.Png` enum ensures lossless compression.

![przykład wyjścia generatora kodów kreskowych c#](generated_barcode_example.png)

*Obraz: kod kreskowy wygenerowany z współczynnikiem proporcji 15.*

## Krok 6: Zmień współczynnik proporcji na 30 i wygeneruj drugi obraz

Reusing the same `BarcodeGenerator` instance avoids allocating a new object. Simply update the `AspectRatio` and call `Save` again.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Now you have two PNG files that differ only in vertical scaling. This technique is useful when you need the same data rendered for different label sizes.

## Typowe warianty i przypadki brzegowe

### Przełączanie na inny typ kodu kreskowego

If you need a QR code, Code 128, or PDF417, replace the enum value in the constructor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

All other configuration steps (X‑dimension, saving) remain identical.

### Obsługa nieobsługiwanych znaków

The `BarcodeGenerator` validates the input string against the selected symbology. Supplying an illegal character throws an `ArgumentException`. Wrap the creation in a try‑catch block to provide a friendly error message:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Eksport do innych formatów obrazu

Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument of `Save` accordingly:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Wyjście wysokiej rozdzielczości do druku

When printing on high‑DPI printers, increase the X‑dimension and optionally set the `Resolution` property:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

These settings produce larger files but maintain crisp edges on physical media.

## Oczekiwany wynik

Running the complete program creates the following files inside `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – kod DataBar o standardowej wysokości  
* `DatabarAspectRatio30.png` – wersja rozciągnięta w pionie  

Both images contain the same encoded GS1 data, and you can verify them with any barcode scanner app.

## Pełny kod źródłowy

Copy the code below into a new console project (`dotnet new console`) and run it. The program prints status messages to the console and writes the PNG files to disk.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Running the program produces console output similar to:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Zakończenie

You now have a **c# barcode generator** that can create DataBar stacked Omni‑Directional symbols, adjust the X‑dimension, and export PNG files with custom aspect ratios. The same pattern works for any other barcode symbology supported by Aspose.BarCode, making it easy to integrate barcode creation into inventory, shipping, or point‑of‑sale solutions.

If you want to explore further, try:

* Generowanie kodów QR lub symboli PDF417 (`how to generate barcode` dla aplikacji mobilnych)  
* Eksport do SVG dla skalowalnej grafiki internetowej  
* Osadzanie wygenerowanych obrazów bezpośrednio w fakturach PDF przy użyciu Aspose.PDF  

Eksperymentuj z różnymi wartościami `AspectRatio`, rozmiarami wymiaru X i formatami wyjściowymi, aby dopasować dokładnie

## Co powinieneś nauczyć się dalej?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak dostosować rozmiar kodu kreskowego – współczynnik proporcji Codablock F przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generować i dostosować wysokość kodu DataBar jednowymiarowego przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}