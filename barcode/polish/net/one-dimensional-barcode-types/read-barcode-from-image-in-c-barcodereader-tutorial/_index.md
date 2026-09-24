---
category: general
date: 2026-08-15
description: Odczytaj kod kreskowy z obrazu w C# przy użyciu BarCodeReader. Dowiedz
  się, jak odczytywać wiele kodów kreskowych w C#, odczytywać kod PDF417 oraz zobacz
  pełny przykład BarCodeReader w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: pl
lastmod: 2026-08-15
og_description: Odczytaj kod kreskowy z obrazu w C# dzięki przewodnikowi krok po kroku.
  Dowiedz się, jak odczytywać wiele kodów kreskowych w C#, dekodować symbole PDF417
  i uruchomić kompletny przykład C# BarCodeReader.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Odczytaj kod kreskowy z obrazu w C# – samouczek BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Odczyt kodu kreskowego z obrazu w C# – samouczek BarCodeReader
url: /pl/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt kodu kreskowego z obrazu w C# – samouczek BarCodeReader

Jeśli potrzebujesz **odczytać kod kreskowy z obrazu** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić przy użyciu klasy `BarCodeReader`. Zobaczysz także, jak **odczytać wiele kodów kreskowych w C#**, zdekodować symbol PDF417 oraz uzyskać kompletny **przykład C# BarCodeReader**, który możesz skopiować do swojego projektu.

Samouczek obejmuje każdy krok — od dodania wymaganego pakietu NuGet po wypisanie rozszerzonych pól PDF417 — tak abyś zakończył z działającym programem konsolowym. Nie potrzebna jest żadna zewnętrzna dokumentacja; cały kod i wyjaśnienia są zawarte.

## Czego będziesz potrzebować

* .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
* Visual Studio 2022 lub dowolny edytor kompatybilny z C#
* Pakiet NuGet `Aspose.BarCode` (lub równoważna biblioteka udostępniająca `BarCodeReader`)
* Plik obrazu zawierający kod kreskowy Macro PDF417 (np. `ExtPDF417Meta.png`)

Posiadanie tych wymagań zapewnia, że przykładowy kod skompiluje się bez dodatkowej konfiguracji.

## Odczyt kodu kreskowego z obrazu przy użyciu BarCodeReader

Pierwszym krokiem jest utworzenie instancji `BarCodeReader`, która wskazuje plik obrazu i informuje bibliotekę, jakiego typu kodu kreskowego szukać.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Dlaczego to działa:**  
`BarCodeReader` otwiera obraz, skanuje pod kątem określonego `DecodeType` i zwraca kolekcję obiektów `BarCodeResult`. Każdy wynik zawiera ogólne dane kodu kreskowego (`CodeTypeName`, `CodeText`) oraz, w przypadku Macro PDF417, obiekt `Extended.Pdf417`, który udostępnia wszystkie dodatkowe pola zdefiniowane w standardzie.

## Odczyt wielu kodów kreskowych w C# na jednym obrazie

Czasami obraz zawiera więcej niż jeden kod kreskowy (np. kod QR obok PDF417). Aby obsłużyć taką sytuację, po prostu pomiń explicite `DecodeType` lub przekaż `DecodeType.AllSupported` i iteruj po wynikach.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Dlaczego tego potrzebujesz:**  
Określenie `AllSupported` instruuje silnik, aby wypróbował każdy znany format kodu kreskowego, co gwarantuje przechwycenie każdego symbolu na obrazie. Jest to zalecane podejście, gdy nie możesz wcześniej przewidzieć typów kodów kreskowych.

## Jak odczytać kod PDF417 przy użyciu C#

Jeśli interesuje Cię tylko klasyczny format PDF417 (bez makra), zmień `DecodeType` na `Pdf417`. Reszta kodu pozostaje identyczna, z wyjątkiem braku dostępnych pól rozszerzonych.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Dlaczego to ma znaczenie:**  
Klasyczny PDF417 nie udostępnia właściwości specyficznych dla makra, więc blok `Extended.Pdf417` jest niepotrzebny. Użycie precyzyjnego `DecodeType` przyspiesza skanowanie, ponieważ biblioteka pomija nieobsługiwane algorytmy.

## Pełny przykład C# BarCodeReader, który możesz skopiować

Poniżej znajduje się kompletny program, który łączy trzy scenariusze w jedną, łatwą do uruchomienia aplikację konsolową. Zamień `YOUR_DIRECTORY/ExtPDF417Meta.png` na rzeczywistą ścieżkę do swojego obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Oczekiwany wynik

Gdy przykładowy obraz zawiera kod Macro PDF417, konsola wypisuje coś podobnego do:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Jeśli obraz zawiera tylko zwykły PDF417, sekcja „Macro PDF417” będzie pusta, a sekcja „Classic PDF417” wyświetli zdekodowany tekst.

## Podsumowanie

Teraz wiesz, jak **odczytać kod kreskowy z obrazu** w C# przy użyciu `BarCodeReader`, jak **odczytać wiele kodów kreskowych w C#** w jednym pliku oraz jakie są dokładne kroki, aby **odczytać kod PDF417** — zarówno w wersji makro, jak i klasycznej. Pełny **przykład C# BarCodeReader** jest gotowy do wklejenia w dowolnym projekcie .NET i możesz go rozbudować, aby obsługiwał inne formaty lub zintegrować z większym potokiem przetwarzania obrazu.

**Kolejne kroki**

* Zbadaj wzorce obsługi błędów, takie jak `try / catch` wokół bloku czytnika.  
* Eksperymentuj z obiektem `ReaderParameters`, aby dostroić szybkość i dokładność wykrywania.  
* Połącz odczyt kodów kreskowych z bibliotekami przetwarzania obrazu (

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Odczyt kodu DataMatrix w C# – Generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Odczyt kodu kreskowego z obrazu – Opanowanie wyodrębniania regionu kodu kreskowego w Javie z Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}