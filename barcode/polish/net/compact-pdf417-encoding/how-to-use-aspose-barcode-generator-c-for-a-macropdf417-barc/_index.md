---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# umożliwia łatwe dodawanie danych makro i
  generowanie kodów kreskowych PDF417. Dowiedz się krok po kroku, jak dodać metadane
  makro i utworzyć obraz PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: pl
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# pokazuje, jak dodać metadane makra i wygenerować
  kod kreskowy PDF417 w kilku linijkach kodu.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Generator kodów kreskowych Aspose C# – dodaj makro i generuj kod PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Jak używać generatora kodów kreskowych Aspose w C# do kodu MacroPdf417
url: /pl/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose Barcode Generator C# do kodu kreskowego MacroPdf417

Jeśli potrzebujesz utworzyć kod kreskowy MacroPdf417 w C#, **Aspose Barcode Generator C#** zapewnia zwięzłe API, które obsługuje zarówno obraz kodu kreskowego, jak i wymagane metadane makra. Ten samouczek pokazuje dokładnie, jak dodać informacje makra i wygenerować obraz kodu PDF417 w kilku prostych krokach.

Nauczysz się konfigurować parametry wizualne, osadzać pola makra takie jak identyfikator pliku i znacznik czasu oraz zapisywać wynik jako PNG. Nie są wymagane żadne zewnętrzne narzędzia — wystarczy biblioteka Aspose.BarCode oraz środowisko programistyczne .NET.

## Wymagania wstępne

* .NET 6.0 lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE C#)  
* Licencjonowana lub ewaluacyjna kopia **Aspose.BarCode for .NET**  

Kod działa na Windows, Linux i macOS, ponieważ biblioteka jest niezależna od platformy.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz swój projekt w Visual Studio, a następnie uruchom następujące polecenie w **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

To dodaje zestaw `Aspose.BarCode` oraz jego zależności do Twojego projektu.

## Krok 2: Utwórz instancję generatora kodów kreskowych

Pierwsza linia tworzy obiekt `BarcodeGenerator` dla symbolu **MacroPdf417** i podaje tekst, który ma zostać zakodowany.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Dlaczego to ważne*: Wartość `EncodeTypes.MacroPdf417` informuje bibliotekę, że ma oczekiwać pól związanych z makrem, które ustawisz w następnym kroku.

## Krok 3: Zdefiniuj wygląd wizualny

Możesz kontrolować rozmiar każdego modułu (najmniejszego czarnego lub białego kwadratu) oraz liczbę kolumn w macierzy PDF417. Dostosowanie `XDimension` wpływa na ogólną rozdzielczość obrazu.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Zwiększenie `Columns` zmniejsza wysokość kodu kreskowego, natomiast większe `XDimension` sprawia, że obraz jest wyraźniejszy na ekranach o wysokiej rozdzielczości DPI.

## Krok 4: Dodaj metadane makra (jak dodać makro)

MacroPdf417 wymaga kilku dodatkowych pól opisujących plik źródłowy i jego segmentację. Poniższe właściwości mapują się bezpośrednio na specyfikacje makra PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Dlaczego te pola*:
* `MacroPdf417FileID` łączy wszystkie segmenty, zapewniając, że skaner może ponownie złożyć oryginalny dokument.
* `MacroPdf417SegmentID` i `MacroPdf417SegmentsCount` informują dekoder o kolejności i łącznej liczbie części.
* `MacroPdf417FileSize` i `MacroPdf417Checksum` zapewniają kontrole integralności, co jest przydatne przy przesyłaniu dużych ilości danych.

## Krok 5: Zapisz obraz kodu kreskowego (jak wygenerować pdf417)

Na koniec zapisz kod kreskowy na dysku. Metoda `Save` przyjmuje ścieżkę pliku oraz format obrazu. PNG zachowuje ostre krawędzie kodu kreskowego bez artefaktów kompresji.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Po uruchomieniu programu znajdziesz **ExtPDF417Meta.png** w folderze wyjściowym. Otworzenie obrazu pokazuje czysty kod MacroPdf417 gotowy do druku lub osadzenia w PDF.

### Oczekiwany wynik

| Nazwa pliku          | Format | Wymiary (przybliżone) |
|----------------------|--------|-----------------------|
| ExtPDF417Meta.png    | PNG    | 300 × 150 px (varies with `XDimension`) |

Skanowanie obrazu przy użyciu czytnika kompatybilnego z PDF417 (np. ZXing, Aspose.BarCode for .NET) zwraca oryginalny tekst **„Åspóse.Barcóde©”** wraz ze wszystkimi polami makra.

## Typowe pułapki i jak ich uniknąć

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Nieprawidłowy `EncodeTypes`** | Użycie `EncodeTypes.Pdf417` zamiast `EncodeTypes.MacroPdf417` wyłącza pola makra. | Zawsze twórz generator z `EncodeTypes.MacroPdf417`. |
| **Brak pól makra** | Niektóre skanery ignorują kod kreskowy, jeśli wymagane pola makra są pominięte. | Wypełnij przynajmniej `FileID`, `SegmentID`, `SegmentsCount` i `Terminator`. |
| **Zbyt małe `XDimension`** | Wartość poniżej 1 piksela może spowodować nieczytelny kod kreskowy na wyświetlaczach o niskiej rozdzielczości. | Utrzymuj `XDimension` ≥ 2 piksele w większości scenariuszy ekranowych i drukarskich. |
| **Błędy ścieżki pliku** | Podanie względnej ścieżki, która nie istnieje, powoduje wyrzucenie wyjątku. | Użyj `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` lub ścieżki bezwzględnej. |

## Pełny kod źródłowy

Poniżej znajduje się kompletny, gotowy do uruchomienia przykład, który możesz skopiować do nowego projektu konsolowego.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Uruchom program (`dotnet run`). Po wykonaniu konsola wyświetli komunikat o sukcesie, a plik PNG pojawi się w folderze wyjściowym projektu.

## Kolejne kroki

* **Koduj większe dane** – Zwiększ `Columns` lub dostosuj `Rows` (poprzez `Pdf417.Rows`), aby pomieścić więcej znaków.  
* **Osadź w PDF** – Użyj Aspose.PDF, aby umieścić wygenerowany PNG w dokumencie.  
* **Weryfikacja skanowania** – Skorzystaj z `Aspose.BarCode.Reader`, aby odczytać kod kreskowy i programowo potwierdzić pola makra.  

Zgłębianie tych tematów pogłębia Twoją wiedzę o **tworzeniu kodów PDF417** z bogatymi informacjami makra i przygotowuje do rzeczywistych przypadków użycia, takich jak przetwarzanie dokumentów wsadowych czy bezpieczna wymiana danych.

---

*Miłego kodowania! Jeśli ten przewodnik był przydatny, rozważ podzielenie się nim z współpracownikami lub oznaczenie gwiazdką repozytorium Aspose.BarCode na GitHubie.*

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy macro PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak wygenerować kod kreskowy PDF417 w C# za pomocą Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Przykład Aspose barcode: generowanie Macro PDF417 w C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}