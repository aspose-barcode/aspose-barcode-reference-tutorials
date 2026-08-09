---
category: general
date: 2026-08-09
description: Generuj kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak generować kod kreskowy, obsługiwać znaki specjalne i szybko tworzyć kod
  PDF417 w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: pl
lastmod: 2026-08-09
og_description: Generuj kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Ten
  samouczek pokazuje, jak generować kod kreskowy, obsługiwać znaki specjalne oraz
  tworzyć kod PDF417 w C# z pełnym kodem.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Generowanie kodu kreskowego z tekstu w C# – szybki przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Generowanie kodu kreskowego z tekstu w C# – kompletny przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wygeneruj kod kreskowy z tekstu w C# – kompletny przewodnik krok po kroku

Jeśli potrzebujesz **generate barcode from text** w aplikacji .NET, ten przewodnik poprowadzi Cię przez cały proces. Zobaczysz, jak generować kod kreskowy, obsługiwać znaki specjalne i stworzyć implementację kodu kreskowego PDF417 w C#, która działa od razu.

Generowanie kodu kreskowego z tekstu jest powszechnym wymaganiem w systemach inwentaryzacji, platformach biletowych i przepływach dokumentów. Po zakończeniu tego samouczka będziesz mieć działającą aplikację konsolową C#, która tworzy obraz PNG MicroPdf417 przy użyciu Aspose.BarCode. Nie są wymagane żadne zewnętrzne usługi, a kod obsługuje znaki Unicode, takie jak „Å”, „©” i „é”.

