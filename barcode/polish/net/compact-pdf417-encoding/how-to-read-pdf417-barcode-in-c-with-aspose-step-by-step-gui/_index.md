---
category: general
date: 2026-10-24
description: Dowiedz się, jak odczytywać kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Ten tutorial obejmuje odczyt obrazu kodu kreskowego, wyodrębnianie pól Macro PDF417
  oraz obsługę typowych scenariuszy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: pl
lastmod: 2026-10-24
og_description: Jak odczytać kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Przejdź przez ten kompletny samouczek, aby dekodować obrazy, pobierać metadane Macro
  PDF417 i unikać typowych pułapek.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Jak odczytać kod kreskowy PDF417 w C# z Aspose – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Jak odczytać kod kreskowy PDF417 w C# z użyciem Aspose – przewodnik krok po
  kroku
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy PDF417 w C# przy użyciu Aspose – przewodnik krok po kroku

Jeśli potrzebujesz **jak odczytać kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak odczytać kod PDF417 w C# przy użyciu biblioteki Aspose.BarCode. Niezależnie od tego, czy przetwarzasz zeskanowane dokumenty, zdjęcia mobilne czy obrazy importowane partiami, poniższy kod dekoduje kod kreskowy i wyodrębnia wszystkie właściwości Macro PDF417, które mogą być potrzebne.

Odczytywanie obrazu kodu kreskowego w C# może wydawać się trudne, szczególnie gdy kod zawiera rozszerzone metadane. Ten tutorial eliminuje zgadywanie, dostarczając kompletny, gotowy do uruchomienia przykład, wyjaśniając każdą linię i omawiając przypadki brzegowe, takie jak brakujące segmenty makro lub uszkodzone obrazy. Po zakończeniu będziesz w stanie zintegrować dekodowanie PDF417 w dowolnym projekcie C# z pewnością siebie.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)  
* Licencję lub darmową wersję próbną **Aspose.BarCode for .NET** – tymczasowy klucz możesz uzyskać na stronie Aspose  
* Plik obrazu zawierający kod Macro PDF417 (np. `ExtPDF417Meta.png`)

