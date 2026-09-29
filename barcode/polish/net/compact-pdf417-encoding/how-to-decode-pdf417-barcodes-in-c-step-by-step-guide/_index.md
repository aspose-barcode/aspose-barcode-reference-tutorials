---
category: general
date: 2026-09-29
description: Jak dekodować kody kreskowe PDF417 w C# przy użyciu Aspose.BarCode. Poznaj
  przykład czytnika kodów kreskowych, który pokazuje, jak odczytywać obrazy kodów
  kreskowych i wyodrębniać dane makro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: pl
lastmod: 2026-09-29
og_description: Jak dekodować kody kreskowe PDF417 w C# przy użyciu Aspose.BarCode.
  Ten przewodnik pokazuje gotowy do uruchomienia przykład czytnika kodów kreskowych
  do odczytu obrazów kodów.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Jak dekodować kody PDF417 w C# – kompletny przykład czytnika kodów
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Jak dekodować kody kreskowe PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekodować kody kreskowe PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **jak dekodować PDF417** kody kreskowe w C#, ten tutorial dostarcza kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz **przykład czytnika kodów kreskowych**, który demonstruje **jak odczytywać kod kreskowy** z obrazów, wyodrębnia informacje makro i wypisuje wyniki w konsoli.

Dekodowanie PDF417 jest powszechne przy przetwarzaniu etykiet wysyłkowych, biletów czy dokumentów tożsamości. Po zakończeniu tego przewodnika będziesz w stanie odczytać obraz kodu PDF417, uzyskać dostęp do jego pól makro oraz obsłużyć typowe przypadki brzegowe. Nie jest wymagana żadna zewnętrzna dokumentacja – wszystko, czego potrzebujesz, znajduje się w tym tutorialu.

## Czego się nauczysz

- Zainstalować bibliotekę Aspose.BarCode dla .NET  
- Utworzyć `BarCodeReader`, który **read PDF417 barcode** dane z pliku PNG lub JPEG  
- Iterować po obiektach `BarCodeResult` i pobierać właściwości macro‑PDF417  
- Rozwiązywać typowe problemy, takie jak nieobsługiwane formaty obrazów lub brak danych makro  

## Wymagania wstępne

| Wymaganie | Powód |
|-------------|--------|
| .NET 6.0 SDK lub nowszy | Dostarcza środowisko uruchomieniowe dla projektów C# |
| Visual Studio 2022 (lub dowolne IDE obsługujące .NET) | Umożliwia łatwe tworzenie projektów i debugowanie |
| Pakiet NuGet **Aspose.BarCode** | Dostarcza klasę `BarCodeReader` używaną w przykładzie |
| Obraz makro PDF417 (np. `ExtPDF417Meta.png`) | Plik źródłowy, który czytnik będzie dekodował |

> **Pro tip:** Jeśli nie masz obrazu PDF417, możesz go wygenerować za pomocą darmowego demo online Aspose.BarCode lub zeskanować rzeczywistą etykietę.

## Krok 1: Zainstaluj Aspose.BarCode przez NuGet

Otwórz terminal w folderze rozwiązania i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję Aspose.BarCode do Twojego projektu i aktualizuje plik `.csproj`. Biblioteka ta implementuje funkcjonalność **read barcode image C#** dla dziesiątek symbologii, w tym PDF417.

## Krok 2: Utwórz BarCodeReader do **jak dekodować PDF417**

Rdzeniem procesu **how to read barcode** jest `BarCodeReader`. Musisz podać czytnikowi zarówno ścieżkę do pliku, jak i oczekiwaną symbologię (`DecodeType.MacroPdf417`). Podanie właściwego `DecodeType` zwiększa szybkość wykrywania i dokładność.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Dlaczego to ważne:**  
- `DecodeType.MacroPdf417` informuje silnik, aby szukał pól macro‑PDF417 (identyfikator pliku, identyfikator segmentu itp.).  
- Użycie `using` zapewnia zamknięcie strumienia obrazu, zapobiegając problemom z blokadą plików w systemie Windows.

