---
category: general
date: 2026-08-22
description: Samouczek generatora kodów kreskowych w C# pokazuje, jak generować pliki
  PNG z kodami kreskowymi, tworzyć kody DataBar oraz regulować wysokość kodu kreskowego
  w kilku prostych krokach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: pl
lastmod: 2026-08-22
og_description: Poradnik generatora kodów kreskowych w C# prowadzi Cię krok po kroku,
  jak generować PNG kodów kreskowych, tworzyć kody DataBar oraz efektywnie regulować
  wysokość kodu.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: generator kodów kreskowych C# – twórz kody DataBar i dostosuj wysokość
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak używać generatora kodów kreskowych w C# do tworzenia kodów DataBar Omni‑directional
url: /pl/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar Omni‑directional

If you need a **barcode generator C#** that can produce high‑quality PNG images, this guide has you covered. You’ll learn how to generate barcode PNG files, create a DataBar Omni‑directional barcode, and adjust the barcode height without leaving your IDE.

Generating barcodes programmatically removes the manual step of using a graphic editor. By the end of this tutorial you’ll have two PNG files—one with a 30‑pixel bar height and another with a 60‑pixel bar height—ready for inclusion in invoices, labels, or inventory systems.

**Wymagania wstępne**

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Odwołanie do pakietu NuGet `Aspose.BarCode` (lub dowolnej biblioteki udostępniającej podobne API)
- Podstawowa znajomość C# oraz Visual Studio lub wybranego IDE

---

## Krok 1: Skonfiguruj projekt generatora kodów kreskowych C# 

Creating a **barcode generator C#** instance is the first thing you do. The constructor takes two arguments: the barcode type (`EncodeTypes.DatabarOmniDirectional`) and the data payload. In this example the payload follows the GS1 Application Identifier format for a 14‑digit GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Dlaczego to ważne:** The `EncodeTypes.DatabarOmniDirectional` enum tells the library to render a DataBar that can be read from any direction, which is ideal for small retail labels.

---

## Krok 2: Zdefiniuj wymiar modułu (X‑dimension)

The X‑dimension controls the width of a single barcode module. Setting it to 2 pixels gives a crisp, readable image while keeping file size low.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Wskazówka:** If you need a tighter barcode for limited space, lower the value to 1 pixel, but test readability with a scanner.

---

## Krok 3: Wygeneruj pierwszy PNG z wysokością paska 30 pixeli

Bar height determines how tall the bars appear. A 30‑pixel height is a common default for standard labels.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

The file `DatabarBarHeight30Pixels.png` now contains a **generate barcode PNG** that can be used directly in web pages or printed on demand.

---

## Krok 4: Dostosuj wysokość kodu kreskowego do 60 pixels i zapisz drugi PNG

Changing the bar height is as simple as assigning a new value to the same property. This demonstrates the **adjust barcode height** capability of the generator.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Now you have `DatabarBarHeight60Pixels.png`, which is ideal for larger packaging where the barcode must be scanned from a distance.

**Oczekiwany wynik**

- `DatabarBarHeight30Pixels.png` – kompaktowy kod DataBar Omni‑directional, wysokości 30 px.
- `DatabarBarHeight60Pixels.png` – ten sam kod, podwojony w wysokości dla lepszej widoczności.

Both images are PNG files, preserving lossless quality and supporting transparency if needed.

---

## Jak generować pliki PNG z kodami kreskowymi w różnych formatach

While this tutorial focuses on PNG, the `Save` method accepts other formats such as `Jpeg`, `Bmp`, and `Svg`. To **how to generate barcode** files in another format, simply replace `BarCodeImageFormat.Png` with the desired enum value:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Choosing SVG is handy when you need a vector image that scales without pixelation.

---

## Częste pułapki przy **create DataBar barcode** obrazach

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Kod kreskowy jest rozmyty | X‑dimension zbyt niska dla docelowej rozdzielczości | Increase `XDimension.Pixels` to 3 or 4 |
| Skaner nie może odczytać kodu | Bar height too short for the scanner’s optics | Use a minimum of 30 pixels or follow the scanner’s specifications |
| Ciąg danych odrzucony | Incorrect GS1 formatting | Ensure the string starts with the proper Application Identifier, e.g., `(01)` for GTIN‑14 |

Addressing these points early saves time when integrating barcodes into production pipelines.

---

## Zaawansowana wskazówka: Ponowne użycie tego samego generatora dla wielu kodów kreskowych

If you need to **generate barcode PNG** files for a batch of products, reuse the same `BarcodeGenerator` instance and only update the `CodeText` property:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

This pattern minimizes object creation overhead and keeps your code concise.

---

## Podsumowanie

You now have a complete **barcode generator C#** workflow that **creates DataBar barcodes**, **generates barcode PNG** files, and lets you **adjust barcode height** with a single property change. The example covers everything from project setup to handling edge cases, so you can integrate barcode creation into any .NET application with confidence.

**Kolejne kroki**

- Zbadaj inne symbologie kodów kreskowych (`EncodeTypes.QR`, `EncodeTypes.Code128`), aby rozszerzyć swoje rozwiązanie.
- Połącz generator z ASP.NET Core, aby serwować kody kreskowe w locie poprzez punkt końcowy API.
- Eksperymentuj z opcjami kolorów (`generator.Parameters.Barcode.ForeColor`) w celach brandingowych.

Miłego kodowania i niech Twoje skany zawsze będą szybkie!

## Co powinieneś nauczyć się dalej?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Jak generować i dostosowywać wysokość kodu kreskowego dla jednowymiarowego Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generowanie jednowymiarowych kodów Databar 2D przy użyciu Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}