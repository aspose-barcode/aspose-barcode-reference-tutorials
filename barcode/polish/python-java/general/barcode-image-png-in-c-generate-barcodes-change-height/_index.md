---
category: general
date: 2026-08-15
description: Obraz kodu kreskowego PNG w C# – dowiedz się, jak generować kody pocztowe,
  tworzyć kod Planet oraz zmieniać wysokość kodu kreskowego przy użyciu prostego generatora.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: pl
lastmod: 2026-08-15
og_description: Samouczek Barcode image PNG w C# pokazuje, jak generować kody pocztowe,
  tworzyć kod Planet oraz zmieniać wysokość kodu kreskowego przy użyciu API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Obraz kodu kreskowego PNG w C# – generowanie i dostosowywanie kodów kreskowych
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Obraz kodu kreskowego PNG w C# – generowanie kodów kreskowych, zmiana wysokości
url: /pl/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obraz kodu kreskowego PNG w C# – generowanie kodów kreskowych, zmiana wysokości

Jeśli potrzebujesz **obrazu kodu kreskowego PNG** w C#, ten przewodnik poprowadzi Cię przez cały proces. Dowiesz się, jak generować kody pocztowe, stworzyć kod Planet oraz zmienić wysokość kodu kreskowego bez wychodzenia z IDE.

Generowanie niezawodnych plików PNG z kodami kreskowymi jest powszechnym wymogiem dla etykiet wysyłkowych, systemów inwentaryzacji i zautomatyzowanych rozwiązań pocztowych. Po zakończeniu tego tutorialu będziesz posiadać wielokrotnego użytku fragment kodu, który tworzy wysokiej jakości pliki PNG zarówno w formacie Planet, jak i RM4SCC, oraz zrozumiesz, jak dostosować wysokość pasków, aby spełnić specyfikacje pocztowe.

## Czego będziesz potrzebować

- .NET 6+ lub .NET Framework 4.7.2 (API BarcodeGenerator działa z dowolnym aktualnym środowiskiem .NET)  
- Odwołanie do pakietu NuGet **Aspose.BarCode for .NET** (lub dowolnej kompatybilnej biblioteki udostępniającej `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`)  
- Podstawowa znajomość składni C# oraz operacji I/O na plikach  

Nie są wymagane dodatkowe narzędzia; kod działa w Visual Studio, Rider lub przy użyciu interfejsu `dotnet` CLI.

## Obraz kodu kreskowego PNG – podstawowe generowanie

Pierwszym krokiem jest utworzenie **obrazu kodu kreskowego PNG** o domyślnych wymiarach. To tworzy bazowy plik, który później możesz dostosować.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Dlaczego to działa:**  
- `EncodeTypes.Planet` instruuje generator, aby użył symboliki Planet, wymaganą przez wiele usług pocztowych.  
- `XDimension.Pixels` kontroluje szerokość najmniejszego paska; wartość 4 px zapewnia czytelny kod przy typowych rozmiarach etykiet.  
- Metoda `Save` zapisuje **obraz kodu kreskowego PNG** na dysku, zachowując wszystkie informacje wektorowe jako piksele rastrowe.

## Zmiana wysokości kodu kreskowego – dostosowanie wagi wizualnej

Wytyczne pocztowe często wymagają określonej wysokości pasków. Poniższy fragment pokazuje, jak ustawić własną wysokość 100 pikseli dla tego samego kodu Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Dlaczego zmieniamy wysokość:**  
Wyższy pasek zwiększa niezawodność skanowania na drukarkach o niskiej rozdzielczości, natomiast niższy pasek oszczędza miejsce na etykiecie. Właściwość `BarHeight.Pixels` pozwala precyzyjnie dostroić ten parametr bez wpływu na wymiar X.

## Generowanie kodu pocztowego – przykład RM4SCC

Format RM4SCC to kolejny popularny kod pocztowy używany w Wielkiej Brytanii. Kroki generacji odzwierciedlają przykład Planet, wzmacniając wzorzec **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Zmiana wysokości kodu kreskowego – wariant RM4SCC

Podobnie jak w przypadku kodu Planet, możesz dostosować wysokość pasków RM4SCC. Poniższy kod ustawia wysokość na 100 px, tworząc drugi **obraz kodu kreskowego PNG** dla tego samego ciągu danych.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Pełny, gotowy do uruchomienia przykład

Połączenie wszystkich kroków daje pojedynczy, samodzielny program, który tworzy cztery pliki PNG:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}