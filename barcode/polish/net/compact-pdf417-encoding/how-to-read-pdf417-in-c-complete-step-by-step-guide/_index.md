---
category: general
date: 2026-07-15
description: Jak odczytać kod kreskowy PDF417 w C# oraz odczytać wiele kodów kreskowych
  z obrazu. Dowiedz się, jak odczytywać obrazy kodów kreskowych w C# z szczegółowym
  kodem i wskazówkami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: pl
lastmod: 2026-07-15
og_description: Jak szybko odczytać kod kreskowy PDF417 w C#. Ten przewodnik pokazuje,
  jak odczytać wiele kodów kreskowych z jednego obrazu i zdekodować każdą właściwość.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Jak odczytać PDF417 w C# – Pełny przykład kodu i wyjaśnienie
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Jak odczytać PDF417 w C# – Kompletny przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać PDF417 w C# – Kompletny przewodnik krok po kroku

Zastanawiałeś się kiedyś **jak odczytać PDF417** z obrazu przy użyciu C#? Nie jesteś jedyny. Większość programistów napotyka problem, gdy muszą wyciągnąć rozszerzone pola Macro‑PDF417 ze zeskanowanego dokumentu. Dobra wiadomość? Dzięki kilku linijkom kodu możesz zdekodować PDF417, odczytać wiele kodów kreskowych na tym samym zdjęciu i pobrać wszystkie ukryte właściwości, które oferuje specyfikacja.

W tym samouczku przeprowadzimy Cię przez praktyczny przykład, który pokazuje **jak odczytać PDF417**, jak **odczytać wiele kodów kreskowych** z jednego pliku oraz dlaczego kod **read barcode image C#** wygląda tak, jak wygląda. Po zakończeniu będziesz mieć gotową do uruchomienia aplikację konsolową, która wypisze każdą potrzebną informację — ID pliku, ID segmentu, sumę kontrolną, znaczniki czasu, cokolwiek potrzebujesz.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Core i .NET Framework).  
* Visual Studio 2022 (lub dowolny edytor, który preferujesz).  
* Pakiet NuGet **Aspose.BarCode for .NET** – to biblioteka, która faktycznie parsuje PDF417.  
* Przykładowy obraz zawierający kod Macro‑PDF417 (np. `ExtPDF417Meta.png`).  

Nie wymagana jest dodatkowa konfiguracja; biblioteka dostarcza wszystkie potrzebne dekodery.

## Krok 1: Zainstaluj Aspose.BarCode

Otwórz folder projektu w terminalu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

To polecenie pobiera najnowszą stabilną wersję (stan na lipiec 2026 to 23.12). Jeśli wolisz konsolę Package Manager w Visual Studio, użyj:

```powershell
Install-Package Aspose.BarCode
```

> **Wskazówka:** zablokuj wersję (`23.12.0`) w pliku `.csproj`, aby uniknąć przypadkowych niekompatybilnych zmian w przyszłości.

## Krok 2: Utwórz szkielet aplikacji konsolowej

Utwórz nowy projekt konsolowy, jeśli jeszcze go nie masz:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Zastąp automatycznie wygenerowany plik `Program.cs` poniższym kodem. Wyjaśnimy każdy fragment w kolejnych sekcjach.

## Krok 3: Napisz pełny kod „Jak odczytać PDF417”

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Dlaczego ten kod działa

* **`BarCodeReader`** jest klasą podstawową, która wczytuje obraz, wykrywa kody kreskowe i zwraca kolekcję obiektów `BarCodeResult`.  
* Przekazanie **`DecodeType.MacroPdf417`** informuje bibliotekę, aby traktowała Macro‑PDF417 w specjalny sposób; nadal zwraca zwykłe symbole PDF417, co spełnia wymaganie **read multiple barcodes**.  
* Obiekt **`Extended.Pdf417.MacroPdf417`** zawiera wszystkie opcjonalne pola zdefiniowane w standardzie ISO/IEC 15438 – to tam znajdują się `FileID`, `SegmentID`, `Checksum` itd.  
* Blok `using` zapewnia zwolnienie zasobów natywnych, zapobiegając wyciekom pamięci w usługach działających długo.

## Krok 4: Uruchom aplikację i zweryfikuj wyjście

Z terminala:

```bash
dotnet run
```

Powinieneś zobaczyć coś podobnego:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Jeśli obraz zawiera więcej niż jeden kod kreskowy, pętla wydrukuje linię separatora (`----------------------------------------`) i przejdzie do kolejnego wyniku — dokładnie to, co w praktyce oznacza **read multiple barcodes**.

## Częste pytania i przypadki brzegowe

### Co zrobić, gdy obraz zawiera zarówno symbole Macro‑PDF417, jak i zwykłe PDF417?

To samo wywołanie `BarCodeReader` zwróci oba typy. Możesz je odróżnić, sprawdzając `result.CodeType` (`MacroPdf417` vs `Pdf417`). Rozszerzone właściwości będą `null` dla zwykłego PDF417, więc warunek `if (macro != null)` zapobiega `NullReferenceException`.

### Mój kod jest obrócony lub pochyły — czy czytnik nadal zadziała?

Aspose.BarCode zawiera wbudowaną kompensację rotacji i zniekształceń. Jeśli kod zajmuje co najmniej 30 % szerokości obrazu, dekoder zazwyczaj się powiedzie. W skrajnych przypadkach możesz włączyć `reader.Options.AllowInvertedBarcodes = true;` przed wywołaniem `ReadBarCodes()`.

### Jak obsłużyć duże partie obrazów?

Umieść logikę odczytu w pętli `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Wzorzec `using` zapewnia zwolnienie natywnych zasobów każdego obrazu przed kolejną iteracją, utrzymując niskie zużycie pamięci.

## Pełny listing źródłowy (gotowy do kopiowania i wklejania)

Poniżej znajduje się cały program w jednym bloku, gotowy do szybkiego kopiowania i wklejania. Brak ukrytych zależności — jedynie pakiet NuGet Aspose.BarCode.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Podsumowanie – Co omówiliśmy

* **How to read PDF417** przy użyciu Aspose.BarCode w C#.  
* Dokładne kroki, aby **read multiple barcodes** z jednego obrazu.  
* Jak **read barcode image C#** i wyodrębnić każde pole Macro‑PDF417.  
* Wskazówki dotyczące rotacji, przetwarzania wsadowego i obsługi brakujących rozszerzonych danych.

## Kolejne kroki i powiązane tematy

* **Encode PDF417** – generuj własne kody Macro‑PDF417 przy użyciu `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – przy użyciu tej samej klasy `BarCodeReader`.  
* **Integrate with ASP.NET Core** – udostępnij endpoint webowy przyjmujący przesłany obraz i zwracający JSON z zdekodowanymi polami.  

Śmiało eksperymentuj: zmień ścieżkę obrazu, wrzuć zwykły PDF417 do tego samego folderu lub zmodyfikuj flagi `DecodeType`, aby zobaczyć, jak biblioteka się zachowuje. Im więcej będziesz się bawić, tym pewniej będziesz się czuł w scenariuszach **read barcode image C#**.

Masz trudny obraz, który odmawia dekodowania? Dodaj komentarz poniżej lub otwórz zgłoszenie w repozytorium GitHub projektu przykładowego. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera pełne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Odczyt kodu DataMatrix C# – Generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}