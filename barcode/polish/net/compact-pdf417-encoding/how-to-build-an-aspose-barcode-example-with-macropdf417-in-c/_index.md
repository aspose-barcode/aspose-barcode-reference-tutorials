---
category: general
date: 2026-10-12
description: Poznaj, jak stworzyć przykład kodu kreskowego Aspose w C#, który generuje
  kod MacroPdf417 z pełnymi metadanymi i odczytuje go przy użyciu BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: pl
lastmod: 2026-10-12
og_description: Przykład kodu kreskowego Aspose w C#, który pokazuje, jak wygenerować
  kod MacroPdf417 z osadzonymi metadanymi i odczytać go za pomocą BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Utwórz przykład kodu kreskowego Aspose z MacroPdf417 w C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Jak zbudować przykład kodu kreskowego Aspose z MacroPdf417 w C#
url: /pl/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zbudować przykład Aspose barcode z MacroPdf417 w C#

Jeśli potrzebujesz **aspose barcode example**, które tworzy kod kreskowy MacroPdf417 i odczytuje osadzone metadane, ten przewodnik pokaże Ci kompletny przepływ pracy. Zobaczysz, jak skonfigurować generator, osadzić informacje na poziomie pliku, zapisać obraz oraz następnie zdekodować te same dane przy użyciu `BarCodeReader`.

Samouczek obejmuje wszystko, co musisz wiedzieć o **C# barcode generation** przy użyciu Aspose.BarCode, w tym typowe pułapki i wskazówki dotyczące obsługi dużych identyfikatorów plików lub niestandardowych znaczników czasu.

## Czego będziesz potrzebował

* .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
* Visual Studio 2022 lub dowolne IDE obsługujące C#
* Aktywna licencja Aspose.BarCode (bezpłatna wersja próbna działa w środowisku deweloperskim)
* Pakiet NuGet `Aspose.BarCode` zainstalowany w projekcie

Te wymagania wstępne gwarantują, że przykład uruchomi się bez dodatkowej konfiguracji.

## Krok 1: Skonfiguruj projekt przykładu Aspose barcode

Utwórz nową aplikację konsolową i dodaj bibliotekę Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Pakiet `Aspose.BarCode` dostarcza `BarcodeGenerator`, `BarCodeReader` oraz wszystkie typy potrzebne do obsługi MacroPdf417.

### Dlaczego ten krok jest ważny
Dodanie pakietu NuGet rozwiązuje enumy `EncodeTypes`, `DecodeType` i `BarCodeImageFormat` używane później. Bez tego pakietu kompilator nie rozpozna tych symboli i przykład nie skompiluje się.

## Krok 2: Utwórz generator kodu kreskowego MacroPdf417

Otwórz **Program.cs** i zamień kod szablonu następującym blokiem. Ten blok tworzy `BarcodeGenerator` skonfigurowany dla symbolu MacroPdf417 i ustawia podstawowe parametry wyglądu.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Wyjaśnienie kluczowych właściwości

| Właściwość | Cel | Typowy zakres / uwagi |
|------------|-----|-----------------------|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku | Musi być ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu | Zaczyna się od 0 |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów w pliku | Musi być ≥ SegmentID |
| `MacroPdf417FileName` | Czytelna nazwa pliku | Do 255 znaków |
| `MacroPdf417Checksum` | Suma kontrolna CCITT‑16 oryginalnego pliku | Obliczana przez zewnętrzne narzędzie w razie potrzeby |
| `MacroPdf417FileSize` | Rozmiar oryginalnego pliku w bajtach | Przydatne do walidacji |
| `MacroPdf417TimeStamp` | Data/godzina utworzenia pliku | Używaj UTC dla spójności |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcjonalne informacje routingu | Dowolny ciąg do 255 znaków |
| `MacroPdf417Terminator` | Oznacza ostatni segment | Użyj `Set` dla ostatniego segmentu |

