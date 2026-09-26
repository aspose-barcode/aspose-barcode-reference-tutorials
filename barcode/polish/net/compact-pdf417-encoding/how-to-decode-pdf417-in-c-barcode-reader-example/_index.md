---
category: general
date: 2026-09-26
description: Dowiedz się, jak dekodować PDF417 w C# przy użyciu przykładu czytnika
  kodów kreskowych krok po kroku. Ten przewodnik pokazuje, jak odczytać obraz kodu
  kreskowego w C# przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: pl
lastmod: 2026-09-26
og_description: Jak szybko dekodować PDF417 w C#. Skorzystaj z tego przykładu czytnika
  kodów kreskowych, aby odczytać obraz kodu kreskowego w C# przy użyciu Aspose.BarCode
  i wyodrębnić szczegóły makra.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Jak dekodować PDF417 w C# – kompletny przewodnik po czytniku kodów kreskowych
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Jak dekodować PDF417 w C# – przykład czytnika kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekodować PDF417 w C# – przykład czytnika kodów kreskowych

Jeśli potrzebujesz **jak dekodować PDF417** w aplikacji .NET, ten tutorial dostarcza kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz, jak odczytać obraz kodu kreskowego w C# przy użyciu biblioteki Aspose.BarCode, pobrać rozszerzone informacje makro PDF417 oraz wyświetlić każde istotne pole.

