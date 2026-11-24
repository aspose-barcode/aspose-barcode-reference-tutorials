---
category: general
date: 2026-11-23
description: Dowiedz się, jak wygenerować obraz kodu kreskowego przy użyciu Aspose.BarCode
  for .NET z metadanymi MacroPdf417 w języku C#. Przejdź do pełnego przewodnika krok
  po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: pl
lastmod: 2026-11-23
og_description: Jak wygenerować obraz kodu kreskowego przy użyciu Aspose.BarCode dla
  .NET. Ten samouczek pokazuje konfigurację metadanych MacroPdf417 oraz generowanie
  kodu kreskowego w C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Jak wygenerować obraz kodu kreskowego przy użyciu MacroPdf417 w C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Jak wygenerować obraz kodu kreskowego przy użyciu MacroPdf417 w C#
url: /pl/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować obraz kodu kreskowego przy użyciu MacroPdf417 w C#

Jeśli potrzebujesz **wygenerować obraz kodu kreskowego** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić przy użyciu **Aspose.BarCode for .NET**. Przejdziemy przez tworzenie **kodu kreskowego MacroPdf417**, konfigurowanie jego metadanych i zapisywanie wyniku jako plik PNG.

Ten tutorial obejmuje wszystko, od instalacji biblioteki po napisanie kompletnego, uruchamialnego programu konsolowego. Po zakończeniu będziesz mieć gotowy do użycia przykład kodu, który generuje wysokiej jakości obraz kodu kreskowego, oraz zrozumiesz, jak **ustawiać metadane kodu kreskowego**, wybierać **format obrazu kodu kreskowego** i rozwiązywać typowe problemy. Nie wymagana jest wcześniejsza znajomość Aspose — wystarczy podstawowa wiedza o C#.

## Zainstaluj Aspose.BarCode dla .NET

Zanim będziesz mógł **wygenerować obraz kodu kreskowego**, potrzebujesz pakietu NuGet Aspose.BarCode.

1. Otwórz terminal lub konsolę Package Manager w Visual Studio.  
2. Uruchom następujące polecenie:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode.Generation`, która zawiera klasę `BarcodeGenerator` używaną do **generowania kodów kreskowych w C#**.

> **Wskazówka:** Użyj najnowszej stabilnej wersji (stan na listopad 2026, aktualna wersja to 24.11), aby uzyskać najnowsze funkcje i poprawki błędów.

## Utwórz instancję BarcodeGenerator

Pierwszy krok kodu tworzy `BarcodeGenerator` skonfigurowany dla typu **kod kreskowy MacroPdf417** i podaje ciąg danych, który chcesz zakodować.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Blok `using` zapewnia prawidłowe zwolnienie generatora, uwalniając wszelkie niezarządzane zasoby.

## Skonfiguruj podstawowy wygląd

Czytelny kod kreskowy zaczyna się od rozsądnych wymiarów. Tutaj ustawiamy szerokość w pikselach każdego modułu (`XDimension`) oraz liczbę kolumn macierzy PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Dlaczego te wartości?*  
- **XDimension** kontroluje grubość każdego paska; 2 piksele działają dobrze przy wyświetlaniu na ekranie i w większości drukarek.  
- **Columns** wpływa na całkowitą szerokość; mała liczba kolumn utrzymuje kod kreskowy w kompaktowej formie, zachowując jednocześnie zdolność korekcji błędów.

## Ustaw metadane kodu kreskowego (specyficzne dla MacroPdf417)

MacroPdf417 umożliwia osadzenie informacji na poziomie pliku bezpośrednio w kodzie kreskowym. To tutaj **ustawiasz metadane kodu kreskowego**, takie jak ID pliku, ID segmentu i znaczniki czasu.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Co oznacza każde właściwość

| Właściwość | Cel |
|------------|-----|
| **MacroPdf417FileID** | Unikalny identyfikator logicznego pliku, do którego należy kod kreskowy. |
| **MacroPdf417SegmentID** | Indeks bieżącego segmentu (liczony od 0). |
| **MacroPdf417SegmentsCount** | Łączna liczba segmentów tworzących cały plik. |
| **MacroPdf417FileName** | Czytelna nazwa źródłowego pliku. |
| **MacroPdf417Checksum** | Opcjonalna suma kontrolna CCITT‑16 weryfikująca integralność danych. |
| **MacroPdf417FileSize** | Oczekiwany rozmiar oryginalnego pliku w bajtach. |
| **MacroPdf417TimeStamp** | Data i godzina wygenerowania kodu kreskowego – przydatne do śledzenia wersji. |
| **MacroPdf417Addressee / Sender** | Niestandardowe ciągi, które mogą zawierać informacje routingu. |
| **MacroPdf417Terminator** | Wskazuje, czy ten segment jest ostatnim (`Set`) czy nie (`Unset`). |

> **Przypadek brzegowy:** Jeśli planujesz podzielić duży dokument na wiele segmentów, utrzymuj `SegmentsCount` spójny we wszystkich wygenerowanych kodach kreskowych. Niepasujące liczby spowodują błędy dekodowania.

## Wybierz format obrazu kodu kreskowego i zapisz

Aspose obsługuje wiele **formatów obrazu kodu kreskowego** (PNG, JPEG, BMP, TIFF itp.). PNG jest bezstratny i dobrze sprawdza się w większości scenariuszy webowych i drukarskich.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Zastąp `YOUR_DIRECTORY` ścieżką bezwzględną lub względną do folderu, w którym aplikacja ma uprawnienia do zapisu.

Gdy program zostanie uruchomiony, powinieneś zobaczyć komunikat w konsoli potwierdzający lokalizację pliku. Otwórz plik PNG dowolnym przeglądarką obrazów — zobaczysz wyraźny **kod kreskowy MacroPdf417**, który koduje podany tekst oraz zdefiniowane metadane.

### Oczekiwany wynik

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Rozmiar pliku obrazu będzie wynosił około 30‑40 KB, w zależności od wybranej `XDimension` i liczby kolumn.

## Zweryfikuj kod kreskowy i rozwiąż problemy

1. **Inspekcja wizualna** – Kod kreskowy powinien wyświetlać serię ułożonych kolumn z cichą strefą (białym marginesem) wokół.  
2. **Test dekodowania** – Użyj aplikacji skanującej kod kreskowy lub klasy Aspose.BarCode `BarCodeReader`, aby odczytać obraz i potwierdzić, że wszystkie pola metadanych zostały poprawnie osadzone.



## Co warto nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj obraz kodu PDF417 przy użyciu Aspose.BarCode w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Jak wygenerować kod kreskowy z własnym tekstem przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Jak odczytać kody kreskowe z obrazu przy użyciu C# i Aspose.BarCode – przewodnik krok po kroku](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}