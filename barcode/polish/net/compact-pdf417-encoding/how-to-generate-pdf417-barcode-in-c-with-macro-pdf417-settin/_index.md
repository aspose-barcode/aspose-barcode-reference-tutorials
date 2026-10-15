---
category: general
date: 2026-10-15
description: Dowiedz się, jak generować kod kreskowy PDF417 w C# przy użyciu parametrów
  Macro‑PDF417, ustawiać wymiary kodu i zapisywać jako PNG. Dołączony pełny przykład
  kodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: pl
lastmod: 2026-10-15
og_description: Jak wygenerować kod kreskowy PDF417 w C# z pełną konfiguracją Macro‑PDF417,
  kontrolą wymiarów i wyjściem PNG. Śledź kompletny przykład.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Jak wygenerować kod kreskowy PDF417 w C# z ustawieniami Macro‑PDF417
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# z ustawieniami Macro‑PDF417

Jeśli potrzebujesz **jak wygenerować kod kreskowy PDF417** w przepływie dokumentów, ten przewodnik pokaże Ci dokładne kroki. Zobaczysz, jak skonfigurować parametry Macro‑PDF417, ustawić wymiary kodu kreskowego i wyeksportować wynik jako obraz PNG — wszystko w jednym, uruchamialnym programie C#.

Generowanie kodu kreskowego PDF417 nie wymaga wielu bibliotek ani skomplikowanego przetwarzania pośredniego. Korzystając z Aspose.Barcode dla .NET, możesz kontrolować każdy aspekt kodu, od szerokości modułu po sumę kontrolną, i uzyskać wysokiej jakości obraz gotowy do druku lub skanowania.

## Wymagania wstępne

* Zainstalowany SDK .NET 6.0 (lub nowszy)  
* Visual Studio 2022 lub dowolne preferowane środowisko IDE dla C#  
* Pakiet NuGet Aspose.Barcode dla .NET (`Install-Package Aspose.Barcode`)  

Te wymagania zapewniają, że kod kompiluje się bez dodatkowej konfiguracji.

## Krok 1: Utwórz generator kodu kreskowego dla kodu Macro‑PDF417

Pierwsza operacja tworzy instancję `BarcodeGenerator`, która celuje w format `EncodeTypes.MacroPdf417`. Konstruktor otrzymuje dane, które chcesz zakodować — w tym przypadku łańcuch `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Utworzenie generatora konfiguruje wewnętrzny obiekt `Parameters`, którego użyjesz do dostosowania właściwości **C# PDF417 barcode**.

## Krok 2: Ustaw podstawowy wygląd kodu kreskowego – określ wymiary kodu

Kontrolowanie wizualnego rozmiaru kodu kreskowego zwiększa niezawodność skanowania. Właściwość `XDimension.Pixels` definiuje szerokość modułu (kropki), natomiast `Pdf417.Columns` określa liczbę kolumn, które kod będzie zawierał.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Ustawienie tych wymiarów zapewnia, że kod mieści się w typowych rozmiarach etykiet i spełnia specyfikacje skanera.

## Krok 3: Dostarcz identyfikację pliku Macro‑PDF417

Macro‑PDF417 rozszerza standardowy kod PDF417 o metadane na poziomie pliku. Musisz przypisać unikalny identyfikator pliku, identyfikator segmentu, całkowitą liczbę segmentów oraz czytelną nazwę pliku.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Te **parametry Macro PDF417** umożliwiają systemom downstream odtworzenie oryginalnego pliku z wielu segmentów kodu kreskowego.

## Krok 4: Dodaj dodatkowe metadane macro — uwzględnij sumę kontrolną kodu

Oprócz identyfikacji, Macro‑PDF417 może przechowywać sumę kontrolną, rozmiar pliku, znacznik czasu, odbiorcę, nadawcę oraz flagę zakończenia. Dostarczenie sumy kontrolnej poprawia sprawdzanie integralności danych podczas dekodowania.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Dołączenie **sumy kontrolnej kodu kreskowego** i innych metadanych sprawia, że kod jest samopiszący się, co jest cenne w zautomatyzowanych pipeline'ach przetwarzania dokumentów.

## Krok 5: Zapisz wygenerowany kod jako obraz PNG — wybierz format obrazu kodu

Ostatni krok zapisuje kod do pliku. Metoda `Save` przyjmuje ścieżkę pliku oraz wyliczenie `BarCodeImageFormat`. PNG zapewnia bezstratną kompresję, zachowując ostre krawędzie dla niezawodnego skanowania.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Po wykonaniu, plik `MacroPdf417.png` zawiera wyraźny kod PDF417 gotowy do osadzenia w PDF-ach, drukowania na etykietach lub wyświetlania na ekranach.

## Oczekiwany wynik

Otwierając `C:/Barcodes/MacroPdf417.png` zobaczysz prostokątny kod kreskowy z zakodowanym tekstem „Sample text”. Kod zawiera ustawione przez Ciebie metadane macro, które możesz zweryfikować dowolnym skanerem PDF417 obsługującym Macro‑PDF417. Wymiary obrazu odzwierciedlają szerokość modułu (2 px) i liczbę kolumn (5), co daje kompaktowy, ale czytelny kod.

## Typowe wariacje i przypadki brzegowe

| Situation | Adjustment |
|-----------|------------|
| **Different data length** | Zastąp `"Sample text"` dowolnym ciągiem UTF‑8; generator automatycznie dostosuje rozmiar kodu. |
| **Higher resolution** | Zwiększ `XDimension.Pixels` do 3 lub 4, aby uzyskać większe moduły, przydatne przy drukarkach o niskiej rozdzielczości. |
| **More segments** | Zmien `MacroPdf417SegmentsCount`, aby odpowiadał całkowitej liczbie części kodu, które planujesz wygenerować. |
| **Alternative image format** | Użyj `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp`, jeśli Twój system downstream preferuje te formaty. |
| **Custom error correction** | Zmodyfikuj `generator.Parameters.Barcode.Pdf417.ErrorLevel` (zakres 0‑8), aby wymienić gęstość danych na tolerancję błędów. |

**Wskazówka:** Zawsze weryfikuj wygenerowany kod przy użyciu fizycznego skanera przed wdrożeniem go do produkcji. Skanery mogą mieć ograniczenia firmware dotyczące szerokości modułu lub liczby kolumn.

## Pełny kod źródłowy

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Uruchomienie tego programu tworzy `MacroPdf417.png` w folderze `C:/Barcodes`. Konsola potwierdza pomyślne wygenerowanie.

## Zakończenie

Teraz wiesz, **jak wygenerować kod kreskowy PDF417** w C# z pełną kontrolą Macro‑PDF417, jak **ustawić wymiary kodu**, jak osadzić **sumę kontrolną kodu** i inne metadane macro oraz jak wyeksportować wynik przy użyciu wybranego **formatu obrazu kodu**. Pełny przykład można skopiować do dowolnego projektu .NET, zmodyfikować pod różne ładunki danych i zintegrować z większymi pipeline'ami automatyzacji dokumentów.

### Kolejne kroki

* Zbadaj poziomy korekcji błędów **C# PDF417 barcode**, aby poprawić niezawodność skanowania.  
* Połącz wiele segmentów Macro‑PDF417, aby zakodować duże pliki, takie jak PDF‑y lub obrazy.  
* Przełącz **format obrazu kodu** na SVG, aby uzyskać skalowalną grafikę wektorową w aplikacjach internetowych.  

Śmiało eksperymentuj z parametrami i podziel się wynikami w komentarzach lub na forach społecznościowych. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}