Te pola stanowią **metadata kodu kreskowego**, które czytnik może później wyodrębnić.

## Krok 3: Zdekoduj kod kreskowy i wyświetl metadane

Po zapisaniu obrazu, ten sam program kontynuuje otwieranie pliku przy użyciu `BarCodeReader`. Dodaj następujący kod wewnątrz metody `Main`, po poprzednim bloku `using`:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Dlaczego odczyt zwrotny jest ważny
`BarCodeReader` weryfikuje, czy osadzone metadane są poprawnie zakodowane. Jeśli jakaś właściwość jest brakująca lub poza zakresem, czytnik zwraca `null` dla tego pola, co pozwala na eleganckie obsłużenie błędów.

## Krok 4: Uruchom i zweryfikuj wynik

Uruchom program:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście konsoli podobne do:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Jeśli wartości są zgodne z tymi ustawionymi w Kroku 2, **aspose barcode example** działa zgodnie z oczekiwaniami.

## Przypadki brzegowe i wskazówki najlepszych praktyk

| Sytuacja | Na co zwrócić uwagę | Zalecane postępowanie |
|----------|---------------------|-----------------------|
| **FileID exceeds 32‑bit range** | Aspose rzuca `ArgumentOutOfRangeException`. | Utrzymuj ID ≤ 2 147 483 647 lub podziel plik na wiele bloków MacroPdf417. |
| **Timestamp in local time** | Czytniki w innej strefie czasowej mogą źle zinterpretować wartość. | Przechowuj znaczniki czasu w UTC (`DateTime.UtcNow`) i konwertuj przy wyświetlaniu w razie potrzeby. |
| **Large file size** | `MacroPdf417FileSize` jest typu `int`; wartości > 2 GB przepełniają. | Użyj pola niestandardowego lub podziel plik na mniejsze segmenty. |
| **Missing segment** | Jeśli `SegmentID` nie jest kolejny, rekonstrukcja nie powiedzie się. | Zweryfikuj kolejność segmentów przed kodowaniem lub użyj ustawień korekcji błędów. |
| **Unsupported image format** | Zapis jako BMP może znacznie zwiększyć rozmiar. | PNG jest dobrym domyślnym wyborem; JPEG można użyć, jeśli akceptujesz kompresję stratną. |

**Pro tip:** Gdy generujesz wiele kodów kreskowych w partii, ponownie używaj jednej instancji `BarcodeGenerator` i zmieniaj tylko `EncodeTypes` oraz tekst źródłowy. To zmniejsza alokacje pamięci i przyspiesza przetwarzanie.

## Powiązane tematy, które możesz zbadać dalej

* **Other macro symbologies** – Aspose również obsługuje MacroPdf417 z poziomami korekcji błędów.
* **Embedding barcodes in PDFs** – Połącz `Aspose.PDF` z generatorem kodów kreskowych, aby tworzyć dokumenty do druku.
* **ASP.NET Core integration** – Udostępniaj wygenerowane kody kreskowe bezpośrednio z API webowego.
* **Scanning via mobile devices** – Użyj SDK `Aspose.BarCode.Cloud` do dekodowania wieloplatformowego.

Te tematy uzupełniające naturalnie rozszerzają **aspose barcode example** i pogłębiają Twoją wiedzę w zakresie **C# barcode generation**.

## Zakończenie

Masz teraz w pełni funkcjonalny **aspose barcode example**, który tworzy kod MacroPdf417, osadza bogate **metadata kodu kreskowego**, zapisuje obraz i odczytuje dane z powrotem przy użyciu `BarCodeReader`. Postępując zgodnie z powyższymi krokami, możesz dostosować kod do różnych identyfikatorów plików, znaczników czasu lub nawet innych typów kodów kreskowych obsługiwanych przez Aspose.

Śmiało eksperymentuj z dodatkowymi polami metadata, zmieniaj format obrazu lub integruj generator w większej aplikacji. Szczęśliwego kodowania!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}