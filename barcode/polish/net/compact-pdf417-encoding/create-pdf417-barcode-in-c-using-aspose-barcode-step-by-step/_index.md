---
category: general
date: 2026-10-18
description: Dowiedz się, jak tworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Ten samouczek obejmuje generowanie podstawowego, kompaktowego, makro i mikro PDF417
  wraz z pełnym kodem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: pl
lastmod: 2026-10-18
og_description: Utwórz kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Postępuj
  zgodnie z tym przewodnikiem, aby krok po kroku generować podstawowe, kompaktowe,
  makro i mikro kody PDF417.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Tworzenie kodu kreskowego PDF417 w C# – kompletny samouczek Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Tworzenie kodu kreskowego PDF417 w C# przy użyciu Aspose.BarCode – przewodnik
  krok po kroku
url: /pl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417** w aplikacji .NET, ten samouczek przeprowadzi Cię przez cały proces. Zobaczysz, jak wygenerować podstawowy kod kreskowy, włączyć tryb kompaktowy, dodać metadane makro oraz stworzyć wariant mikro — wszystko z klarownymi wyjaśnieniami i gotowym do uruchomienia kodem.

Generowanie kodów kreskowych PDF417 jest powszechne w logistyce, systemach biletowych i zarządzaniu dokumentami. Po zakończeniu tego przewodnika będziesz w stanie zintegrować tworzenie kodów kreskowych z dowolnym projektem C# bez użycia zewnętrznych narzędzi.

## Wymagania wstępne

* .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
* Visual Studio 2022 lub dowolne IDE C#
* **Aspose.BarCode for .NET** pakiet NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Uprawnienia do zapisu w folderze, w którym będą zapisywane wygenerowane pliki PNG

Nie wymagana jest dodatkowa konfiguracja; biblioteka obsługuje wszystkie szczegóły kodowania niskiego poziomu.

## Krok 1: Utwórz podstawowy kod kreskowy PDF417

Pierwszy krok tworzy standardowy kod kreskowy PDF417 o niestandardowym rozmiarze i liczbie kolumn.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Dlaczego te ustawienia mają znaczenie**

* `XDimension.Pixels` kontroluje fizyczny rozmiar każdego elementu kodu kreskowego. Wartość 2 tworzy wyraźny obraz na większości ekranów i drukarek.
* `Pdf417.Columns` określa, ile kolumn danych zawiera kod kreskowy. Mniej kolumn zmniejsza szerokość; więcej kolumn zwiększa pojemność danych.

Uruchomienie kodu tworzy plik `Pdf417Basic.png`, który wygląda jak typowy symbol PDF417 z trzema kolumnami danych i pełną kolumną metadanych po prawej stronie.

## Krok 2: Włącz tryb kompaktowy (obcięty)

Tryb kompaktowy usuwa prawą kolumnę metadanych, co sprawia, że kod kreskowy jest węższy. Jest to przydatne, gdy miejsce jest ograniczone, ale dane można odtworzyć z pozostałych wierszy.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Dlaczego obcinać?**  
Gdy `Truncate` ma wartość `true`, generator pomija opcjonalną prawą kolumnę, w której przechowywane są korekcje błędów i metadane na poziomie pliku. Powstały kod kreskowy zajmuje mniej kolumn, a jednocześnie jest nadal odczytywalny przez większość czytników PDF417.

## Krok 3: Utwórz kod kreskowy Macro PDF417 z metadanymi na poziomie pliku

Macro PDF417 rozszerza standardowy format o identyfikatory segmentów, umożliwiając podzielenie dużego dokumentu na wiele kodów kreskowych. Jest to przydatne przy kodowaniu długich ciągów znaków lub wielostronicowych plików.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Wyjaśnienie pól makro**

| Właściwość | Cel |
|------------|-----|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku; wszystkie segmenty dzielą tę wartość. |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 1). |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów tworzących pełny zestaw danych. |

Skaner obsługujący Macro PDF417 może odtworzyć oryginalne dane, odczytując wszystkie segmenty i wykorzystując te identyfikatory.

## Krok 4: Utwórz kod kreskowy Micro PDF417 dla krótkich danych

Micro PDF417 to kompaktowa wersja przeznaczona dla małych ładunków danych (do 90 znaków). Ogranicza zakres kolumn do 1‑4, co czyni kod kreskowy odpowiednim dla małych etykiet lub urządzeń o ograniczonej powierzchni wyświetlacza.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Kiedy używać Micro PDF417**  
Użyj tej wersji, gdy ładunek danych jest krótki i potrzebny jest jak najmniejszy kod kreskowy. Jest idealny dla etykiet inwentaryzacyjnych, kart dostępu lub każdego scenariusza, w którym przestrzeń wyświetlacza jest na wagę złota.

## Pełny działający przykład

Poniżej znajduje się samodzielna aplikacja konsolowa, która generuje wszystkie cztery typy kodów kreskowych w jednym uruchomieniu. Skopiuj kod do nowego projektu C#, zamień `YOUR_DIRECTORY` na istniejącą ścieżkę folderu i uruchom go.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu tworzy cztery pliki PNG w określonym folderze:

* `Pdf417Basic.png` – standardowy kod kreskowy z trzema kolumnami
* `CompactPdf417.png` – te same dane, obcięta prawa kolumna
* `MacroPdf417.png` – kod makro zawierający metadane segmentu
* `MicroPdf417.png` – kompaktowy kod micro dla krótkich ciągów znaków

Otwórz dowolny obraz w przeglądarce zdjęć; zobaczysz charakterystyczne wzory PDF417. Zeskanowanie ich przy pomocy mobilnego czytnika kodów kreskowych (np. ZXing, Scandit) zwróci oryginalne ciągi tekstowe.

## Częste pytania i wskazówki

* **Co zrobić, gdy kod kreskowy jest rozmyty?**  
  Zwiększ `XDimension.Pixels` do 3 lub 4. Większe rozmiary modułów dają obrazy o wyższej rozdzielczości, kosztem większego pliku.

* **Czy mogę wyjść w formacie SVG zamiast PNG?**  
  Tak. Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Svg` w wywołaniach `Save`.

* **Czy muszę ręcznie ustawiać poziom korekcji błędów?**  
  Aspose.BarCode automatycznie wybiera optymalny poziom. W specjalistycznych przypadkach możesz dostosować `Pdf417.ErrorCorrectionLevel`.

* **Jak osadzić kod kreskowy w dokumencie PDF?**  
  Użyj `Aspose.Pdf`, aby dodać wygenerowany PNG lub SVG jako element obrazu na stronie PDF.

* **Czy biblioteka jest bezpieczna wątkowo?**  
  Każda instancja `BarcodeGenerator` jest niezależna; możesz tworzyć generatory w wielu wątkach bez współdzielonego stanu.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy PDF417** w C# przy użyciu Aspose.BarCode, obejmując podstawowe, kompaktowe, makro i mikro warianty.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy pdf417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Jak utworzyć kod kreskowy macro PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}