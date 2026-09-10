---
category: general
date: 2026-09-10
description: Jak generować kody kreskowe PDF417 w C# przy użyciu Aspose.BarCode. Postępuj
  zgodnie z przewodnikiem krok po kroku, aby utworzyć Macro PDF417, dostosować parametry
  i wyeksportować jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: pl
lastmod: 2026-09-10
og_description: Jak generować kody kreskowe PDF417 w C# przy użyciu Aspose.BarCode.
  Poznaj pełny przebieg pracy od konfiguracji po zapisanie obrazu Macro PDF417 w formacie
  PNG.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Jak generować kody kreskowe PDF417 w C# – kompletny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Jak generować kody kreskowe PDF417 w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kody kreskowe PDF417 w C# z Aspose.BarCode

Jeśli potrzebujesz **jak generować pdf417** w projekcie .NET, ten samouczek pokazuje kompletny przebieg pracy. Zobaczysz, jak stworzyć kod kreskowy Macro PDF417, dopracować jego ustawienia i wyeksportować wynik jako obraz PNG — wszystko przy użyciu Aspose.BarCode dla .NET.

Generowanie kodów kreskowych PDF417 jest powszechne w logistyce, systemach biletowych i bezpiecznych przepływach dokumentów. Po zakończeniu tego przewodnika będziesz mieć gotowy generator kodów kreskowych w C#, który możesz wstawić do dowolnej aplikacji.

## Czego będziesz potrzebować

