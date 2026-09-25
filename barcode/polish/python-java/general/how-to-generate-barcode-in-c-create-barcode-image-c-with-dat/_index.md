---
category: general
date: 2026-08-22
description: Jak generować kod kreskowy w C# przy użyciu Aspose.BarCode. Dowiedz się,
  jak krok po kroku tworzyć obraz kodu kreskowego w C#, wyłączyć komponent 2‑D i zapisywać
  pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: pl
lastmod: 2026-08-22
og_description: Jak generować kod kreskowy w C# przy użyciu Aspose.BarCode. Ten samouczek
  pokazuje, jak stworzyć obraz kodu kreskowego w C# wykorzystując DataBar Expanded,
  przełączyć komponent 2‑D i zapisać pliki PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Jak generować kod kreskowy w C# – kompletny przewodnik tworzenia obrazu
  kodu kreskowego w C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Jak generować kod kreskowy w C# – tworzenie obrazu kodu kreskowego w C# z użyciem
  DataBar Expanded
url: /pl/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy w C# – tworzenie obrazu kodu kreskowego c# z DataBar Expanded

Generowanie kodu kreskowego w C# jest częstym wymaganiem, gdy trzeba osadzić dane odczytywane maszynowo w aplikacjach. Ten przewodnik pokazuje, jak stworzyć obraz kodu kreskowego c# przy użyciu biblioteki Aspose.BarCode, wyłączyć komponent 2‑D composite i zapisać wynik jako pliki PNG.

Zobaczysz kompletny, uruchamialny program, wyjaśnienie każdej opcji konfiguracyjnej oraz wskazówki dotyczące dostosowywania wyjścia. Nie jest wymagana żadna zewnętrzna dokumentacja – wystarczy poniższy kod i środowisko programistyczne .NET.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)  
* Aspose.BarCode for .NET NuGet package (`Aspose.BarCode`)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

The library provides the `BarcodeGenerator` class used throughout this tutorial.

## Step 1: Set up the project and import namespaces

Create a new console application and import the required namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

The `Aspose.BarCode.Generation` namespace contains all classes needed to configure and render barcodes.

## Step 2: Initialize the DataBar Expanded barcode generator

The first functional line creates a `BarcodeGenerator` for the **DataBar Expanded** symbology and supplies the raw data string. The data string follows the GS1 Application Identifier format `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Creating the generator allocates the internal bitmap canvas, so you can adjust size and appearance before rendering.

## Step 3: Define the module width (X‑dimension)

The X‑dimension controls the width of the smallest barcode element. Setting it in pixels gives you precise control over the final image size.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A value of `2` pixels works well for screen display; increase it for higher‑resolution prints.

## Step 4: Disable the 2‑D composite component

DataBar Expanded can optionally include a 2‑D component that carries additional information. To generate a barcode **without** this component, set the flag to `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Disabling the component reduces the visual complexity and produces a smaller PNG file.

## Step 5: Save the barcode image without the 2‑D component

Choose an output directory and write the image to disk. The `BarCodeImageFormat.Png` enum ensures a lossless PNG file.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

After this call, `Databar2DComponentDisabled.png` contains a clean DataBar Expanded barcode.

## Step 6: Enable the 2‑D composite component

If you need the extra data layer, re‑enable the flag. The same generator instance can be reused, which avoids creating a second object.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Step 7: Save the barcode image with the 2‑D component enabled

Render the second image using the same settings, except for the 2‑D flag.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Now `Databar2DComponentEnabled.png` shows the barcode with the additional 2‑D pattern.

## Full source code

Copy the entire snippet below into `Program.cs` and run the project. The program creates both PNG files in the folder you specify.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Expected output

Running the program prints:

```
Barcode images generated successfully.
```

and creates two files:

* `Databar2DComponentDisabled.png` – kod kreskowy bez komponentu 2‑D  
* `Databar2DComponentEnabled.png` – kod kreskowy z komponentem 2‑D  

Open the PNGs in any image viewer to verify the visual difference.

## Common variations and edge cases

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Różna symbologia** | Zastąp `EncodeTypes.DatabarExpanded` inną wartością, np. `EncodeTypes.Code128`. |
| **Wyższa rozdzielczość** | Zwiększ `XDimension.Pixels` do 4 lub 5, lub ustaw `Resolution` w `barcodeGenerator.Parameters.Image`. |
| **Inne formaty obrazu** | Użyj `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` lub `BarCodeImageFormat.Svg`. |
| **Uruchamianie w aplikacji webowej** | Strumieniuj bajty obrazu bezpośrednio w odpowiedzi HTTP zamiast zapisywać na dysku. |
| **Zarządzanie pamięcią** | Umieść generator w bloku `using`, jeśli celujesz w .NET Framework, aby zapewnić zwolnienie niezarządzanych zasobów. |

## Pro tips

* **Ponowne użycie generatora** – Zmiana tylko flagi 2‑D unika ponownego tworzenia obiektu, co oszczędza cykle CPU.  
* **Walidacja danych** – Dane GS1 muszą spełniać dokładne reguły długości i sumy kontrolnej; nieprawidłowe dane powodują wyrzucenie `ArgumentException`.  
* **Przetwarzanie wsadowe** – Iteruj po kolekcji ciągów danych, przełączaj flagę 2‑D w razie potrzeby i zapisuj każdy obraz pod unikalną nazwą pliku.  

## Conclusion

You now know how to generate barcode in C# and create barcode image c# with full control over the 2‑D composite component. The example demonstrates initializing the generator, configuring the X‑dimension, toggling the component, and saving PNG files. From here you can explore other symbologies, embed the images in PDFs, or integrate barcode generation into ASP.NET Core services.

--- 

*Next steps*: try generating QR codes, experiment with different image resolutions, or embed the generated PNGs into a PDF using Aspose.PDF. These extensions build on the same `BarcodeGenerator` API and keep your workflow consistent.

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generować i dostosowywać wysokość kodu kreskowego dla jednowymiarowego Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}