## Prerequisites

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Core 3.1 i .NET Framework 4.7+)
- Visual Studio 2022 (lub dowolne IDE obsługujące C#)
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Podstawowa znajomość składni C#

## Wygeneruj kod kreskowy z tekstu – konfiguracja generatora

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator`, która wie, jaki **barcode encode type** jest potrzebny. W tym samouczku używamy `EncodeTypes.MicroPdf417`, który jest kompaktową odmianą PDF417 odpowiednią dla krótkich ciągów danych.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Why this works:**  
- `EncodeTypes.MicroPdf417` informuje bibliotekę, aby użyła rodziny PDF417, spełniając wymaganie **create pdf417 barcode c#**.  
- Konstruktor przyjmuje surowy tekst, co jest istotą **generate barcode from text**.  
- Obsługa Unicode jest wbudowana, więc znaki takie jak „Å” i „©” są kodowane poprawnie, co rozwiązuje problem **barcode with special characters**.

## Jak generować kod kreskowy ze znakami specjalnymi

Gdy Twoje dane zawierają symbole nie‑ASCII, musisz zapewnić, że generator używa kodowania UTF‑8. Aspose.BarCode automatycznie wykrywa Unicode, ale możesz jawnie ustawić kodowanie tekstu, jeśli napotkasz problemy:

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Dodanie tej linii przed `ConfigureGenerator` zapewnia, że **barcode with special characters** renderuje się poprawnie na każdej platformie.

### Praktyczna wskazówka
Jeśli wynik wygląda na zniekształcony, sprawdź, czy czcionka używana przez renderer kodu kreskowego obsługuje wymagane glify. Możesz osadzić własną czcionkę TrueType za pomocą:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Typy kodowania kodów kreskowych, które możesz wybrać

Aspose.BarCode obsługuje dziesiątki **barcode encode types**, z których każdy jest odpowiedni dla różnych zastosowań:

| Typ kodowania                | Typowe zastosowanie                     |
|------------------------------|------------------------------------------|
| `EncodeTypes.Code128`        | Etykiety wysyłkowe, inwentaryzacja      |
| `EncodeTypes.QR`             | Płatności mobilne, adresy URL            |
| `EncodeTypes.Pdf417`         | Prawo jazdy, karty pokładowe              |
| `EncodeTypes.MicroPdf417`    | Małe ładunki danych, ograniczona przestrzeń |
| `EncodeTypes.DataMatrix`     | Małe przedmioty, wysoka gęstość danych   |

Zmiana typu kodowania jest tak prosta, jak zamiana wartości wyliczenia w konstruktorze:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Ta elastyczność pozwala odpowiadać na pytania dotyczące **barcode encode types** bez opuszczania IDE.

## Utwórz kod kreskowy PDF417 w C# – końcowe kroki i weryfikacja

Po skonfigurowaniu generatora, ostatnia część **create pdf417 barcode c#** to zapisanie obrazu i potwierdzenie wyniku.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Uruchom program (`dotnet run`) i powinieneś zobaczyć komunikat w konsoli podobny do:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Otwórz plik PNG; zobaczysz wyraźny kod MicroPdf417, który koduje ciąg „Åspóse.Barcóde©”. Skanowanie go za pomocą mobilnego skanera kodów kreskowych (np. ZXing) zwraca oryginalny tekst, co dowodzi, że **generate barcode from text** działa nawet ze znakami specjalnymi.

### Przypadek brzegowy: bardzo długi tekst

MicroPdf417 ma maksymalną pojemność danych wynoszącą 1 KB. Jeśli Twój wejściowy tekst przekracza ten limit, biblioteka zgłasza `ArgumentException`. Aby obsłużyć to elegancko:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

Dla większych ładunków danych przełącz się na pełny `EncodeTypes.Pdf417` lub `EncodeTypes.DataMatrix`.

## Typowe pułapki i jak ich unikać

| Problem                               | Przyczyna                                   | Rozwiązanie |
|---------------------------------------|---------------------------------------------|-------------|
| Kod kreskowy jest rozmyty             | XDimension jest zbyt niska (np. 1 px)       | Zwiększ `XDimension.Pixels` do 2‑3 px |
| Znaki Unicode zamieniają się na `?`   | Domyślne kodowanie tekstu to ASCII          | Ustaw `TextEncoding = Encoding.UTF8` |
| Plik obrazu nie został utworzony      | Katalog wyjściowy nie istnieje               | Użyj `Directory.CreateDirectory` przed `Save` |
| Skaner nie może odczytać kodu kreskowego | Zbyt wiele kolumn dla krótkich danych        | Zmniejsz `Pdf417.Columns` (np. 3‑4) |

## Pełny kod źródłowy (gotowy do skopiowania)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Expected output:** plik o nazwie `MicroPdf417.png` znajdujący się w folderze `output`, zawierający wyraźny kod MicroPdf417, który koduje oryginalny ciąg ze znakami specjalnymi.

## Zakończenie

Teraz wiesz, jak **generate barcode from text** w C# przy użyciu Aspose.BarCode, jak obsługiwać **barcode with special characters**, oraz jak **create pdf417 barcode c#** z pełną kontrolą nad opcjami kodowania. Dostosowując **barcode encode types**, możesz generować kody QR, Code128, DataMatrix lub dowolny inny obsługiwany format.

Następnie, zapoznaj się z poniższymi tematami, aby pogłębić swoją wiedzę o kodach kreskowych:

- **How to generate barcode** w partiach dla tysięcy rekordów (użyj `Parallel.ForEach` dla zwiększenia szybkości)
- Dostosowywanie kolorów i dodawanie logo wewnątrz kodu kreskowego
- Integracja generowania kodów kreskowych z API ASP.NET Core w celu dostarczania obrazów w locie
- Używanie innych bibliotek, takich jak ZXing.Net lub IronBarcode, jako otwarto‑źródłowych alternatyw

Śmiało eksperymentuj z różnymi wymiarami, ustawieniami kolumn i typami kodowania. Powodzenia w kodowaniu i niech Twoje aplikacje skanują bezbłędnie!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak stworzyć kod kreskowy – kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak wygenerować kod kreskowy – konfiguracja Code 39 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak wygenerować kod kreskowy – typy kodów jednowymiarowych](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}