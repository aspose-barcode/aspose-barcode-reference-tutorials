---
category: general
date: 2026-09-22
description: Dowiedz się, jak odczytywać kody kreskowe PDF417 w C# przy użyciu pełnego
  przykładu czytnika kodów kreskowych. Ten poradnik pokazuje, jak szybko i niezawodnie
  odczytywać obrazy kodów kreskowych w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: pl
lastmod: 2026-09-22
og_description: Jak odczytać kody kreskowe PDF417 w C# przy użyciu zwięzłego przykładu
  czytnika kodów. Postępuj zgodnie z przewodnikiem, aby dekodować obrazy Macro PDF417
  i wyodrębniać metadane.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Jak odczytać kody kreskowe PDF417 w C# – pełny przykład czytnika kodów
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Jak odczytywać kody kreskowe PDF417 w C# – kompletny przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kody kreskowe PDF417 w C# – kompletny przewodnik krok po kroku

Jeśli potrzebujesz **jak odczytać pdf417** w aplikacji .NET, ten przewodnik pokaże Ci dokładny kod i uzasadnienie, którego potrzebujesz. Po przeczytaniu pierwszych dwóch zdań będziesz wiedział, jak odczytać obraz kodu kreskowego w C# przy użyciu popularnej klasy `BarCodeReader`, oraz będziesz miał gotowy do uruchomienia przykład, który wyodrębnia każdy element metadanych Macro PDF417.

Odczytywanie kodów kreskowych PDF417 jest częstym wymogiem przy przetwarzaniu etykiet wysyłkowych, kart pokładowych lub dokumentów zabezpieczonych. Ten samouczek obejmuje wszystko, od konfiguracji czytnika po obsługę przypadków brzegowych, dzięki czemu możesz integrować skanowanie kodów kreskowych z pełnym przekonaniem.

## Co osiągniesz

- Zdekoduj plik obrazu Macro PDF417.
- Wydrukuj podstawowe informacje o kodzie kreskowym (typ i tekst).
- Uzyskaj dostęp do wszystkich rozszerzonych pól Macro PDF417, takich jak ID pliku, liczba segmentów i znacznik czasu.
- Zrozum typowe pułapki przy pracy z kodami PDF417 składającymi się z wielu segmentów.

**Wymagania wstępne**

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+).
- Odwołanie do SDK kodów kreskowych, które udostępnia `BarCodeReader`, `DecodeType` i `BarCodeResult` (np. Aspose.BarCode, Dynamsoft lub dowolna biblioteka udostępniająca to samo API).
- Plik obrazu (`ExtPDF417Meta.png`) zawierający kod Macro PDF417.

> **Wskazówka:** Umieść obraz w folderze względem katalogu głównego projektu i ustaw jego właściwość **Copy to Output Directory** na *Copy if newer*, aby ścieżka działała podczas debugowania.

