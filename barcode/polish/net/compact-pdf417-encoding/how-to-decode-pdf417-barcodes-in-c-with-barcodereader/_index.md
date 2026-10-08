---
category: general
date: 2026-09-07
description: Dowiedz się, jak dekodować kody kreskowe PDF417 w C# przy użyciu BarCodeReader.
  Ten przewodnik krok po kroku wyjaśnia również, jak efektywnie odczytywać dane PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: pl
lastmod: 2026-09-07
og_description: Jak dekodować kody PDF417 w C# przy użyciu BarCodeReader. Przejdź
  przez ten samouczek, aby nauczyć się odczytywać dane PDF417 i wyodrębniać pola MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Jak dekodować kody kreskowe PDF417 w C# – kompletny przewodnik
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Jak dekodować kody kreskowe PDF417 w C# przy użyciu BarCodeReader
url: /pl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekodować kody kreskowe PDF417 w C# przy użyciu BarCodeReader

Jeśli potrzebujesz **jak dekodować PDF417** kody kreskowe w aplikacji .NET, ten przewodnik przeprowadzi Cię przez cały proces. Odkryjesz także **jak odczytywać PDF417** dane, takie jak identyfikatory plików i segmentów MacroPdf417, wszystko przy użyciu kilku linii C#.

Dekodowanie PDF417 jest powszechne przy pracy z biletami transportowymi, prawami jazdy czy etykietami wysyłkowymi. Po zakończeniu tego samouczka będziesz mieć działający program konsolowy, który wypisuje każde pole MacroPdf417 udostępnione przez SDK GroupDocs.Barcode.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod kompiluje się z .NET Core i .NET Framework)
* Visual Studio 2022 lub dowolne IDE obsługujące C#
* Pakiet NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Plik obrazu zawierający kod kreskowy Macro PDF417 (np. `ExtPDF417Meta.png`)

> **Wskazówka:** Zainstaluj pakiet za pomocą CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Jak dekodować kody kreskowe PDF417 w C#

Poniższe sekcje dzielą rozwiązanie na logiczne kroki. Każdy krok zawiera dokładny kod, którego potrzebujesz, oraz krótkie wyjaśnienie, dlaczego jest on istotny.

### Krok 1: Przygotuj projekt i zaimportuj przestrzenie nazw

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Dlaczego?*  
`GroupDocs.Barcode` udostępnia klasę `BarCodeReader`, natomiast `GroupDocs.Barcode.Common` zawiera wyliczenie `DecodeType` potrzebne do dekodowania PDF417.

### Krok 2: Zdefiniuj ścieżkę do obrazu

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Dlaczego?*  
Czytnik działa z każdym formatem obrazu obsługiwanym przez .NET (`.png`, `.jpg`, `.bmp`). Podanie poprawnej ścieżki zapewnia, że SDK znajdzie plik.

### Krok 3: Zainicjalizuj czytnik kodów kreskowych dla dekodowania MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Dlaczego?*  
`DecodeType.MacroPdf417` informuje SDK, aby szukał rozszerzonego formatu Macro PDF417, który zawiera dodatkowe metadane, takie jak identyfikatory pliku i segmentu. Użycie instrukcji `using` gwarantuje szybkie zwolnienie zasobów niezarządzanych.

### Krok 4: Odczytaj wszystkie kody kreskowe znalezione na obrazie

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Dlaczego?*  
Obraz może zawierać wiele kodów kreskowych. Metoda `ReadBarCodes()` zwraca kolekcję, co pozwala przetworzyć każdy z nich osobno.

### Krok 5: Pobierz i wyświetl dane specyficzne dla Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Dlaczego?*  
Obiekt `Extended.Pdf417` udostępnia wszystkie pola Macro PDF417 zdefiniowane w specyfikacji. Ich wypisanie pozwala zweryfikować, że operacja dekodowania zakończyła się sukcesem i dostarcza potrzebnych danych do dalszego przetwarzania.

### Pełny działający przykład

Połącz fragmenty powyżej w pojedynczy plik `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Oczekiwany wynik w konsoli** (wartości będą się różnić w zależności od zawartości kodu kreskowego):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Jeśli obraz nie zawiera kodu Macro PDF417, kolekcja `ReadBarCodes()` będzie pusta i nic nie zostanie wypisane.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Jak dostosować kod |
|-----------|----------------------|
| **Standard (non‑macro) PDF417** | Zmien `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Obiekt `Extended.Pdf417` będzie `null`, więc zabezpiecz się przed odwołaniami do null. |
| **Multiple images** | Umieść inicjalizację czytnika w pętli `foreach (var path in imagePaths)`. |
| **Large images** | Ustaw `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;`, aby ograniczyć zużycie pamięci. |
| **Performance‑critical batch** | Ponownie używaj jednej instancji `BarCodeReader` z `reader.SetImage(path)` zamiast tworzyć nowy obiekt dla każdego pliku. |

## Lista kontrolna rozwiązywania problemów

* **Brak wyjścia:** Sprawdź, czy `imagePath` wskazuje na istniejący plik i czy obraz rzeczywiście zawiera kod kreskowy PDF417. |
* **Null `Extended.Pdf417`:** Prawdopodobnie użyto `DecodeType.Pdf417` zamiast `MacroPdf417`. |
* **Wyjątek `FileNotFoundException`:** Upewnij się, że katalog roboczy odpowiada podanej ścieżce lub użyj ścieżki bezwzględnej. |
* **Niska wartość confidence:** Zwiększ jakość obrazu lub dostosuj ustawienia `reader.Options.Quality`. |

## Zakończenie

Teraz wiesz **jak dekodować PDF417** kody kreskowe w C# oraz **jak odczytywać PDF417** metadane, takie jak identyfikatory plików Macro, identyfikatory segmentów i znaczniki czasu. Pełny przykład pokazuje, jak zainicjalizować `BarCodeReader`, wybrać właściwy typ dekodowania, iterować po wynikach i wyodrębnić każde dostępne pole MacroPdf417.

Od tego momentu możesz:

* Zintegrować wyodrębnione dane z systemem logistycznym lub weryfikacji biletów.
* Rozszerzyć aplikację konsolową, aby zapisywała wyniki do bazy danych lub pliku JSON.
* Zbadać inne formaty kodów kreskowych obsługiwane przez GroupDocs.Barcode (QR, DataMatrix, Code128 itp.), zamieniając wyliczenie `DecodeType`.

Miłego kodowania i zachęcamy do eksperymentowania z różnymi obrazami oraz ustawieniami kodów kreskowych, aby opanować dekodowanie PDF417 w swoich projektach .NET!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać PDF417 w C# – Kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Jak odczytać PDF417 w C# – Pełny przykład użycia Barcode Reader](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Jak wygenerować kod kreskowy PDF417 – Kompletny przewodnik programistyczny](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}