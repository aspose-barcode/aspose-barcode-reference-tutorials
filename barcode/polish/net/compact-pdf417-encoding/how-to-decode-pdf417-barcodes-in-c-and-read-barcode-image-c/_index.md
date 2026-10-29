---
category: general
date: 2026-10-28
description: Jak szybko dekodować kody kreskowe PDF417 w C#. Naucz się odczytywać
  obraz kodu kreskowego w C# przy użyciu Aspose.BarCode, z kompletnym, działającym
  przykładem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: pl
lastmod: 2026-10-28
og_description: Jak dekodować kody kreskowe PDF417 w C# za pomocą Aspose.BarCode.
  Ten przewodnik pokazuje, jak odczytać obraz kodu kreskowego w C# krok po kroku,
  wraz z kodem.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Jak dekodować kody PDF417 w C# – tutorial odczytu obrazu kodu kreskowego
  w C#
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Jak dekodować kody PDF417 w C# i odczytywać obraz kodu kreskowego w C#
url: /pl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekodować kody kreskowe PDF417 w C# i odczytywać obraz kodu kreskowego C#

Jeśli potrzebujesz **how to decode pdf417** w aplikacji .NET, ten przewodnik daje gotowe rozwiązanie. Zobaczysz dokładnie, jak **read barcode image c#** przy użyciu biblioteki Aspose.BarCode, wyodrębnić pola macro‑PDF417 i wyświetlić je w konsoli.

Dekodowanie kodów kreskowych PDF417 często pojawia się w systemach logistycznych, biletowych i weryfikacji tożsamości. Po zakończeniu tego samouczka będziesz w stanie wczytać dowolny obraz zawierający kod Macro PDF417, zdekodować go i uzyskać wartości file ID, segment ID oraz segment count, które są niezbędne do składania dokumentów wielosegmentowych.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE C#)  
* Pakiet NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  
* Plik obrazu zawierający kod Macro PDF417 (przykład używa `ExtPDF417Meta.png`)

Możesz dodać pakiet NuGet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy i zaimportuj wymagane przestrzenie nazw. Dyrektywy `using` dają dostęp do `BarCodeReader`, `DecodeType` oraz obiektów rozszerzeń wyniku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Dlaczego ten krok ma znaczenie** – Importowanie właściwych przestrzeni nazw zapobiega błędom kompilacji i udostępnia interfejs API potrzebny do dalszej logiki dekodowania.

## Krok 2: Określ ścieżkę do obrazu

Zdefiniuj pełną lub względną ścieżkę do obrazu kodu kreskowego. Przechowywanie ścieżki w zmiennej sprawia, że kod jest wielokrotnego użytku dla różnych obrazów.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Wskazówka:** Użyj `Path.Combine`, jeśli budujesz ścieżkę z wielu części; obsługuje separatory katalogów w różnych systemach operacyjnych.

## Krok 3: Utwórz `BarCodeReader` skonfigurowany do dekodowania Macro PDF417

Zainicjuj `BarCodeReader` z ścieżką do obrazu i flagą `DecodeType.MacroPdf417`. To informuje bibliotekę, aby szukała konkretnie symboli Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Dlaczego ten krok ma znaczenie** – Wybranie odpowiedniego `DecodeType` zwiększa wydajność, ponieważ silnik pomija niepowiązane formaty kodów kreskowych.

## Krok 4: Odczytaj wszystkie kody kreskowe i wyświetl informacje macro

Iteruj po każdym `BarCodeResult` zwróconym przez `reader.ReadBarCodes()`. Obiekt wyniku zawiera zarówno pola generyczne (`CodeTypeName`, `CodeText`), jak i specyficzne rozszerzenia Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Co robi każda linia

| Linia | Wyjaśnienie |
|------|-------------|
| `result.CodeTypeName` | Czytelna dla człowieka nazwa wykrytego typu kodu kreskowego (np. “MacroPdf417”). |
| `result.CodeText` | Surowe dane zakodowane w kodzie kreskowym. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identyfikator łączący wszystkie segmenty dokumentu macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Indeks bieżącego segmentu w całym dokumencie. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Łączna liczba segmentów oczekiwanych w dokumencie. |

> **Pro tip:** Przechowuj pola macro w bazie danych, jeśli później potrzebujesz złożyć pełny dokument. `File ID` pozwala grupować segmenty pochodzące z tego samego źródła.

## Krok 5: Uruchom program i zweryfikuj wynik

Zbuduj i uruchom aplikację konsolową:

```bash
dotnet run
```

Typowy wynik w konsoli wygląda następująco:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Jeśli obraz zawiera wiele symboli Macro PDF417, pętla wypisuje każdy z nich kolejno.

### Obsługa typowych przypadków brzegowych

| Sytuacja | Zalecane postępowanie |
|-----------|----------------------|
| **Nie znaleziono kodu kreskowego** | Sprawdź `reader.ReadBarCodes().Any()` przed pętlą i wyświetl przyjazny komunikat. |
| **Uszkodzony obraz** | Umieść tworzenie `BarCodeReader` w bloku `try/catch` obsługującym `BarCodeException`. |
| **Wiele formatów kodów kreskowych** | Użyj `DecodeType.AllSupported` i przefiltruj wyniki, sprawdzając `result.CodeTypeName == "MacroPdf417"`. |
| **Duże obrazy** | Zmniejsz rozmiar obrazu przed dekodowaniem, aby poprawić wydajność; biblioteka akceptuje obiekt `Bitmap`. |

## Pełny kod źródłowy

Poniżej znajduje się kompletny, samodzielny program. Skopiuj go do `Program.cs` nowego projektu konsolowego i zamień `YOUR_DIRECTORY/ExtPDF417Meta.png` na rzeczywistą ścieżkę do swojego obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Zakończenie

Teraz wiesz, **how to decode pdf417** kody kreskowe w C# oraz **read barcode image c#** przy użyciu Aspose.BarCode. Samouczek przeprowadził Cię przez konfigurację projektu, wczytywanie obrazu, konfigurację czytnika, wyodrębnianie wyników i obsługę przypadków brzegowych. Dzięki tej bazie możesz zintegrować dekodowanie PDF417 w systemach inwentaryzacji, walidatorach biletów lub dowolnym procesie, który korzysta z danych macro‑zakodowanych.

### Kolejne kroki

* Zbadaj inne formaty kodów kreskowych, zmieniając `DecodeType` (np. `DecodeType.QR`, `DecodeType.Code128`).  
* Połącz wiele zdekodowanych segmentów, aby odtworzyć oryginalny dokument.  
* Użyj klasy `BarCodeGenerator`, aby w locie tworzyć testowe kody PDF417.  

Śmiało eksperymentuj z różnymi źródłami obrazów, dostosowuj wyjście konsoli lub osadź logikę dekodowania w API webowym do przetwarzania w czasie rzeczywistym. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera pełne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak dekodować PDF417 w C# z przykładem czytnika kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Jak generować kody PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [Jak odczytać kod kreskowy z obrazu c# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}