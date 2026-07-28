---
category: general
date: 2026-07-27
description: Jak szybko odczytać kod PDF417 w C#. Dowiedz się, jak odczytywać wiele
  kodów, dekodować obrazy i uzyskać metadane Macro PDF417 w pełnym przykładzie w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: pl
lastmod: 2026-07-27
og_description: Jak odczytać kod kreskowy PDF417 w C# za pomocą tego przewodnika krok
  po kroku. Dekoduj obrazy, obsługuj wiele kodów kreskowych i wyodrębnij metadane
  Macro PDF417 w gotowym do uruchomienia przykładzie.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Jak odczytać PDF417 w C# – Pełny przykład kodu kreskowego
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Jak odczytać PDF417 w C# – Pełny przykład kodu kreskowego
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać PDF417 w C# – Kompletny przykład kodu kreskowego

Zastanawiałeś się kiedyś **jak odczytać kod kreskowy PDF417** w aplikacji C# bez wyrywania sobie włosów? Nie jesteś jedyny. Niezależnie od tego, czy tworzysz skaner logistyczny, weryfikator biletów, czy po prostu potrzebujesz pobrać dane z identyfikatora zakodowanego w PDF417, proces może na początku wydawać się nieco tajemniczy.  

W tym samouczku przeprowadzimy Cię przez **przykład kodu kreskowego c#**, który odczytuje obraz PDF417, obsługuje **odczyt wielu kodów kreskowych**, jeśli są obecne, oraz wyodrębnia wszystkie przydatne metadane Macro PDF417, które mogą być potrzebne.

## Co zbudujesz

Pod koniec tego przewodnika będziesz mieć mały program konsolowy, który:

1. Wczytuje obraz kodu kreskowego z dysku.  
2. Dekoduje **PDF417** (w tym Macro PDF417) kody kreskowe.  
3. Wyświetla podstawowe informacje, takie jak typ kodu i tekst.  
4. Wyświetla pełny zestaw pól Macro PDF417 (identyfikator pliku, identyfikator segmentu, suma kontrolna itp.).  

Bez zewnętrznych usług, tylko pojedynczy pakiet NuGet i kilka linii C#.

## Wymagania wstępne – Co potrzebujesz przed rozpoczęciem

- **.NET 6.0** lub nowszy (kod działa również na .NET Framework 4.6+).  
- Najnowsza wersja biblioteki **Aspose.BarCode for .NET** – zainstaluj ją przez NuGet (`Install-Package Aspose.BarCode`).  
- Plik obrazu zawierający kod kreskowy PDF417 (demo używa `ExtPDF417Meta.png`).  
- Podstawowa znajomość aplikacji konsolowych C# (jeśli napisałeś „Hello World”, jesteś gotowy).

> **Wskazówka:** Jeśli nie masz pod ręką przykładu PDF417, wygeneruj go na stronie demo Aspose lub użyj aplikacji na smartfonie, która może tworzyć tagi PDF417.

## Krok 1: Skonfiguruj projekt i zainstaluj bibliotekę

First, create a new console project:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

To pull in the **c# barcode example** dependencies we need. Open `Program.cs` and replace the default code with the skeleton below:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Krok 2: Zainicjalizuj czytnik kodów kreskowych dla PDF417

Serce rozwiązania stanowi klasa `BarCodeReader`. Informujemy ją, który plik skanować i jakiego typu kod kreskowy nas interesuje — w tym przypadku `DecodeType.Pdf417` lub wariant macro `DecodeType.MacroPdf417`. Użycie typu macro zapewnia przechwycenie rozszerzonych pól.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Dlaczego używać `MacroPdf417` zamiast zwykłego `Pdf417`? Macro PDF417 zawiera dodatkowe metadane (identyfikator pliku, liczba segmentów, znaczniki czasu itp.), na których opiera się wiele rzeczywistych aplikacji — pomyśl o listach przewozowych podzielonych na kilka stron.

## Krok 3: Odczytaj wszystkie kody kreskowe znalezione na obrazie

Pojedynczy obraz może zawierać **odczyt wielu kodów kreskowych** — na przykład kod QR obok PDF417. Metoda `ReadBarCodes()` zwraca `IEnumerable<BarCodeResult>`, po którym możemy iterować.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Jeśli obraz zawiera tylko jeden PDF417, pętla i tak wykona się raz, co utrzymuje kod elastycznym na przyszłe scenariusze, w których może być konieczne **odczytanie wielu kodów kreskowych** z jednego skanu.

## Krok 4: Wyświetl podstawowe informacje o kodzie kreskowym

Zanim zagłębimy się w pola macro, warto wyświetlić typ kodu kreskowego oraz zdekodowany tekst. Pomaga to zweryfikować, że czytnik rzeczywiście rozpoznał PDF417, a nie inną symbologię.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` zwróci *MacroPdf417* (lub *Pdf417*, jeśli flaga macro nie jest ustawiona), natomiast `CodeText` zawiera surowe dane zakodowane w kodzie kreskowym.

## Krok 5: Wyodrębnij metadane Macro PDF417

Właściwość `Extended` pozwala na dogłębny wgląd w strukturę specyficzną dla PDF417. Każde pole, które wypiszemy poniżej, odpowiada bezpośrednio specyfikacji Macro PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Each line pulls a different piece of the macro payload:

- **FileID** – unikalny identyfikator całego zestawu dokumentów.  
- **SegmentID** – część wielosegmentowego pliku, którą przeglądasz.  
- **SegmentsCount** – łączna liczba oczekiwanych segmentów.  
- **FileName, Checksum, FileSize** – przydatne do weryfikacji integralności przesyłanego pliku.  
- **TimeStamp, Addressee, Sender** – pola opcjonalne, które wiele systemów logistycznych osadza.  

Jeśli którekolwiek z tych pól jest nieobecne w źródłowym kodzie kreskowym, biblioteka zwróci `null` lub `0`, co możesz obsłużyć w zależności od potrzeb.

## Krok 6: Uruchom kompletny przykład

Putting it all together, here’s the full, ready‑to‑run program:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Oczekiwany wynik

When you run the program against a valid `ExtPDF417Meta.png`, you should see something akin to:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Jeśli obraz zawiera więcej niż jeden kod kreskowy,

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody kreskowe PDF417 – Kompaktowe kodowanie PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak tworzyć kody kreskowe – Kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak odczytywać kody DataMatrix z Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}