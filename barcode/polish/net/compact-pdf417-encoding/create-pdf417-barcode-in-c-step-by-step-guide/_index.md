---
category: general
date: 2026-08-03
description: Szybko utwórz kod kreskowy PDF417 w C#. Dowiedz się, jak generować kod
  kreskowy PDF417 i jak zapisać obraz kodu jako PNG przy użyciu Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: pl
lastmod: 2026-08-03
og_description: Utwórz kod kreskowy PDF417 w C# z Aspose.Barcode. Skorzystaj z tego
  przewodnika, aby wygenerować kod PDF417 i dowiedzieć się, jak efektywnie zapisać
  obraz kodu kreskowego.
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: Stwórz kod kreskowy PDF417 w C# – kompletny poradnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Tworzenie kodu kreskowego PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie kodu kreskowego PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak wygenerować kod PDF417 i jak zapisać jego obraz. Otrzymasz plik PNG, który można wykorzystać w raportach, biletach lub aplikacjach mobilnych do skanowania.

Tutorial obejmuje wszystko, od konfiguracji projektu po ostateczny plik PNG. Nie jest wymagana żadna zewnętrzna dokumentacja; po prostu postępuj zgodnie z krokami i uruchom kod.

## Czego będziesz potrzebować

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
* Visual Studio 2022 lub dowolne IDE obsługujące C#
* Dostęp do Internetu w celu zainstalowania pakietu NuGet **Aspose.Barcode for .NET**

Te wymagania wstępne zapewniają, że kod skompiluje się bez dodatkowej konfiguracji.

## Tworzenie kodu kreskowego PDF417 – konfiguracja projektu

1. Otwórz wiersz poleceń i utwórz nowy projekt konsolowy:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Dodaj bibliotekę Aspose.Barcode:

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. Otwórz wygenerowany plik `Program.cs`. Dyrektywy `using` na początku dają dostęp do klas kodów kreskowych:

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

Projekt jest już gotowy do **utworzenia kodu kreskowego PDF417**.

## Jak wygenerować kod kreskowy PDF417 przy użyciu Aspose.Barcode

Podstawą tworzenia kodu kreskowego jest klasa `BarcodeGenerator`. Określasz symbologię (`EncodeTypes.Pdf417`) oraz dane, które chcesz zakodować.

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### Dlaczego to ważne

* **EncodeTypes.Pdf417** informuje bibliotekę, aby użyła standardu PDF417, który obsługuje duże ładunki danych i korekcję błędów.
* Dostarczenie znaków Unicode dowodzi, że generator radzi sobie z wejściem nie‑ASCII bez dodatkowej konfiguracji.

## Jak skonfigurować wygląd kodu kreskowego

Możesz kontrolować rozmiar każdego modułu, liczbę kolumn oraz to, czy kod używa trybu kompaktowego (skróconego). Ustawienia te wpływają zarówno na czytelność, jak i rozmiar pliku.

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### Praktyczna wskazówka

Jeśli potrzebujesz wyższego kodu kreskowego przy ograniczonej przestrzeni poziomej, zwiększ `Columns`. Ustawienie `Truncate` na `true` zmniejsza całkowitą wysokość, usuwając strefy ciszy, co jest idealne dla ekranów mobilnych.

## Jak zapisać obraz kodu kreskowego jako PNG

Po skonfigurowaniu generatora wywołaj `Save` z ścieżką pliku i żądanym formatem obrazu. Metoda zapisuje obraz bezpośrednio na dysku.

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### Oczekiwany rezultat

Uruchomienie programu tworzy plik `CompactPdf417.png` w folderze projektu. Otwarcie pliku pokazuje kompaktowy kod PDF417, który koduje ciąg *Åspóse.Barcóde©*. Obraz można osadzić w HTML, raportach PDF lub wydrukować na etykietach.

## Pełny kod źródłowy

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Skopiuj go do `Program.cs` i wykonaj `dotnet run`.

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Weryfikacja wyniku

Po zakończeniu programu możesz szybko sprawdzić, czy plik istnieje, używając polecenia:

```bash
dotnet run && ls -l CompactPdf417.png
```

Jeśli plik się pojawi, proces **tworzenia kodu kreskowego PDF417** zakończył się sukcesem.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Dłuższy ciąg danych** | Zwiększ `Columns` lub ustaw `Rows`, aby pomieścić więcej kodowych słów. |
| **Inny format obrazu** | Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`. |
| **Wyższa rozdzielczość** | Ustaw `generator.Parameters.ImageResolution` przed wywołaniem `Save`. |
| **Kolor tła** | Użyj `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Obsługa wyjątków** | Owiń `generator.Save` w blok `try/catch`, aby przechwycić błędy I/O. |

Te warianty pozwalają dostosować kod kreskowy do konkretnych urządzeń lub wymagań brandingowych.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy PDF417** w C# przy użyciu Aspose.Barcode, jak skonfigurować jego wygląd oraz **zapisać obraz kodu kreskowego** jako plik PNG. Pełny przykład demonstruje każdy niezbędny krok, od konfiguracji projektu po weryfikację, dzięki czemu możesz zintegrować generowanie kodów kreskowych z dowolnym rozwiązaniem .NET.

Następnie rozważ zgłębienie tematów takich jak **generowanie kodów QR**, **osadzanie kodów kreskowych w dokumentach PDF** lub **personalizacja kolorów kodów kreskowych**. Wszystkie te zagadnienia opierają się na tym samym API generatora, co pozwala rozszerzyć możliwości skanowania w Twojej aplikacji przy minimalnym wysiłku. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}