## Krok 3: Iteruj po wykrytych kodach kreskowych

Jedno zdjęcie może zawierać wiele kodów kreskowych. Metoda `ReadBarCodes()` zwraca `IEnumerable<BarCodeResult>`, po którym możesz iterować.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Jeśli obraz nie zawiera żadnych symboli PDF417, ciało pętli nigdy się nie wykona i możesz obsłużyć ten przypadek po zakończeniu pętli (zobacz sekcję „Error handling”).

## Krok 4: Dostęp do pól makro PDF417

Każdy `BarCodeResult` udostępnia właściwość `Extended` z pod‑obiektem `Pdf417`. Najczęściej potrzebne pola makro to:

| Właściwość | Znaczenie |
|----------|---------|
| `MacroPdf417FileID` | Identyfikator całego pliku macro PDF417 |
| `MacroPdf417SegmentID` | Numer kolejny bieżącego segmentu |
| `MacroPdf417FileName` | Opcjonalna nazwa pliku przechowywana w makro |

Oto pełny kod, który wypisuje te wartości:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Oczekiwany wynik w konsoli

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Jeśli pola makro nie są obecne, wyjście będzie zawierało puste linie, ponieważ właściwości są `null`. Jest to normalne dla kodów PDF417 nie‑makro.

## Krok 5: Obsługa typowych problemów (obsługa błędów i przypadki brzegowe)

### Nie wykryto kodu kreskowego

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Nieobsługiwany format obrazu

Aspose.BarCode obsługuje PNG, JPEG, BMP, TIFF i GIF. Próba odczytu pliku RAW lub WebP powoduje wyrzucenie `ArgumentException`. Przed przekazaniem obrazu do czytnika skonwertuj go na obsługiwany format.

### Duże pliki makro

Macro‑PDF417 może rozciągać się na wiele segmentów. Aby odtworzyć oryginalny plik, musisz zebrać wszystkie segmenty (posortowane według `MacroPdf417SegmentID`) i połączyć ich ładunki. Powyższy przykład jedynie wypisuje metadane poszczególnych segmentów; w implementacji produkcyjnej każdy segment byłby przechowywany w słowniku, a po odczytaniu wszystkich segmentów zostanie złożony w całość.

### Wskazówka dotycząca wydajności

Jeśli przetwarzasz tysiące obrazów, ponownie używaj jednej instancji `BarCodeReader` z metodą `SetImage` zamiast tworzyć nowy obiekt dla każdego pliku. Redukuje to alokacje pamięci i przyspiesza dekodowanie.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Pełny działający przykład

Skopiuj poniższy program do nowego projektu Console App (`dotnet new console`). Zawiera wszystkie kroki, obsługę błędów i komentarze.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Uruchamianie programu**

```bash
dotnet run
```

Powinieneś zobaczyć wypisane pola makro w konsoli, zgodnie z oczekiwanym wynikiem pokazanym wcześniej.

## Zakończenie

W tym tutorialu nauczyłeś się **jak dekodować PDF417** kody kreskowe w C# przy użyciu zwięzłego **przykładu czytnika kodów kreskowych**. Instalując Aspose.BarCode, tworząc `BarCodeReader` dla `MacroPdf417`, iterując po wynikach i uzyskując dostęp do właściwości `Extended.Pdf417`, możesz niezawodnie **read PDF417 barcode** dane z dowolnego obsługiwanego obrazu.  

Od tego momentu możesz:

- Zaimplementować agregację segmentów w celu odtworzenia wielosegmentowych plików makro.  
- Poznać inne symbologie (QR, Code128) używając tego samego wzorca `BarCodeReader`.  
- Zintegrować dekoder z API webowym, które przetwarza przesłane obrazy (`read barcode image C#` w kontekście usługi).  

Śmiało eksperymentuj z różnymi źródłami obrazów, strategiami obsługi błędów i optymalizacjami wydajności. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać PDF417 w C# – kompletny przewodnik po czytniku kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Jak wygenerować kod kreskowy PDF417 z Aspose – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak utworzyć kod kreskowy PDF417 z Aspose – kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}