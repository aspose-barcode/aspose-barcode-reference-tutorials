---
category: general
date: 2026-08-19
description: Generuj kod kreskowy w C# przy użyciu Aspose.BarCode, aby utworzyć Macro
  PDF417 z niestandardowym tekstem i zapisać jako plik obrazu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: pl
lastmod: 2026-08-19
og_description: Generuj kod kreskowy w C# przy użyciu Aspose.BarCode, dowiedz się,
  jak generować PDF417, dodaj własny tekst i zapisz plik obrazu kodu kreskowego.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Generowanie kodu kreskowego C# – przewodnik po Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generowanie kodu kreskowego C# z Macro PDF417 – pełny przykład
url: /pl/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego C# z Macro PDF417 – pełny przykład

Jeśli potrzebujesz **generate barcode C#** dla formatu Macro PDF417, ten przewodnik pokazuje gotowe rozwiązanie do uruchomienia. Zobaczysz, jak **how to generate pdf417**, osadzić własny tekst i **generate barcode image file** w jednym, samodzielnym programie.

Samouczek obejmuje wszystko, od instalacji biblioteki Aspose.BarCode po konfigurowanie metadanych Macro PDF417, dzięki czemu możesz skopiować kod bezpośrednio do swojego projektu i od razu zobaczyć wynik.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 (lub dowolne IDE obsługujące C#)
- Licencja Aspose.BarCode for .NET (bezpłatna wersja próbna działa w celach oceny)
- Podstawowa znajomość składni C#

> **Wskazówka:** Zainstaluj pakiet NuGet za pomocą CLI, aby uniknąć niezgodności wersji:  
> `dotnet add package Aspose.BarCode`

## Krok 1: Skonfiguruj projekt i zaimportuj bibliotekę

Utwórz nową aplikację konsolową i dodaj wymagane dyrektywy `using`.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Dlaczego ten krok jest ważny:**  
`Namespace` `Aspose.BarCode.Generation` udostępnia klasę `BarcodeGenerator`, która jest punktem wejścia do tworzenia dowolnego typu kodu kreskowego, w tym Macro PDF417. Importowanie `System` daje dostęp do `DateTime` potrzebnego do metadanych znacznika czasu.

## Krok 2: Utwórz generator Macro PDF417 z własnym tekstem

Zastąp komentarz zastępczy inicjalizacją generatora. To pokazuje **create barcode custom text**, jednocześnie wybierając właściwy typ kodowania.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Wyjaśnienie:**  
- `EncodeTypes.MacroPdf417` informuje Aspose, aby wygenerował kod PDF417 obsługujący funkcje makro (segmentacja pliku, suma kontrolna itp.).  
- Tekst `"Åspóse.Barcóde©"` pokazuje, że znaki Unicode są w pełni obsługiwane, co często jest wymagane w aplikacjach międzynarodowych.

## Krok 3: Skonfiguruj wygląd i metadane Macro PDF417

Doprecyzuj wymiary kodu kreskowego i ustaw pola specyficzne dla makro, niezbędne do obsługi segmentowanych plików.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Dlaczego te ustawienia są ważne:**

| Ustawienie | Cel |
|------------|-----|
| `XDimension.Pixels` | Kontroluje gęstość wizualną; 2 px zapewnia wyraźny, możliwy do zeskanowania obraz. |
| `Columns` | Określa liczbę kolumn danych w wierszu, wpływając na rozmiar kodu. |
| `MacroPdf417FileID` | Unikalnie identyfikuje logiczny plik we wszystkich segmentach. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Umożliwia odtworzenie oryginalnego pliku z wielu kodów. |
| `MacroPdf417FileName` | Czytelna dla człowieka nazwa przechowywana w kodzie kreskowym do dalszego przetwarzania. |
| `MacroPdf417Checksum` | Zapewnia wykrywanie błędów przy użyciu algorytmu CCITT‑16 CRC. |
| `MacroPdf417FileSize` | Pomaga dekoderowi określić, kiedy cały plik został odebrany. |
| `MacroPdf417TimeStamp` | Rejestruje moment generowania kodu, przydatny w ścieżkach audytu. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcjonalne pola, które mogą być używane w procesach biznesowych. |
| `MacroPdf417Terminator` | Wskazuje, że ten segment jest ostatni (`Set`). |

## Krok 4: Zapisz kod kreskowy jako plik obrazu

Na koniec zapisz kod kreskowy do pliku PNG, aby móc go wyświetlić lub osadzić w innym miejscu.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Co zobaczysz:**  
Obraz PNG o nazwie `ExtPDF417Meta.png` zawierający kod Macro PDF417, który koduje własny tekst oraz wszystkie pola metadanych ustawione powyżej. Obraz można otworzyć w dowolnym standardowym przeglądarce lub wstawić do plików PDF, raportów czy stron internetowych.

## Pełny kod źródłowy (gotowy do kopiowania)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu wypisuje:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Otworzenie `ExtPDF417Meta.png` pokazuje czysty kod Macro PDF417, który skanuje się poprawnie w każdym czytniku PDF417, zachowując własny tekst `"Åspóse.Barcóde©"` oraz zdefiniowane metadane makro.

## Częste pytania i przypadki brzegowe

- **Czy mogę wygenerować inny format obrazu?**  
  Tak. Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Gif` w zależności od potrzeb.

- **Co zrobić, jeśli moje dane przekraczają jeden kod kreskowy?**  
  Macro PDF417 jest zaprojektowany do segmentacji. Dostosuj `MacroPdf417SegmentsCount` i `MacroPdf417SegmentID` dla każdej części, a następnie połącz zeskanowane wyniki.

- **Czy wsparcie Unicode jest gwarantowane?**  
  Aspose.BarCode w pełni obsługuje Unicode. Upewnij się, że plik źródłowy jest zapisany w kodowaniu UTF‑8, aby uniknąć uszkodzenia znaków.

- **Czy potrzebna jest licencja do produkcji?**  
  Wersja licencjonowana usuwa znak wodny oceny i zapewnia pełną funkcjonalność. Wersja próbna działa do testów i nauki.

## Podsumowanie

Teraz wiesz, jak **generate barcode C#** dla Macro PDF417, **how to generate pdf417** z bogatymi metadanymi, **create barcode custom text** oraz **generate barcode image file** przy użyciu Aspose.BarCode. Pełny, działający przykład demonstruje każdy wymagany krok — od konfiguracji projektu po zapisanie ostatecznego obrazu PNG.

### Kolejne kroki

- Eksperymentuj z innymi ustawieniami PDF417, takimi jak `ErrorCorrectionLevel` i `CompactPdf417`, aby uzyskać mniejsze symbole.  
- Zintegruj wygenerowany kod kreskowy w raporcie PDF przy użyciu Aspose.PDF.  
- Zbadaj generowanie wsadowe: iteruj po kolekcji plików i twórz serię segmentowanych kodów Macro PDF417.

Śmiało dostosuj kod do własnego przepływu pracy, aby generowanie kodów kreskowych stało się płynną częścią Twoich aplikacji C#. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generowanie obrazu kodu kreskowego – Code 93 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Jak generować i dostosowywać wysokość kodu kreskowego One-Dimensional Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}