Dekodowanie PDF417 nie ogranicza się do zwykłego tekstu; format może przenosić dane segmentacji plików, znaczniki czasu i sumy kontrolne. Ten przewodnik przeprowadzi Cię przez każdy krok, wyjaśni, dlaczego kod jest tak skonstruowany, i wskaże typowe pułapki, które możesz napotkać przy implementacji przykładu czytnika kodów kreskowych w C#.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 (lub nowszy) SDK zainstalowany  
* Visual Studio 2022 (lub dowolne IDE kompatybilne z C#)  
* **Aspose.BarCode for .NET** pakiet NuGet (`Aspose.BarCode`)  
* Przykładowy obraz Macro PDF417 (np. `ExtPDF417Meta.png`)

Te wymagania zapewniają, że kod się skompiluje i uruchomi bez dodatkowej konfiguracji.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Pierwszy krok w każdym projekcie **read barcode image C#** to dodanie biblioteki kodów kreskowych. Otwórz terminal w folderze rozwiązania i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet udostępnia `BarCodeReader`, `DecodeType` oraz właściwość `Extended` używaną do dostępu do danych makro. Zainstalowanie go raz sprawia, że klasy są dostępne w całym projekcie.

## Krok 2: Utwórz czytnik kodów kreskowych dla obrazu Macro PDF417

Teraz możesz utworzyć instancję `BarCodeReader` z ścieżką do obrazu i określić `DecodeType.MacroPdf417`. To informuje bibliotekę, aby szukała rozszerzonego formatu PDF417 zawierającego informacje makro.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Dlaczego to ważne:**  
`DecodeType.MacroPdf417` aktywuje parser specyficzny dla makro. Jeśli go pominiesz, czytnik zwróci tylko zwykły tekst i zignoruje pola makro, które prawdopodobnie są potrzebne do odtworzenia pliku.

## Krok 3: Odczytaj wszystkie kody kreskowe znalezione na obrazie

Pojedynczy obraz może zawierać wiele symboli PDF417, szczególnie gdy dane są podzielone na segmenty. Pętla `ReadBarCodes()` zapewnia, że przechwycisz każdy segment.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Dlaczego pętla:**  
Dane makro PDF417 często pojawiają się w kilku segmentach. Przetwarzanie każdego `BarCodeResult` zapewnia zebranie pełnego zestawu pól makro, takich jak `MacroPdf417FileID` i `MacroPdf417SegmentsCount`.

## Krok 4: Pobierz i wyświetl podstawowe dane kodu kreskowego

Obiekt `BarCodeResult` zawiera typ oraz zdekodowany tekst. Wyświetlenie tych wartości pomaga zweryfikować, że czytnik poprawnie zidentyfikował symbol, zanim przejdziesz do szczegółów makro.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Wskazówka:** Jeśli `CodeText` jest pusty, obraz może być uszkodzony lub tryb dekodowania jest nieprawidłowy. Sprawdź ponownie użyty `DecodeType` podczas inicjalizacji.

## Krok 5: Wyodrębnij rozszerzone informacje makro PDF417

Dane makro znajdują się pod `barcodeResult.Extended.Pdf417`. Każda właściwość odpowiada polu zdefiniowanemu w specyfikacji PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Co oznacza każde pole**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Identyfikator grupujący wszystkie segmenty należące do tego samego logicznego pliku. |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (licząc od 1). |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów potrzebnych do odtworzenia oryginalnego pliku. |
| `MacroPdf417FileName` | Opcjonalna nazwa pliku osadzona w makro. |
| `MacroPdf417Checksum` | Suma kontrolna CRC‑16 służąca weryfikacji integralności. |
| `MacroPdf417FileSize` | Oczekiwany rozmiar odtworzonego pliku (w bajtach). |
| `MacroPdf417TimeStamp` | Data i godzina wygenerowania makro. |
| `MacroPdf417Addressee` | Opcjonalny identyfikator odbiorcy. |
| `MacroPdf417Sender` | Opcjonalny identyfikator nadawcy. |
| `MacroPdf417Terminator` | Flaga terminatora; powinna być `true` w ostatnim segmencie. |

Zrozumienie tych pól pozwala odtworzyć oryginalny plik, zweryfikować integralność danych i wdrożyć własną logikę biznesową (np. odrzucanie przestarzałych dokumentów).

## Krok 6: Obsłuż wiele segmentów i odbuduj oryginalny plik (zaawansowane)

Gdy `MacroPdf417SegmentsCount` jest większy niż 1, musisz zebrać każdy segment, posortować je według `MacroPdf417SegmentID` i połączyć wartości `CodeText`. Poniżej znajduje się zwięzła implementacja:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Dlaczego to ważne:**  
Bez sortowania i łączenia zdekodowane dane byłyby niekompletne lub zniekształcone. Fragment kodu pokazuje także programowanie defensywne poprzez sprawdzanie liczby segmentów.

## Krok 7: Zakończenie z obsługą błędów i najlepszymi praktykami

Przykład **c# barcode reader example** gotowy do produkcji powinien przewidywać błędy I/O, nieobsługiwane formaty i uszkodzone obrazy.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Lista kontrolna najlepszych praktyk**

* Zweryfikuj ścieżkę obrazu przed utworzeniem `BarCodeReader`.  
* Używaj instrukcji `using`, aby zagwarantować zwolnienie niezarządzanych zasobów.  
* Loguj pola makro dla celów audytu — szczególnie `MacroPdf417Checksum` i `MacroPdf417TimeStamp`.  
* Przy obsłudze dużych plików rozważ strumieniowe zapisywanie połączonego ładunku na dysk zamiast trzymania go w całości w pamięci.

## Oczekiwany wynik

Uruchomienie pełnego programu przeciwko prawidłowemu `ExtPDF417Meta.png` generuje wyjście podobne do:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Jeśli wszystkie trzy segmenty są obecne, blok odbudowy wypisuje pełny ładunek po komunikacie weryfikacyjnym.

## Zakończenie

Teraz wiesz **jak dekodować PDF417** w C# przy użyciu solidnego przykładu czytnika kodów kreskowych. Tutorial obejmował instalację Aspose.BarCode, inicjalizację `BarCodeReader` dla Macro PDF417, iterację po wielu kodach kreskowych, wyodrębnianie pól makro, odbudowę danych segmentowanych oraz obsługę błędów.  

Od tego momentu możesz:

* Zintegrować czytnik z Web API przyjmującym przesłane obrazy.  
* Przechowywać metadane makro w bazie danych w celach audytowych.  
* Rozszerzyć rozwiązanie na inne symbole 2‑D, zamieniając `DecodeType` (e

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}