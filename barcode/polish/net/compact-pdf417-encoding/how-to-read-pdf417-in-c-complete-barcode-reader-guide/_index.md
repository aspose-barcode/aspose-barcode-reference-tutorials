---
category: general
date: 2026-08-09
description: Jak odczytać PDF417 w C# przy użyciu BarCodeReader. Dowiedz się, jak
  odczytywać pliki PNG z kodami kreskowymi, obsługiwać wiele kodów kreskowych i wyodrębniać
  rozszerzone metadane.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: pl
lastmod: 2026-08-09
og_description: Jak odczytać PDF417 w C# przy użyciu Aspose.BarCode. Ten samouczek
  pokazuje, jak odczytywać pliki PNG z kodami kreskowymi, przetwarzać wiele kodów
  kreskowych na jednym obrazie oraz pobierać rozszerzone metadane PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Jak odczytać PDF417 w C# – samouczek czytnika kodów kreskowych
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak odczytać PDF417 w C# – kompletny przewodnik po czytniku kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać PDF417 w C# – kompletny przewodnik po czytniku kodów kreskowych

Jeśli potrzebujesz **jak odczytać PDF417** w aplikacji .NET, ten przewodnik zapewnia gotowe do uruchomienia rozwiązanie. Zobaczysz, jak odczytać PNG z kodem kreskowym, przetworzyć kilka kodów w tym samym obrazie oraz wyciągnąć rozszerzone pola PDF417, które wiele skanerów ukrywa.

Odczytywanie kodów PDF417 jest powszechne w logistyce, biletowaniu i zarządzaniu dokumentami. Po zakończeniu tego samouczka będziesz mógł zdekodować obraz Macro PDF417, wyświetlić każdy wynik i wykorzystać dodatkowe informacje (identyfikator pliku, liczba segmentów, znaczniki czasu itp.) w swojej logice biznesowej.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 lub dowolne IDE C#
- **Aspose.BarCode for .NET** (bezpłatna wersja próbna lub licencjonowany pakiet NuGet)
- Obraz PNG zawierający kod Macro PDF417 (przykładowy plik nosi nazwę `ExtPDF417Meta.png`)

> **Wskazówka:** Zainstaluj bibliotekę za pomocą konsoli NuGet:  
> `dotnet add package Aspose.BarCode`

## Jak odczytać PDF417 za pomocą BarCodeReader w C#

Głównym elementem rozwiązania jest klasa `BarCodeReader`. Przyjmuje ona ścieżkę do obrazu oraz wyliczenie `DecodeType`, które informuje silnik, jaką symbologię ma szukać.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Dlaczego to działa

- **`DecodeType.MacroPdf417`** informuje czytnik, aby szukał wariantu Macro PDF417, który przechowuje dodatkowe pola widoczne w kroku 4.
- Blok `using` automatycznie zwalnia czytnik, uwalniając uchwyty plików.
- `ReadBarCodes()` zwraca **wszystkie** kody kreskowe pasujące do żądanego typu, co spełnia wymóg *odczytu wielu kodów kreskowych* nawet jeśli obraz zawiera tylko jeden.

Uruchomienie programu wypisuje wynik podobny do:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Używanie czytnika kodów kreskowych w C# do odczytu wielu kodów

Jeśli obraz zawiera kilka symboli Macro PDF417 (na przykład zeskanowaną stronę z partią biletów), ta sama pętla `foreach` przetwarza każdy z nich. Nie jest wymagany dodatkowy kod; czytnik wewnętrznie agreguje wyniki.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Częste pułapki

- **Format obrazu:** Czytnik obsługuje PNG, JPEG, BMP i TIFF. Jeśli spróbujesz użyć formatu, którego nie potrafi zdekodować, otrzymasz pustą kolekcję. Dlatego w samouczku podkreślono *odczyt kodu kreskowego PNG*.
- **Rozdzielczość:** Obrazy o niskiej rozdzielczości (< 300 dpi) mogą powodować pominięcie segmentów. Zwiększ rozmiar lub poproś o skan o wyższej jakości, gdy to możliwe.
- **Flaga Macro:** Zapomnienie o `DecodeType.MacroPdf417` ogranicza silnik do zwykłego PDF417 i odrzuca rozszerzone dane. Zawsze określaj typ macro, gdy potrzebujesz pól *odczytu rozszerzonych kodów kreskowych*.

## Odczytywanie plików PNG z kodami kreskowymi – najlepsze praktyki

Praca z plikami PNG jest prosta, ponieważ format zachowuje bezstratne dane pikseli. Oto szybka lista kontrolna:

1. Sprawdź, czy plik istnieje przed utworzeniem czytnika.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Używaj `Image.FromFile` tylko wtedy, gdy potrzebujesz wstępnej obróbki (obrót, przycięcie). `BarCodeReader` może otworzyć plik bezpośrednio, co unika dodatkowej alokacji pamięci.
3. Jeśli PNG zawiera przezroczystość, czytnik nadal działa, ponieważ kod kreskowy jest renderowany na nieprzezroczystych pikselach.

## Dostęp do rozszerzonych metadanych PDF417

Obiekt `Extended.Pdf417` udostępnia każde opcjonalne pole zdefiniowane w specyfikacji PDF417. Możesz mapować te pola na model domenowy, przechowywać je w bazie danych lub używać do walidacji.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Wypełnij model:



## Co warto nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix za pomocą Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Jak stworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Odczyt kodu DataMatrix w C# – Generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}