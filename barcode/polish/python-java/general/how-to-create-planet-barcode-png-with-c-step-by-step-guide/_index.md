---
category: general
date: 2026-09-07
description: Szybko utwórz obraz PNG kodu kreskowego planet w C#. Dowiedz się, jak
  generować obrazy kodu kreskowego planet przy użyciu Aspose.BarCode z wypełnionymi
  i pustymi paskami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: pl
lastmod: 2026-09-07
og_description: Twórz szybkie obrazy PNG kodu kreskowego planet w C#. Skorzystaj z
  tego przewodnika, aby dowiedzieć się, jak generować obrazy kodu kreskowego planet
  z wypełnionymi i pustymi paskami przy użyciu Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Tworzenie kodu kreskowego planety PNG w C# – kompletny samouczek programistyczny
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak stworzyć kod kreskowy planety w formacie PNG w C# – przewodnik krok po
  kroku
url: /pl/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć plik PNG z kodem kreskowym Planet w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć pliki PNG z kodem kreskowym Planet** w C#, ten przewodnik pokaże Ci dokładne kroki. Niezależnie od tego, czy tworzysz integrację z usługą pocztową, czy pulpit logistyczny, dowiesz się **jak generować obrazy kodu kreskowego Planet** zarówno z wypełnionymi, jak i pustymi paskami, używając biblioteki Aspose.BarCode.

W tym tutorialu:

* Skonfigurujesz folder wyjściowy dla swoich obrazów.  
* Skonfigurujesz `BarcodeGenerator` dla symbologii Planet.  
* Wygenerujesz PNG w domyślnym stylu wypełnionych pasków.  
* Wygenerujesz PNG z pustymi paskami dla kontrastu wizualnego.  

Żadne zewnętrzne usługi nie są wymagane — wszystko działa lokalnie na .NET 6 lub nowszym.

## Prerequisites

Zanim rozpoczniesz, upewnij się, że masz:

| Wymaganie | Dlaczego jest ważne |
|-------------|----------------|
| .NET 6 SDK (or newer) | Zapewnia środowisko uruchomieniowe dla aplikacji konsolowej C#. |
| Visual Studio 2022 or VS Code | Dowolne IDE, które może kompilować projekty C#. |
| Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`) | Dostarcza klasę `BarcodeGenerator` używaną do renderowania kodów kreskowych Planet. |
| Write permission to a folder on disk | Pliki PNG zostaną zapisane w tej lokalizacji. |

Zainstaluj pakiet NuGet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a new console project

Otwórz terminal i uruchom:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Tworzy minimalną aplikację konsolową C# o nazwie **PlanetBarcodeDemo**.

## Step 2: Define the output directory

Pierwszy fragment kodu określa, gdzie będą przechowywane wygenerowane pliki PNG. Działa zarówno ścieżka bezwzględna, jak i względna; wystarczy upewnić się, że folder istnieje lub pozwolić programowi go utworzyć.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Dlaczego ten krok?* Oddzielenie wyjścia od kodu źródłowego utrzymuje projekt w porządku i zapobiega przypadkowym nadpisaniom.

## Step 3: Generate a filled‑bars Planet barcode

Kod kreskowy Planet składa się z koncentrycznych kół (domyślnie wypełnionych). Konfigurujemy wymiar X (szerokość piksela każdego paska), a następnie zapisujemy obraz jako PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Wyjaśnienie**

* `EncodeTypes.Planet` informuje Aspose, aby użył symbologii Planet, która jest powszechna w usługach pocztowych.  
* `XDimension.Pixels = 4` daje wyraźny, drukowalny rozmiar bez ręcznego skalowania.  
* Metoda `Save` zapisuje plik PNG; możesz również wybrać JPEG lub BMP, zmieniając `BarCodeImageFormat`.

## Step 4: Generate an empty‑bars Planet barcode

Czasami potrzebny jest wizualny efekt z pustymi (przezroczystymi) paskami — na przykład, gdy kod kreskowy jest nakładany na kolorowe tło. Ustawienie `FilledBars` na `false` tworzy taki styl.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Wyjaśnienie**

* `FilledBars = false` wyłącza wypełnione koła, pozostawiając jedynie kontury.  
* Wszystkie pozostałe ustawienia (X‑dimension, ciąg danych) pozostają identyczne, co gwarantuje, że oba obrazy reprezentują te same dane.

## Step 5: Run the program and verify the output

Skompiluj i uruchom:

```bash
dotnet run
```

Powinieneś zobaczyć komunikaty w konsoli potwierdzające zapisane pliki, a folder `Barcodes` będzie zawierał:

* `PostalPlanetFilledBars.png` – klasyczny kod kreskowy Planet z wypełnionymi paskami.  
* `PostalPlanetEmptyBars.png` – te same dane renderowane z pustymi paskami.

Otwórz pliki PNG w dowolnym przeglądarce obrazów. Oba obrazy kodują ciąg liczbowy **123456** i mogą być odczytane przez standardowe czytniki kodów kreskowych poczty.

## Common questions and edge‑case handling

### What if I need a different data format?

Kody kreskowe Planet akceptują ciągi liczbowe do 12 cyfr. Jeśli przekażesz wartość nienumeryczną, Aspose zgłosi `ArgumentException`. Zweryfikuj dane wejściowe przed utworzeniem generatora:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### How do I change the image size without altering bar thickness?

Użyj właściwości `Resolution` lub przeskaluj uzyskany bitmap po zapisaniu:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Can I generate other image formats?

Tak. Zastąp `BarCodeImageFormat.Png` przez `BarCodeImageFormat.Jpeg`, `Bmp` lub `Gif`. API obsługuje wszystkie popularne formaty rastrowe.

### What about color customization?

Ustaw `BarColor` i `BackColor` w parametrach `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Te opcje działają zarówno dla wersji wypełnionych, jak i pustych pasków.

## Pro tips for production use

* **Cache'uj generator** gdy musisz renderować wiele kodów kreskowych z tymi samymi ustawieniami — wielokrotne inicjalizowanie obiektu zwiększa obciążenie.  
* **Dispose** obiekty `BarcodeGenerator`, jeśli tworzysz ich wiele w pętli (implementują `IDisposable`).  
* **Sprawdź folder wyjściowy** wcześnie, aby uniknąć wyjątków w czasie wykonywania w katalogach chronionych przed zapisem.  

## Conclusion

Teraz wiesz, jak **utworzyć pliki PNG z kodem kreskowym Planet** w C# i rozumiesz **jak generować obrazy kodu kreskowego Planet** zarówno w stylu wypełnionych, jak i pustych pasków. Pełny, działający przykład pokazuje, jak ustawić folder wyjściowy, skonfigurować `BarcodeGenerator` i zapisać wyniki jako pliki PNG.

Następnie możesz zbadać:

* Dodawanie **czytelnego dla człowieka tekstu** pod kodem kreskowym (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrację wygenerowanych PNG w **fakturę PDF** przy użyciu Aspose.PDF.  
* Przejście na inne symbologie pocztowe, takie jak **IMB** lub **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Śmiało eksperymentuj z grubością pasków, kolorami i rozdzielczością obrazu, aby dopasować je do konkretnych wymagań aplikacji. Szczęśliwego kodowania!

## What Should You Learn Next?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obraz kodu kreskowego Planet w C# – Jak generować kod pocztowy](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Utwórz kod kreskowy Planet w C# – Pełny przewodnik krok po kroku](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generuj kod kreskowy PNG przy użyciu Aspose.BarCode dla .NET: Jednowymiarowe wypełnione paski](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}