---
category: general
date: 2026-07-21
description: Jak odczytać kod kreskowy PDF417 w C# przy użyciu zwięzłego przykładu
  czytnika kodów. Szybko naucz się odczytywać kod kreskowy z obrazu, korzystając z
  kodu krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: pl
lastmod: 2026-07-21
og_description: Jak odczytać kod kreskowy PDF417 w C# w praktycznym przykładzie. Dowiedz
  się, jak odczytać kod kreskowy z obrazu i natychmiast zintegrować przykład czytnika
  kodów kreskowych w C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Jak odczytać PDF417 w C# – Pełny przewodnik po czytniku kodów kreskowych
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Jak odczytać PDF417 w C# – Kompletny przykład czytnika kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać PDF417 w C# – Kompletny przykład czytnika kodów kreskowych

Zastanawiałeś się kiedyś **jak odczytać PDF417** w projekcie .NET, nie przeszukując nieskończonych dokumentacji? Nie jesteś jedyny. Niezależnie od tego, czy skanujesz prawo jazdy, karty pokładowe, czy własne etykiety inwentaryzacyjne, wyodrębnianie tych danych w sposób niezawodny jest rzeczywistą potrzebą.  

W tym przewodniku przeprowadzimy Cię przez **przykład czytnika kodów kreskowych w c#**, który pobiera każdy element metadanych Macro PDF417 z pojedynczego pliku obrazu. Po zakończeniu będziesz mieć gotową do uruchomienia aplikację konsolową, która **odczytuje kod kreskowy z obrazu** i wypisuje wszystkie rozszerzone pola, które mogą być potrzebne.

## Czego będziesz potrzebować

- .NET 6.0 SDK lub nowszy (możesz także celować w .NET Framework 4.7+ – kod działa tak samo)
- Visual Studio 2022, VS Code lub dowolny edytor C#, którego używasz
- Pakiet NuGet **Aspose.BarCode for .NET** (klasa `BarCodeReader` pochodzi z tej biblioteki)
- Plik obrazu zawierający kod Macro PDF417 (do demonstracji użyjemy `ExtPDF417Meta.png`)

> **Wskazówka:** Jeśli nie masz pod ręką przykładu PDF417, Aspose udostępnia kilka obrazów testowych w swoim repozytorium GitHub – po prostu pobierz jeden i umieść go w folderze projektu.

## Krok 1: Zainstaluj bibliotekę kodów kreskowych

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje `BarCodeReader`, `DecodeType` oraz właściwość `Extended`, której będziemy potrzebować później. Nie wymaga dodatkowej konfiguracji; biblioteka działa od razu dla większości formatów obrazów (PNG, JPEG, BMP itp.).

## Krok 2: Utwórz minimalną aplikację konsolową

Utwórz nowy projekt konsolowy, jeśli jeszcze tego nie zrobiłeś:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Zastąp wygenerowany plik `Program.cs` poniższym kodem. Zauważ, że każda sekcja jest skomentowana, abyś mógł śledzić logikę, nawet jeśli jesteś nowy w przetwarzaniu kodów kreskowych.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Dlaczego to działa

- **`DecodeType.MacroPdf417`** informuje czytnik, że ma oczekiwać rozszerzonego formatu Macro PDF417, który zawiera dodatkowe metadane (ID pliku, liczba segmentów, znaczniki czasu itp.).
- Obiekt **`Extended.Pdf417`** jest wypełniany tylko dla kodów Macro PDF417, więc dostęp do tych właściwości jest bezpieczny po wywołaniu `ReadBarCodes()`.
- Użycie bloku **`using`** zapewnia zwolnienie uchwytów plików, zapobiegając problemom z blokadą plików w systemie Windows.

## Krok 3: Uruchom aplikację

Skompiluj i uruchom:

```bash
dotnet run
```

Jeśli obraz zawiera prawidłowy kod Macro PDF417, powinieneś zobaczyć wyjście podobne do:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Jeśli nic nie zostanie wypisane, sprawdź ponownie, czy ścieżka do obrazu jest poprawna i czy kod rzeczywiście jest wariantem Macro PDF417. Zwykły PDF417 (bez rozszerzenia macro) nadal zostanie zdekodowany, ale właściwości `Extended` będą puste.

## Obsługa przypadków brzegowych

### Wiele kodów kreskowych na jednym obrazie

Czasami pojedyncze skanowanie zawiera więcej niż jeden segment PDF417 (np. wielostronicowy dokument zakodowany w kilku symbolach). Pętla `foreach` już enumeruje *wszystkie* wykryte kody, więc nie potrzebujesz dodatkowej logiki — po prostu zbierz segmenty i złoż je ponownie później, jeśli to konieczne.

### Brak danych rozszerzonych

Nie każdy PDF417 zawiera informacje macro. W takim scenariuszu `result.Extended.Pdf417` zostanie zainicjowany, ale jego pola będą miały wartości domyślne (zero, pusty ciąg lub `false`). Możesz się przed tym zabezpieczyć w następujący sposób:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Wskazówki dotyczące wydajności

- **Przetwarzanie wsadowe:** Jeśli masz folder z obrazami, otocz tworzenie `BarCodeReader` pętlą, która ponownie używa tej samej instancji przy pomocy `barcodeReader.SetImage(imagePath)`. To zmniejsza narzut alokacji.
- **Równoległość:** Przy dużych obciążeniach rozważ użycie `Parallel.ForEach` na liście plików, ale pamiętaj, że czytnik Aspose jest bezpieczny wątkowo tylko wtedy, gdy każdy wątek używa własnej instancji `BarCodeReader`.

## Pełny kod źródłowy (gotowy do kopiowania i wklejenia)

Poniżej znajduje się cały program ponownie, gotowy do wstawienia do `Program.cs`. Nie są potrzebne dodatkowe pliki oprócz obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Podsumowanie: Jak szybko odczytać PDF417 w C# 

- Zainstaluj **Aspose.BarCode** za pomocą NuGet.
- skieruj `BarCodeReader` na swój obraz z `DecodeType.MacroPdf417`.
- Przejdź pętlą przez `ReadBarCodes()` i pobierz zarówno podstawowe, jak i rozszerzone pola.
- Elegancko obsłuż brak danych macro i rozważ optymalizacje wydajności przy skanach hurtowych.

## Kolejne kroki i powiązane tematy

- **Odczyt kodu kreskowego z obrazu** przy użyciu innych formatów (QR, DataMatrix) – po prostu zamień enum `DecodeType`.
- **Kodowanie PDF417** przy użyciu `BarCodeGenerator`, jeśli potrzebujesz tworzyć kody kreskowe programowo.
- Zbadaj **poziomy korekcji błędów** i ich wpływ na niezawodność skanowania.
- Zintegruj tę logikę z API ASP.NET Core, aby udostępnić odczyt kodów kreskowych jako usługę webową.

Śmiało eksperymentuj: zmień obraz, baw się flagą `DecodeType` lub wprowadź dane macro do bazy danych. Podstawowy wzorzec pozostaje taki sam, a teraz masz solidny **przykład czytnika kodów kreskowych w c#** w swoim arsenale.

Szczęśliwego kodowania i niech Twoje skany zawsze będą czyste!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletny działający kod z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak stworzyć strefę ciszy dla Code 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}