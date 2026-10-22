---
category: general
date: 2026-10-21
description: Generuj obraz kodu kreskowego databar expanded stacked w C# przy użyciu
  BarcodeGenerator. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby tworzyć
  obrazy kodów kreskowych, dostosowywać wiersze i kolumny oraz eksportować pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: pl
lastmod: 2026-10-21
og_description: Wygeneruj kod kreskowy DataBar Expanded Stacked w C# dzięki temu samouczkowi.
  Dowiedz się, jak używać BarcodeGenerator, ustawiać wiersze i kolumny oraz zapisywać
  obrazy PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Generowanie kodu kreskowego Databar Expanded Stacked w C# – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy Databar Expanded Stacked w C#
url: /pl/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy Databar Expanded Stacked w C#

Jeśli potrzebujesz wygenerować **databar expanded stacked** kod kreskowy w C#, ten przewodnik pokaże Ci, jak to zrobić. Symbolika databar expanded stacked jest idealna do kodowania dużych ilości danych w kompaktowej formie, a obraz możesz utworzyć w kilku linijkach kodu. Dowiesz się także, jak **generować pliki obrazu kodu kreskowego** w różnych formatach oraz jak dostosować liczbę wierszy lub kolumn do swojego środowiska skanowania.

Ten tutorial obejmuje wszystko, co jest potrzebne, aby rozpocząć produkcję kodów kreskowych databar: instalację wymaganego biblioteki, przygotowanie folderu wyjściowego, tworzenie kodu kreskowego z własnymi wierszami lub kolumnami oraz zapis wyniku jako plik PNG. Po zakończeniu będziesz w stanie **tworzyć obrazy kodów kreskowych databar** programowo i dostosować kod do innych formatów obrazu lub scenariuszy uruchomieniowych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Core 3.1 i .NET Framework 4.7+)
* Środowisko programistyczne, takie jak Visual Studio 2022, Visual Studio Code lub Rider
* Dostęp do Internetu w celu zainstalowania pakietu NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Pro tip:** Jeśli używasz potoku CI/CD, dodaj odwołanie do pakietu NuGet w pliku projektu, aby kompilacje były odtwarzalne.

## Zainstaluj bibliotekę Barcode Generator C#

Przykład wykorzystuje bibliotekę Aspose.BarCode, która udostępnia klasę `BarcodeGenerator` oraz wyliczenie `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję do Twojego projektu. Po instalacji możesz zaimportować przestrzeń nazw w swoich plikach C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Przygotuj folder wyjściowy

Solidna ścieżka pliku zapobiega błędom w czasie wykonywania, gdy biblioteka próbuje zapisać obraz. Poniższy kod tworzy katalog, jeśli nie istnieje:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Dlaczego to ważne:** Próba zapisu do nieistniejącego katalogu generuje `IOException`. Utworzenie folderu z wyprzedzeniem sprawia, że kod jest odporny zarówno w środowisku lokalnym, jak i produkcyjnym.

## Generowanie obrazu kodu kreskowego databar expanded stacked

### Podstawowe generowanie kodu kreskowego

Najprostszy sposób na wygenerowanie obrazu **databar expanded stacked** polega na utworzeniu instancji `BarcodeGenerator` z żądaną wartością `EncodeTypes` i zwykłym ładunkiem tekstowym.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Uruchomienie fragmentu tworzy plik `DatabarBasic.png` w folderze *Barcodes*. Obraz zawiera standardowy symbol databar expanded stacked z domyślnym układem (4 kolumny × 4 wiersze).

### Dostosowywanie kolumn – tworzenie kodu kreskowego databar z 4 kolumnami

Liczbę kolumn możesz kontrolować za pomocą właściwości `Parameters.Barcode.DataBar.Columns`. Poniższy przykład tworzy kod kreskowy z **4 kolumnami**, zachowując domyślną liczbę wierszy.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Powstały plik, **DatabarCols4.png**, wygląda tak:

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*Tekst alternatywny obrazu (og_image_alt):* **Sample databar expanded stacked barcode image generated with C#** – spełnia wymóg SEO dla tekstu alternatywnego obrazu.

### Dostosowywanie wierszy – tworzenie kodu kreskowego databar z 3 wierszami

Podobnie, liczbę wierszy możesz zmienić poprzez `Parameters.Barcode.DataBar.Rows`. Poniższy kod generuje kod kreskowy z **3 wierszami** i domyślną liczbą kolumn (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Plik **DatabarRows3.png** zawiera symbol databar expanded stacked, który jest nieco krótszy w pionie, co może być przydatne przy etykietach o ograniczonej przestrzeni.

### Eksport do innych formatów

Jeśli potrzebujesz innego typu obrazu (np. JPEG, BMP lub SVG), zamień `BarCodeImageFormat.Png` na odpowiednią wartość wyliczenia:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Biblioteka obsługuje także formaty wektorowe, takie jak SVG, które są idealne do druku w wysokiej rozdzielczości.

## Zaawansowane scenariusze

### Zapis do strumienia pamięci

Czasami chcesz osadzić kod kreskowy bezpośrednio w odpowiedzi webowej lub w PDF, nie zapisując go na dysku. Użyj `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Obsługa nieprawidłowego wejścia

`BarcodeGenerator` waliduje ładunek pod kątem wybranej symboliki. Jeśli dane zawierają zabronione znaki, zostaje rzucony `ArgumentException`. Owiń kod generujący w blok try‑catch, aby wyświetlić przyjazny komunikat o błędzie:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Skalowanie obrazu kodu kreskowego

Rozmiar obrazu możesz zmienić bez modyfikacji zakodowanych danych, ustawiając `Parameters.Image.Width` i `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Skalowanie jest przydatne, gdy kod kreskowy musi spełniać określone wymagania DPI dla skanerów.

## Pełny działający przykład

Poniżej znajduje się kompletny, gotowy do uruchomienia program konsolowy, demonstrujący wszystkie opisane kroki:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Oczekiwany wynik**


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to build a barcode generator example in C# with DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}