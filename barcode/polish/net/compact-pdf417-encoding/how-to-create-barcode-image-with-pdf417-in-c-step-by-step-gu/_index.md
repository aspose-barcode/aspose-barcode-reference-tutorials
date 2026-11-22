---
category: general
date: 2026-11-20
description: Utwórz obraz kodu kreskowego w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak wygenerować kod PDF417 z niestandardowym układem i zapisać go jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: pl
lastmod: 2026-11-20
og_description: Utwórz obraz kodu kreskowego w C# przy użyciu Aspose.BarCode. Ten
  przewodnik pokazuje, jak wygenerować kod PDF417, dostosować układ i wyeksportować
  do formatu PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Utwórz obraz kodu kreskowego PDF417 w C# – kompletny poradnik
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Jak stworzyć obraz kodu kreskowego PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie **jak wygenerować kod kreskowy PDF417** z niestandardowym układem i zapisać go jako plik PNG. Zobaczysz kompletny, działający kod, zrozumiesz, dlaczego każde ustawienie ma znaczenie, oraz poznasz typowe pułapki, aby Twój kod kreskowy działał niezawodnie w produkcji.

W tym samouczku:

* Zainicjalizować generator Aspose.BarCode dla PDF417.
* Skonfigurować liczbę kolumn i wierszy, aby kontrolować kształt kodu kreskowego.
* Wyeksportować wynik jako wysokiej jakości obraz PNG.
* Poznać opcjonalne ustawienia korekcji błędów i długości danych.

Jedynym wymogiem wstępnym jest aktualny .NET SDK (.NET 6 lub nowszy) oraz licencja lub darmowa wersja próbna **Aspose.BarCode for .NET**.

---

## Wymagania wstępne i konfiguracja

Before you start, make sure you have:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6 SDK or newer | Zapewnia środowisko uruchomieniowe dla aplikacji konsolowej C#. |
| Visual Studio 2022 (or VS Code) | Dostarcza IDE z IntelliSense dla API Aspose. |
| Aspose.BarCode for .NET NuGet package | Udostępnia `BarcodeGenerator`, `EncodeTypes` oraz pomocniki eksportu obrazu. |
| Write permission to the output folder | Generator zapisuje plik PNG na dysku. |

You can add the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

---

## Krok 1: Utwórz nowy projekt konsolowy

First, scaffold a simple console application that will host the barcode‑generation logic.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Dlaczego ten kod działa

* **`BarcodeGenerator`** jest punktem wejścia dla wszystkich typów kodów kreskowych. Przekazując `EncodeTypes.Pdf417` informujesz bibliotekę, aby wygenerowała symbol PDF417.
* **Kolumny i wiersze** są podstawowymi dźwigniami układu. Mniej kolumn daje wyższy kod kreskowy; więcej kolumn sprawia, że jest szerszy. Dostosuj te wartości do przestrzeni, w której obraz będzie wyświetlany (np. drukarka etykiet vs. strona internetowa).
* **Korekcja błędów** zwiększa niezawodność skanowania, gdy kod może być rozmazany lub wydrukowany na niskiej jakości nośniku. Domyślny poziom to 0; podniesienie go nieco (2–4) jest dobrym kompromisem między rozmiarem a wytrzymałością.
* **`Save`** zapisuje obraz na dysku w formacie PNG, co zachowuje ostre krawędzie i działa we wszystkich przeglądarkach oraz na urządzeniach mobilnych.

When you run the program (`dotnet run`), it creates `CustomPdf417.png` in the project folder. The PNG looks like this:

![Wygenerowany obraz kodu kreskowego PDF417](https://example.com/images/pdf417-sample.png "Zrzut ekranu wygenerowanego obrazu kodu kreskowego stworzonego przy użyciu PDF417 w C#")

*Alt text:* **utworzyć obraz kodu kreskowego** – kod kreskowy PDF417 wygenerowany w C# i zapisany jako PNG.

---

## Krok 2: Dostosuj kod kreskowy do scenariuszy rzeczywistych

### Dostosowywanie długości danych

PDF417 can encode up to 1,850 characters. If you need to encode longer strings, consider splitting the data across multiple barcodes or using the **compact mode**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Compact mode reduces the number of rows but may increase the visual density, so test with your scanner.

### Kontrola rozmiaru obrazu

The default image size is calculated from the module size (the smallest square in the barcode). You can explicitly set the DPI or scale the image after generation:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Or, after saving, resize with System.Drawing if you need a thumbnail.

### Obsługa znaków specjalnych

PDF417 supports the full ASCII set. If your data contains Unicode characters, ensure you encode the string as UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Krok 3: Typowe pułapki i jak ich unikać

| Pułapka | Objaw | Rozwiązanie |
|---------|-------|-------------|
| Zbyt wiele kolumn dla danych | Kod kreskowy jest przycięty lub wyrzuca wyjątek. | Zredukuj `Columns` lub pozwól bibliotece automatycznie dopasować rozmiar, pomijając to ustawienie. |
| Niska korekcja błędów przy drukarce o słabej jakości | Skanery przerywają odczyt kodu kreskowego. | Zwiększ `ErrorCorrectionLevel` przynajmniej do 2. |
| Zapisywanie do katalogu tylko do odczytu | `UnauthorizedAccessException` w czasie wykonywania. | Użyj katalogu zapisywalnego, np. `Environment.CurrentDirectory` lub `Path.GetTempPath()`. |
| Używanie przestarzałej wersji Aspose.BarCode | Brak właściwości takich jak `CompactMode`. | Zaktualizuj pakiet NuGet do najnowszej stabilnej wersji. |

---

## Krok 4: Zweryfikuj wynik

To confirm that the barcode was generated correctly, you can:

1. Otwórz `CustomPdf417.png` w dowolnym przeglądarce obrazów – kod kreskowy powinien być wyraźny, z czarnymi modułami na białym tle.
2. Użyj darmowej aplikacji skanującej PDF417 (dostępnej na iOS i Android), aby zeskanować obraz. Aplikacja powinna wyświetlić **„Sample data for PDF417 barcode”**.
3. (Opcjonalnie) Załaduj obraz w teście jednostkowym przy użyciu `System.Drawing.Bitmap` i sprawdź, że piksel w `(0,0)` jest czarny, potwierdzając, że obraz nie jest pusty.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

If the assertion passes, you’ve successfully **utworzyć obraz kodu kreskowego** and **wygenerować kod kreskowy PDF417** programmatically.

---

## Zakończenie

You now know how to **create barcode image** in C# by **generating PDF417 barcode** with a custom layout, adjusting error correction, and exporting to PNG. The complete example demonstrates every required step—from initializing `BarcodeGenerator` to saving the final image—so you can copy, paste, and run it in your own project.

Next, you might explore:

* **Osadzenie PNG w API webowym**, aby klienci mogli żądać kodów kreskowych na żądanie (`generate pdf417` jako usługa).
* **Generowanie wsadowe** dla dużych zestawów danych — iteruj listę ciągów i przechowuj każdy PNG w bazie danych.
* **Alternatywne formaty wyjściowe** (SVG, JPEG) poprzez zmianę `BarCodeImageFormat`.

Feel free to experiment with column/row ratios, error‑correction levels, and image resolution to meet the exact requirements of your scanner hardware or UI design. Happy coding!

## Co powinieneś nauczyć się dalej?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Jak utworzyć obraz kodu kreskowego PDF417 w C# – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Jak utworzyć obraz kodu kreskowego PDF417 w C# z opcjami Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Jak utworzyć mikro kod PDF417 i wygenerować PNG w C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}