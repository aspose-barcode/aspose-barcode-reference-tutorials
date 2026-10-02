---
category: general
date: 2026-10-02
description: Dowiedz się, jak odczytywać kod kreskowy z obrazu w C# przy użyciu kompletnego
  przykładu, który pokazuje, jak dekodować kod PDF417 za pomocą Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: pl
lastmod: 2026-10-02
og_description: Odczytaj kod kreskowy z obrazu w C# przy użyciu Aspose.BarCode. Ten
  samouczek wyjaśnia, jak zdekodować kod PDF417 i wyodrębnić rozszerzone metadane.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Odczytaj kod kreskowy z obrazu w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak odczytać kod kreskowy z obrazu w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy z obrazu c# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **odczytać kod kreskowy z obrazu c#**, ten przewodnik przeprowadzi Cię przez kompletną, gotową do uruchomienia rozwiązanie. Nauczysz się, jak dekodować kod kreskowy PDF417, uzyskać dostęp do jego rozszerzonych danych makro i wydrukować wyniki w konsoli.

Odczytywanie kodów kreskowych z obrazów jest powszechnym wymogiem w systemach inwentaryzacji, weryfikacji biletów i przetwarzaniu dokumentów. Ten tutorial obejmuje wszystko, czego potrzebujesz: wymagane pakiety, wyjaśnienie kodu, obsługę przypadków brzegowych oraz oczekiwany wynik. Nie wymaga dodatkowej dokumentacji; przykład działa od razu z Aspose.BarCode .NET.

## Prerequisites

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE C#)  
* Odwołanie NuGet do **Aspose.BarCode** (wersja 23.10 lub nowsza)  
* Plik obrazu zawierający kod kreskowy PDF417 – na przykład `ExtPDF417Meta.png`

Jeśli którekolwiek z tych elementów brakuje, zainstaluj .NET SDK, dodaj pakiet NuGet poleceniem `dotnet add package Aspose.BarCode` i umieść obraz w folderze, do którego możesz odwołać się w swoim projekcie.

## Jak odczytać kod kreskowy z obrazu c# – krok po kroku

Poniższe sekcje dzielą implementację na logiczne kroki. Każdy krok zawiera fragment kodu, wyjaśnienie **dlaczego** krok jest ważny oraz wskazówkę, którą możesz zastosować w rzeczywistych projektach.

### Krok 1: Utwórz `BarCodeReader` dla obrazu PDF417

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Why this matters** – Konstruktor `BarCodeReader` przyjmuje ścieżkę do obrazu oraz oczekiwany typ kodu kreskowego. Określenie `MacroPdf417` zawęża wyszukiwanie, co poprawia wydajność i zmniejsza liczbę fałszywych trafień, gdy obraz zawiera wiele symbologii.

**Pro tip:** Jeśli nie jesteś pewien typu kodu kreskowego, użyj `DecodeType.AllSupportedTypes` i przefiltruj wyniki później.

### Krok 2: Iteruj po wszystkich wykrytych kodach kreskowych

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Why this matters** – Obraz makro PDF417 może zawierać kilka segmentów. Metoda `ReadBarCodes()` zwraca kolekcję, umożliwiając przetworzenie każdego segmentu osobno.

**Edge case:** Jeśli obraz nie zawiera żadnych symboli PDF417, kolekcja jest pusta i ciało pętli nigdy się nie wykona. Rozważ dodanie sprawdzenia po pętli, aby poinformować użytkownika.

### Krok 3: Uzyskaj dostęp do rozszerzonych metadanych makro PDF417

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Why this matters** – Właściwość `Extended.Pdf417` udostępnia pola zdefiniowane w specyfikacji PDF417, takie jak identyfikator pliku, identyfikator segmentu i nazwa pliku. Dane te są niezbędne, gdy musisz odtworzyć dokument wielostronicowy z oddzielnych skanów kodów kreskowych.

**Pro tip:** Zawsze sprawdzaj, czy `barcodeResult.Extended` nie jest nullem przed dostępem do `Pdf417`. Biblioteka zwraca `null` dla symbologii, które nie obsługują danych rozszerzonych.

### Krok 4: Wyświetl tekst kodu kreskowego i szczegóły makro

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Why this matters** – Wyjście w konsoli daje natychmiastowy wgląd zarówno w zdekodowany tekst, jak i metadane makro. Jest to przydatne przy debugowaniu oraz dalszym przetwarzaniu, np. przechowywaniu informacji w bazie danych.

**Expected output** (zakładając, że przykładowy obraz zawiera jeden segment makro):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Jeśli obraz zawiera trzy segmenty, pętla wydrukuje trzy bloki, każdy z innym `Segment ID`.

### Krok 5: Obsłuż błędy i zwolnij zasoby

Instrukcja `using` automatycznie zwalnia zasoby `BarCodeReader`. Jednak nadal powinieneś przechwytywać wyjątki, które mogą wystąpić przy brakujących plikach lub nieobsługiwanych formatach:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Why this matters** – Solidne aplikacje nigdy nie zawieszają się z powodu brakującego pliku lub uszkodzonego obrazu. Dostarczenie jasnego komunikatu o błędzie pomaga Tobie lub Twojemu zespołowi wsparcia szybko zdiagnozować problem.

## Jak dekodować kod kreskowy PDF417 przy użyciu Aspose.BarCode

Drugorzędne słowo kluczowe **how to decode pdf417 barcode** pojawia się naturalnie w tej sekcji. Dekodowanie kodu PDF417 podąża tym samym schematem, co powyżej, ale możesz pominąć flagę `MacroPdf417`, jeśli potrzebujesz jedynie zwykłego tekstu:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Why you might choose this variant** – Gdy kod kreskowy nie zawiera informacji makro, użycie `DecodeType.Pdf417` zmniejsza obciążenie przetwarzania i upraszcza obsługę wyniku.

**Common question:** *What if the barcode is rotated?*  
Aspose.BarCode automatycznie wykrywa obrót i koryguje go, więc nie potrzebujesz dodatkowego kodu do wstępnego przetwarzania obrazu.

## Pełny, gotowy do uruchomienia przykład

Skopiuj cały program poniżej do nowego projektu konsolowego (`dotnet new console`) i zamień `YOUR_DIRECTORY/ExtPDF417Meta.png` na rzeczywistą ścieżkę do swojego obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Uruchomienie programu wypisuje typ kodu kreskowego, zdekodowany tekst oraz ewentualne metadane makro. Jeśli obraz nie zawiera makro PDF417, program poinformuje Cię w sposób elegancki.

## Zakończenie

Teraz wiesz, jak **odczytać kod kreskowy z obrazu c#** przy użyciu Aspose.BarCode, jak **dekodować kod kreskowy PDF417** oraz jak wyodrębnić rozszerzone pola makro‑PDF417. Rozwiązanie obejmuje inicjalizację, iterację, dostęp do metadanych, obsługę błędów oraz wariant dla zwykłego dekodowania PDF417.

Od tego momentu możesz:

* Przechowywać wyodrębnione dane w bazie danych SQL do późniejszego odczytu.  
* Połączyć wiele segmentów, aby odtworzyć oryginalny dokument.  
* Odkrywać inne symbologie obsługiwane przez Aspose.BarCode, takie

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i eksplorować alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać PDF417 w C# – Kompletny przykład kodu kreskowego](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Jak odczytać PDF417 w C# – Kompletny przykład czytnika kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Jak wygenerować obraz kodu kreskowego PDF417 w C# przy użyciu Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}