- **Visual Studio 2022** (lub dowolne IDE C#)  
- **.NET 6.0** lub nowszy  
- **Aspose.BarCode for .NET** pakiet NuGet (`Install-Package Aspose.BarCode`)  
- Podstawowa znajomość składni C#  

> **Porada:** Użyj najnowszej wersji Aspose.BarCode, aby uzyskać najnowsze funkcje Macro PDF417 i poprawki błędów.

---

## Jak generować kody kreskowe PDF417 w C#  

Poniżej znajduje się w pełni działający przykład, który tworzy kod kreskowy **Macro PDF417**, konfiguruje jego pola specyficzne dla makra i zapisuje obraz.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Dlaczego każdy krok ma znaczenie

1. **Utwórz generator Macro PDF417** – `EncodeTypes.MacroPdf417` informuje Aspose.BarCode, aby używał wersji makro PDF417, która obsługuje podział dużej ładowności na wiele symboli.  
2. **Dostosuj podstawowy wygląd** – `XDimension` kontroluje szerokość modułu (kropki); `Columns` określa liczbę kolumn w każdym symbolu, wpływając na rozmiar i czytelność.  
3. **Ustaw pola specyficzne dla makra** – Te właściwości (`MacroPdf417FileID`, `MacroPdf417SegmentID` itd.) są wymagane przez specyfikację makra PDF417, aby odtworzyć oryginalne dane po stronie skanera.  
4. **Wyeksportuj obraz** – `BarCodeImageFormat.Png` zapewnia obraz bezstratny, który dobrze sprawdza się w sieci, druku i na urządzeniach mobilnych.

---

## Konfigurowanie Aspose.BarCode dla .NET (generator kodów kreskowych C#)

Zanim będziesz mógł uruchomić powyższy kod, musisz dodać bibliotekę Aspose.BarCode do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

*Pakiet NuGet zawiera wszystkie zależności, więc nie są potrzebne dodatkowe pliki DLL.*

Jeśli celujesz w .NET Framework, to samo polecenie `Install-Package Aspose.BarCode` działa z konsoli Package Manager Console.

### Częste pułapki

- **Brak licencji** – Domyślnie Aspose działa w trybie ewaluacyjnym, który dodaje znak wodny do kodu kreskowego. Zarejestruj plik licencji (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`), aby go usunąć.  
- **Nieprawidłowy `EncodeTypes`** – Użycie `EncodeTypes.Pdf417` zamiast `EncodeTypes.MacroPdf417` spowoduje zignorowanie wszystkich pól makra, co zepsuje rekonstrukcję wielosegmentową.

---

## Konfigurowanie parametrów kodu kreskowego Macro PDF417

Pola makra pozwalają podzielić duży dokument na kilka symboli PDF417. Oto szybka tabela odniesienia:

| Property | Purpose | Typical range |
|----------|---------|---------------|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów w pliku | 1‑255 |
| `MacroPdf417FileName` | Opcjonalna nazwa czytelna dla człowieka | 0‑255 characters |
| `MacroPdf417Checksum` | Suma kontrolna CCITT‑16 do wykrywania błędów | 0‑65535 |
| `MacroPdf417FileSize` | Rozmiar oryginalnego pliku w bajtach | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Znacznik czasu utworzenia (opcjonalny) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcjonalne metadane do routingu | Any string |
| `MacroPdf417Terminator` | Wskazuje ostatni segment (`Set` lub `Unset`) | `Pdf417MacroTerminator` enum |

Dostosuj te wartości do danych, które kodujesz. Na przykład, jeśli podzielisz plik o wielkości 2 MB na 20 segmentów, ustaw `MacroPdf417FileSize` na `2_000_000` oraz `MacroPdf417SegmentsCount` na `20`.

---

## Eksportowanie kodu kreskowego jako obrazu PNG (eksport obrazu kodu kreskowego)

Zapisywanie kodu kreskowego jako PNG jest najczęstszym formatem eksportu, ponieważ zachowuje ostre krawędzie i obsługuje przezroczystość. Aspose.BarCode obsługuje także JPEG, BMP, GIF i TIFF — wybierz ten, który pasuje do Twojego dalszego procesu.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Wskazówki dla wysokiej jakości wyjścia**

- Zwiększ `XDimension.Pixels` dla większych modułów przy drukowaniu na nośnikach wysokiej rozdzielczości.  
- Użyj `BarCodeImageFormat.Tiff` z kompresją CCITT Group 4 dla PDF‑ów kompatybilnych z faksem.  
- Ustaw `generator.Parameters.ImageOptions.Resolution`, jeśli potrzebujesz określonej liczby DPI (np. 300 dpi do druku).

---

## Testowanie i rozwiązywanie problemów z kodem kreskowym PDF417

1. **Weryfikacja wizualna** – Otwórz `MacroPdf417.png` w dowolnym przeglądarce obrazów. Powinieneś zobaczyć ułożony stos pionowych pasków z małym podpisem tekstowym (zakodowane dane).  
2. **Test skanera** – Użyj aplikacji mobilnej do skanowania kodów kreskowych, która obsługuje PDF417. Zeskanuj obraz; aplikacja powinna zwrócić oryginalny „Sample text” oraz metadane makra (file ID, segment ID itp.).  
3. **Obsługa błędów** – Jeśli skaner zgłasza „checksum error”, sprawdź podwójnie `MacroPdf417Checksum` i upewnij się, że `MacroPdf417Terminator` jest prawidłowo ustawiony w ostatnim segmencie.  
4. **Wydajność** – Generowanie wielu segmentów w pętli może być intensywne dla CPU. Ponownie używaj jednej instancji `BarcodeGenerator` i aktualizuj jedynie pola makra pomiędzy zapisami, aby zwiększyć przepustowość.

---

## Podsumowanie

Teraz wiesz **jak generować kody kreskowe PDF417** w C# przy użyciu Aspose.BarCode, od instalacji biblioteki po konfigurowanie pól Macro PDF417 i eksportowanie czystego obrazu PNG. Pełne rozwiązanie demonstruje:

- Konfigurowanie **generatora kodów kreskowych C#** z typem Macro PDF417  
- Dostosowywanie **parametrów kodu kreskowego PDF417** dla danych wielosegmentowych  
- Wykonywanie **eksportu obrazu kodu kreskowego** do dalszego użycia  

Od tego momentu możesz zgłębiać zaawansowane tematy, takie jak osadzanie kodu kreskowego w dokumentach PDF, generowanie towarzyszących kodów QR lub automatyzacja przetwarzania wsadowego dużych plików.

**Kolejne kroki**

- Wypróbuj różne wartości `BarCodeImageFormat` (np. `Tiff` dla wydruków wysokiej rozdzielczości).  
- Połącz Macro PDF417 z innymi symbologiami w tym samym dokumencie, używając `generator.Parameters.Barcode.Symbology`.  
- Przejrzyj [dokumentację Aspose.BarCode](https://docs.aspose.com/barcode/net/) w celu głębszych opcji dostosowywania, takich jak poziom korekcji błędów i tryby kodowania.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj kod kreskowy z tekstem – Pełny przewodnik PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Dostosuj rozmiar kodu kreskowego – przewodnik C# do generowania kodów PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Jak generować kod kreskowy PDF417 – Kompletny przewodnik programistyczny](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}