> **Wskazówka:** Jeśli chcesz tylko poeksperymentować, Aspose oferuje 30‑dniowy trial, który zawiera pełną funkcjonalność odczytu kodów kreskowych.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz folder projektu w terminalu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode.ReadRecognition`, w której znajduje się klasa `BarCodeReader` używana do dekodowania obrazów.

## Krok 2: Utwórz BarCodeReader dla obrazu PDF417

Konstruktor `BarCodeReader` przyjmuje dwa argumenty: ścieżkę do pliku obrazu oraz `DecodeType`, który chcesz użyć. Określenie `DecodeType.MacroPdf417` informuje Aspose, aby szukał symboli Macro PDF417 i automatycznie wypełniał rozszerzone właściwości.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Dlaczego używać `DecodeType.MacroPdf417`?

* **Macro PDF417** przechowuje dodatkowe pola (identyfikator pliku, liczbę segmentów, znaczniki czasu itp.), które nie występują w standardowym PDF417.  
* Właściwość `Extended` obiektu `BarCodeResult` jest wypełniana tylko wtedy, gdy żądasz typu makro, co eliminuje potrzebę osobnego kroku parsowania.

## Krok 3: Przejdź przez wszystkie wykryte kody kreskowe

Jedno zdjęcie może zawierać wiele symboli PDF417 (np. gdy dokument jest podzielony na kilka stron). Metoda `ReadBarCodes()` zwraca `IEnumerable<BarCodeResult>`, po którym możesz iterować.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Jeśli obraz nie zawiera żadnego kodu kreskowego, pętla po prostu się nie wykona, a program zakończy się łagodnie. Takie zachowanie sprawia, że kod jest bezpieczny w przetwarzaniu wsadowym, gdzie niektóre pliki mogą nie mieć kodu kreskowego.

## Krok 4: Wyświetl rozszerzone właściwości Macro PDF417

Właściwość `Extended.Pdf417` grupuje wszystkie pola specyficzne dla makro. Każde pole mapuje się bezpośrednio na specyfikację PDF417, więc możesz je zapisać w bazie danych, zalogować lub użyć do dalszej walidacji.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Co oznacza każda właściwość

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | Unikalny identyfikator całego dokumentu wielosegmentowego. |
| **MacroPdf417SegmentID** | Indeks bieżącego segmentu (liczony od 0). |
| **MacroPdf417SegmentsCount** | Łączna liczba segmentów należących do pliku. |
| **MacroPdf417FileName** | Opcjonalna nazwa pliku osadzona w kodzie kreskowym. |
| **MacroPdf417Checksum** | Suma kontrolna CRC‑16 dla bloku danych makro. |
| **MacroPdf417FileSize** | Oryginalny rozmiar pliku w bajtach. |
| **MacroPdf417TimeStamp** | Znacznik czasu, kiedy wygenerowano kod makro. |
| **MacroPdf417Addressee** | Odbiorca dokumentu. |
| **MacroPdf417Sender** | Nadawca dokumentu. |
| **MacroPdf417Terminator** | Flaga terminatora wskazująca koniec sekwencji makro. |

Te pola są szczególnie przydatne przy odtwarzaniu dużego PDF lub obrazu, który został podzielony na kilka symboli PDF417 w celu druku na nośnikach o niskiej rozdzielczości.

## Krok 5: Obsługa typowych przypadków brzegowych

### Brakujące pola makro

Czasami kod PDF417 jest generowany bez opcjonalnych pól makro. Dostęp do nieistniejącej właściwości zwraca `null` lub `0`. Zabezpiecz się przed tym, jeśli planujesz przechowywać wartości:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Uszkodzone lub niskiej jakości obrazy

Jeśli obraz jest rozmyty, możesz poprawić wykrywanie, włączając opcje jakości `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Ustawienia te są opcjonalne, ale mogą dramatycznie zwiększyć skuteczność w przypadku zeskanowanych dokumentów.

### Wiele formatów kodów kreskowych na jednym obrazie

Jeśli podejrzewasz, że mogą występować inne typy kodów, użyj `DecodeType.AllSupported` i przefiltruj wyniki:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Kompletny, działający przykład

Skopiuj poniższy program do nowego projektu konsolowego (`dotnet new console`) i uruchom go. Zamień zmienną `imagePath` na ścieżkę do własnego obrazu Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Oczekiwany wynik** (wartości będą się różnić w zależności od obrazu):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Jeśli obraz nie zawiera symboli Macro PDF417, program nic nie wypisze i zakończy się cicho — idealne rozwiązanie dla zadań wsadowych przetwarzających wiele plików.

## Najczęściej zadawane pytania

**Q: Czy mogę odczytać standardowy PDF417 (bez makro) tym samym kodem?**  
A: Tak. Zmien `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Właściwość `Extended` będzie pusta, ale `CodeText` i `CodeTypeName` pozostaną dostępne.

**Q: Czy Aspose.BarCode obsługuje odczyt z strumienia zamiast ścieżki pliku?**  
A: Oczywiście. Użyj przeciążenia `new BarCodeReader(Stream, DecodeType)` i przekaż `FileStream` lub `MemoryStream`. Jest to przydatne, gdy obraz pochodzi z API internetowego.

**Q: Jak zweryfikować sumę kontrolną?**  
A: Pole `MacroPdf417Checksum` zawiera surową wartość CRC‑16. Możesz ponownie obliczyć sumę kontrolną na odtworzonym pliku i porównać ją, aby zapewnić integralność danych.

## Kolejne kroki i powiązane tematy

* **Write PDF417 barcodes** – explore `BarCodeGenerator` to create macro barcodes for testing.  
* **Combine multiple segments** – after reading all segments, order them by `MacroPdf417SegmentID` and concatenate `CodeText` to reconstruct the original payload.  
* **Performance tuning** – for high‑throughput scenarios, reuse a single `BarCodeReader` instance across many images and


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}