---
category: general
date: 2026-08-03
description: Odczytaj kod kreskowy PDF417 z obrazu przy użyciu C# BarCodeReader –
  kompletny przykład czytnika kodów kreskowych, który również pokazuje, jak odczytać
  wiele kodów kreskowych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: pl
lastmod: 2026-08-03
og_description: Szybko odczytaj kod kreskowy PDF417 przy użyciu przykładu C# BarCodeReader.
  Postępuj zgodnie z tym przewodnikiem krok po kroku, aby zdekodować macro PDF417
  i odczytać wiele kodów kreskowych z obrazu.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Odczytaj kod kreskowy PDF417 w C# – kompletny przykład czytnika kodów
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Odczyt kodu PDF417 w C# – przykład czytnika kodów
url: /pl/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczyt kodu kreskowego PDF417 w C# – przykład czytnika kodów kreskowych

Jeśli potrzebujesz odczytać dane z kodu kreskowego PDF417 z obrazu, ten przewodnik pokaże Ci, jak zrobić to przy użyciu klasy **BarCodeReader** w C#. Poznasz przykład czytnika kodów kreskowych, który obsługuje także macro PDF417 i potrafi odczytać wiele kodów w jednym obrazie.

Praca z kodami kreskowymi często oznacza radzenie sobie z różnymi źródłami obrazów, zmiennymi warunkami oświetleniowymi oraz czasami złożonymi danymi, takimi jak segmenty macro PDF417. Ten tutorial obejmuje wszystko, co jest potrzebne do dekodowania kodu PDF417, wyodrębniania jego rozszerzonych pól i przetwarzania kilku kodów z tego samego zdjęcia. Po zakończeniu będziesz mieć działający program konsolowy, który odczytuje kody kreskowe z pliku obrazu i wypisuje szczegółowe informacje w konsoli.

## Czego będziesz potrzebować

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Aktualną wersję pakietu NuGet **Aspose.BarCode for .NET** (lub dowolną kompatybilną bibliotekę, która udostępnia `BarCodeReader` i `DecodeType.MacroPdf417`)  
* Plik obrazu zawierający kod PDF417 lub macro PDF417 (przykład używa `ExtPDF417Meta.png`)  
* Edytor kodu lub IDE, np. Visual Studio 2022  

Nie są wymagane dodatkowe usługi ani zewnętrzne API.

## Konfiguracja projektu do odczytu kodów kreskowych

1. **Utwórz nowy projekt konsolowy**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Dodaj bibliotekę kodów kreskowych**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Skopiuj obraz kodu kreskowego**  

   Umieść `ExtPDF417Meta.png` (lub dowolny obraz zawierający kod PDF417) w folderze projektu.  
   W tym tutorialu zakładamy, że plik znajduje się w `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projekt jest już gotowy do kompilacji i uruchomienia przykładu czytnika kodów kreskowych.

## Jak odczytać kod PDF417 przy użyciu BarCodeReader

Sednem rozwiązania jest blok `using`, który tworzy instancję `BarCodeReader`, określa `DecodeType.MacroPdf417` i iteruje po każdym wykrytym kodzie. Poniższy kod to kompletny, samodzielny program, który możesz wkleić do `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Dlaczego to działa**:  

* `DecodeType.MacroPdf417` instruuje czytnik, aby szukał rozszerzenia macro kodu PDF417, które zawiera dodatkowe metadane, takie jak identyfikator pliku, liczba segmentów i znaczniki czasu.  
* Instrukcja `using` zapewnia, że zasoby niezarządzane (uchwyty plików, natywne bufory dekodowania) zostaną zwolnione natychmiast.  
* Pętla `foreach` automatycznie przetwarza **wszystkie** kody kreskowe znajdujące się na obrazie, spełniając wymóg *odczytu wielu kodów*.

Po uruchomieniu programu (`dotnet run`) powinieneś zobaczyć wyjście podobne do poniższego:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Jeśli obraz zawiera więcej niż jeden kod PDF417, pętla wypisze oddzielny blok dla każdego kodu, demonstrując w ten sposób **odczyt wielu kodów** z jednego zdjęcia.

## Odczyt wielu kodów z obrazu

Ta sama instancja `BarCodeReader` może dekodować kilka typów kodów jednocześnie. Aby rozszerzyć zakres z macro PDF417 na dowolny PDF417 (lub nawet QR, Code128 itp.), zmień flagę `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* jest maską bitową, więc możesz połączyć dowolną liczbę obsługiwanych formatów. Ta elastyczność czyni fragment **przykładem czytnika kodów kreskowych**, który działa w szerokim wachlarzu scenariuszy, takich jak skanowanie etykiet produktów, biletów czy kart identyfikacyjnych.

## Bezpieczny dostęp do pól macro PDF417

Macro PDF417 dodaje bogaty zestaw rozszerzonych właściwości. Jednak nie każdy kod zawiera wszystkie pola. Dostęp do nieistniejącej właściwości może spowodować `NullReferenceException`. Najbezpieczniejszym podejściem jest weryfikacja każdej właściwości przed jej wypisaniem:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Dlaczego to ważne*: W rzeczywistych wdrożeniach możesz otrzymać zwykłe kody PDF417, które nie posiadają danych macro. Sprawdzanie defensywne zapewnia, że aplikacja będzie działać dalej bez awarii.

## Typowe pułapki i dobre praktyki

| Problem | Dlaczego się pojawia | Zalecane rozwiązanie |
|---------|----------------------|----------------------|
| Nieprawidłowa ścieżka do obrazu | `BarCodeReader` zgłasza wyjątek „file‑not‑found” przed rozpoczęciem dekodowania | Użyj `Path.Combine` i sprawdź istnienie pliku przy pomocy `File.Exists` |
| Obraz o niskiej rozdzielczości | Dekoder nie może znaleźć krawędzi kodu, co skutkuje zerową liczbą wykryć | Zapewnij minimalną rozdzielczość 300 dpi dla wiarygodnych wyników |
| Kod obrócony o > 45° | Wiele bibliotek zakłada orientację pionową | Włącz `reader.RecognitionOptions.RotateImage = true`, jeśli obraz może być obrócony |

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Odczyt kodu DataMatrix w C# – generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Odczyt kodu kreskowego z obrazu – mistrzostwo w ekstrakcji regionu kodu w Javie z Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}