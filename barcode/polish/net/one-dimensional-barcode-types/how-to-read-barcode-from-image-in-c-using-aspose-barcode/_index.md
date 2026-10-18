---
category: general
date: 2026-10-18
description: Dowiedz się, jak odczytać kod kreskowy z obrazu w C# przy użyciu Aspose.BarCode,
  obejmując wyodrębnianie metadanych Macro PDF417 oraz kompletny kod przykładowy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: pl
lastmod: 2026-10-18
og_description: Jak odczytać kod kreskowy z obrazu przy użyciu C# Aspose.BarCode.
  Skorzystaj z tego samouczka krok po kroku, aby wyodrębnić metadane Macro PDF417
  i obsłużyć typowe scenariusze.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Jak odczytać kod kreskowy z obrazu w C# – kompletny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak odczytać kod kreskowy z obrazu w C# przy użyciu Aspose.BarCode
url: /pl/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy z obrazu w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **jak odczytać kod kreskowy z obrazu** w aplikacji .NET, ten przewodnik pokazuje dokładne kroki z Aspose.BarCode. Niezależnie od tego, czy przetwarzasz zeskanowane dokumenty, paragony czy etykiety inwentaryzacyjne, zobaczysz, jak odczytać kod kreskowy, pobrać metadane Macro PDF417 i obsłużyć typowe przypadki brzegowe.

Odczytanie kodu kreskowego z obrazu to rutynowe zadanie, ale wyodrębnienie rozszerzonych pól Macro PDF417 dodaje warstwę złożoności. Ten samouczek obejmuje kompletny przepływ pracy, od konfiguracji projektu po w pełni działający przykład, abyś mógł skopiować‑wkleić kod i od razu zobaczyć wyniki.

## Co się nauczysz

- Jak skonfigurować Aspose.BarCode dla projektów C#.
- Poprawny sposób tworzenia **C# barcode reader** dla obrazu Macro PDF417.
- Jak iterować po każdym wykrytym kodzie kreskowym i wyświetlać podstawowe informacje.
- Jak uzyskać dostęp do **Macro PDF417 metadata** takich jak file ID, segment ID i checksum.
- Wskazówki dotyczące obsługi brakujących metadanych, dużych obrazów i typowych błędów dekodowania.

## Wymagania wstępne

- .NET 6.0 (lub nowszy) zainstalowany.  
- Podstawowa znajomość C# i Visual Studio (dowolne IDE działa).  
- Plik obrazu zawierający kod kreskowy Macro PDF417 (np. `ExtPDF417Meta.png`).  

## Krok 1: Zainstaluj Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet zawiera **BarCodeReader class**, który implementuje funkcjonalność **C# barcode reader** potrzebną w tym samouczku.

## Krok 2: Skonfiguruj środowisko programistyczne

Utwórz nową aplikację konsolową, jeśli jeszcze jej nie masz:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Dodaj dyrektywy `using` na początku pliku `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Te przestrzenie nazw udostępniają **BarCodeReader class** oraz wyliczenie `DecodeType` wymagane do dekodowania Macro PDF417.

## Krok 3: Zainicjalizuj BarCodeReader dla Macro PDF417

Rdzeniem **jak odczytać kod kreskowy z obrazu** jest stworzenie instancji `BarCodeReader`, która celuje w konkretny `DecodeType`. Dla Macro PDF417 musisz przekazać `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Dlaczego to jest ważne:**  
Wybranie `DecodeType.MacroPdf417` informuje bibliotekę, że ma szukać rozszerzonego formatu Macro PDF417, który zawiera dodatkowe pola poza podstawowymi danymi kodu kreskowego. Jeśli użyjesz ogólnego `DecodeType.Pdf417`, te dodatkowe pola zostaną zignorowane.

## Krok 4: Iteruj po wykrytych kodach kreskowych

Jedno zdjęcie może zawierać wiele kodów kreskowych. Metoda `ReadBarCodes()` zwraca kolekcję `BarCodeResult`. Przejdź przez nią, aby wypisać podstawowe informacje o każdym kodzie:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` podaje dokładną symbologię kodu (np. „MacroPdf417”), natomiast `CodeText` zawiera odkodowany ciąg znaków.

## Krok 5: Wyodrębnij i wyświetl metadane Macro PDF417

Gdy kod jest typu Macro PDF417, właściwość `Extended.Pdf417` dostarcza bogaty zestaw pól metadanych. Uzyskaj do nich dostęp bezpośrednio, jak pokazano poniżej:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Te pola dają wszystko, co potrzebne do odtworzenia oryginalnego pliku wieloczęściowego, weryfikacji integralności oraz powiązania kodu z konkretnym dokumentem lub nadawcą.

### Oczekiwany wynik w konsoli

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Jeśli obraz nie zawiera kodu Macro PDF417, obiekt `Extended.Pdf417` będzie równy `null`. Zabezpiecz się przed tym, aby uniknąć `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Krok 6: Obsługa typowych błędów i przypadków brzegowych

### Duże obrazy

Odczyt bardzo dużych obrazów może zużywać znaczną ilość pamięci. Użyj przeciążenia `BarcodeReader`, które przyjmuje `ReaderParameters`, aby ograniczyć maksymalny rozmiar obrazu:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Brakujące lub uszkodzone metadane

Jeśli którekolwiek z pól Macro jest brakujące, odpowiadająca właściwość zwróci `null` lub `0`. Zaloguj te przypadki i zdecyduj, czy traktować kod jako niekompletny.

### Wiele typów kodów kreskowych na jednym obrazie

Jeśli obraz może zawierać inne formaty kodów, możesz przekazać tablicę wartości `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

To podejście utrzymuje logikę **jak odczytać kod kreskowy z obrazu** elastyczną, nie poświęcając wydajności.

## Krok 7: Pełny kod źródłowy

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Zastąp `YOUR_DIRECTORY/ExtPDF417Meta.png` ścieżką do własnego obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Uruchom program poleceniem:

```bash
dotnet run
```

Powinieneś zobaczyć typ kodu kreskowego, odkodowany tekst oraz wszystkie dostępne pola Macro PDF417 wypisane w konsoli.

## Zakończenie

W tym samouczku nauczyłeś się **jak odczytać kod kreskowy z obrazu** przy użyciu Aspose.BarCode dla C#. Poradnik obejmował konfigurację **C# barcode reader**,

## Co powinieneś nauczyć się dalej?

Poniższe samouczki dotyczą ściśle powiązanych tematów, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Odczytaj kod kreskowy z obrazu C# – kompletny przewodnik z Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak utworzyć kod kreskowy macro PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak odczytać kod kreskowy PDF417 w C# – kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}