![Jak odczytać kod kreskowy PDF417 przy użyciu C#](https://example.com/placeholder-image.png)

## Jak odczytać kod kreskowy PDF417 w C# – kompletny kod

Poniżej znajduje się samodzielny program, który możesz wkleić do aplikacji konsolowej. Tworzy on czytnik kodów kreskowych, iteruje po każdym zdekodowanym wyniku i wypisuje zarówno standardowe, jak i rozszerzone pola Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
```

### Dlaczego każdy krok ma znaczenie

1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417 is a special variant that can carry file‑level metadata. Specifying the decode type ensures the SDK parses those extra fields instead of treating the code as a plain PDF417.  
   **Tworzenie czytnika z `DecodeType.MacroPdf417`** – Macro PDF417 to specjalna odmiana, która może przenosić metadane na poziomie pliku. Określenie typu dekodowania zapewnia, że SDK analizuje te dodatkowe pola zamiast traktować kod jako zwykły PDF417.

2. **Iterating over `ReadBarCodes()`** – An image can contain more than one barcode (e.g., a QR code next to a PDF417). The loop guarantees you capture every result.  
   **Iterowanie po `ReadBarCodes()`** – Obraz może zawierać więcej niż jeden kod kreskowy (np. kod QR obok PDF417). Pętla gwarantuje przechwycenie każdego wyniku.

3. **Printing `CodeTypeName` and `CodeText`** – These are the most frequently used properties; they give you the symbology name and the human‑readable payload.  
   **Wypisywanie `CodeTypeName` i `CodeText`** – Są to najczęściej używane właściwości; podają nazwę symbologii oraz czytelny dla człowieka ładunek.

4. **Accessing `Extended.Pdf417`** – The `Extended` object only appears for PDF417‑related decode types. Each property maps directly to the Macro PDF417 specification, allowing you to rebuild the original file or validate segment order.  
   **Dostęp do `Extended.Pdf417`** – Obiekt `Extended` pojawia się tylko dla typów dekodowania związanych z PDF417. Każda właściwość mapuje się bezpośrednio na specyfikację Macro PDF417, umożliwiając odtworzenie oryginalnego pliku lub weryfikację kolejności segmentów.

## Typowe warianty i przypadki brzegowe

### Odczyt kodu PDF417 bez makra

Jeśli Twoje obrazy źródłowe zawierają zwykłe kody PDF417 (bez metadanych makra), zamień `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Reszta kodu pozostaje identyczna, ale blok `Extended.Pdf417` będzie pusty, ponieważ te pola po prostu nie istnieją.

### Obsługa wielosegmentowych PDF‑ów

Macro PDF417 can split a large document across several barcode segments. To reassemble the original file you must:

1. Zbierz `Pdf417MacroSegmentID` każdego segmentu.
2. Posortuj segmenty według ich ID.
3. Sprawdź, czy `Pdf417MacroSegmentsCount` odpowiada liczbie otrzymanych segmentów.
4. Połącz kolejno `CodeText` każdego segmentu.
5. Opcjonalnie zweryfikuj `Pdf417MacroChecksum`.

Poniżej znajduje się zwięzły fragment kodu, który demonstruje logikę składania:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Radzenie sobie z uszkodzonymi obrazami

- **Niski kontrast** – Zwiększ wstępne przetwarzanie obrazu (np. wyrównanie histogramu) przed przekazaniem go do `BarCodeReader`.
- **Rotacja** – Użyj `barcodeReader.SetRotateAngle(90)` lub włącz auto‑rotację, jeśli SDK to obsługuje.
- **Częściowe skany** – Upewnij się, że rozdzielczość obrazu wynosi co najmniej 300 dpi; w przeciwnym razie SDK może pominąć małe segmenty.

## Przykład czytnika kodów kreskowych w C# – najlepsze praktyki

| Praktyka | Powód |
|----------|--------|
| **Zwolnij czytnik przy pomocy `using`** | Gwarantuje szybkie zwolnienie zasobów natywnych, zapobiegając wyciekom pamięci. |
| **Sprawdź, czy `result.Extended` nie jest null** | Niektóre SDK zwracają `null` dla kodów nie‑makro; sprawdzenie zapobiega `NullReferenceException`. |
| **Zaloguj `Pdf417MacroFileID`** | Ten identyfikator jest unikalny dla każdego pliku i przydatny w ścieżkach audytu. |
| **Umieść dekodowanie w bloku try/catch** | Błędy I/O (brak pliku) lub nieobsługiwane formaty generują wyjątki, które powinny być obsłużone w sposób elegancki. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Oczekiwany wynik

Uruchomienie pełnego programu przeciwko prawidłowo sformatowanemu `ExtPDF417Meta.png` daje wynik podobny do:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Jeśli obraz zawiera wiele segmentów, pętla wypisze metadane każdego segmentu kolejno.

## Zakończenie

Teraz wiesz **jak odczytać pdf417** w C# i masz **przykład czytnika kodów kreskowych w C#**, który wyodrębnia każde pole Macro PDF417. Rozwiązanie obejmuje podstawowe dekodowanie, ekstrakcję metadanych, składanie wielosegmentowe oraz obsługę błędów, dając Ci gotową do produkcji podstawę dla każdego przepływu przetwarzania dokumentów.

### Kolejne kroki

- Zbadaj techniki **read barcode image C#** dla innych symbologii (QR, DataMatrix) używając tego samego API `BarCodeReader`.
- Zintegruj dekoder kodów kreskowych z usługą ASP.NET Core, aby przetwarzać przesyłane pliki w locie.
- Eksperymentuj z bibliotekami wstępnego przetwarzania obrazu (np. `OpenCvSharp`), aby zwiększyć skuteczność przy skanach niskiej jakości.

Miłego kodowania i śmiało dostosowuj przykład do swojego konkretnego przypadku użycia!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak zapisać kod kreskowy w C# – generowanie kodów PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Jak odczytać PDF417 w C# – kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Jak ustawić poziom błędu w kodzie PDF417 – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}