---
category: general
date: 2026-08-03
description: Samouczek generatora kodów kreskowych w C# pokazuje, jak wygenerować
  obraz kodu kreskowego przy użyciu Aspose.BarCode, ustawić kolumny i wiersze oraz
  zapisać pliki PNG dla DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: pl
lastmod: 2026-08-03
og_description: Samouczek generatora kodów kreskowych w C# wyjaśnia, jak generować
  obraz kodu kreskowego przy użyciu Aspose.BarCode, konfigurować kolumny i wiersze
  DataBar Expanded Stacked oraz zapisywać pliki PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generator kodów kreskowych C# – przewodnik krok po kroku generowania obrazu
  kodu kreskowego
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator kodów kreskowych C# – generuj obraz kodu kreskowego
url: /pl/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator kodów kreskowych C# – generowanie obrazu kodu kreskowego

Jeśli potrzebujesz generatora kodów kreskowych C#, który potrafi generować obraz kodu kreskowego dla DataBar Expanded Stacked, ten przewodnik poprowadzi Cię przez cały proces. Dowiesz się, jak skonfigurować ustawienia kolumn i wierszy, zapisać wynik jako PNG oraz dostosować kod do innych symbologii.

Programowe generowanie obrazów kodów kreskowych eliminuje ręczne kroki i zapewnia spójność w fakturach, etykietach wysyłkowych i systemach magazynowych. Ten tutorial obejmuje wszystko, czego potrzebujesz – od konfiguracji projektu po pełny kod źródłowy, abyś mógł od razu uruchomić przykład.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany  
* IDE, takie jak Visual Studio 2022 (dowolny edytor obsługujący C#)  
* Licencję na **Aspose.BarCode for .NET** – darmowa wersja ewaluacyjna wystarczy do testów  
* Podstawową znajomość składni C#  

Jeśli którekolwiek z tych elementów brakuje, zainstaluj .NET SDK ze strony dotnet.microsoft.com i pobierz pakiet Aspose.BarCode NuGet przy pomocy:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz projekt generatora kodów kreskowych C#

Utwórz nową aplikację konsolową i dodaj wymagane dyrektywy `using`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

Klasa `BarcodeGenerator` jest rdzeniem API generatora kodów kreskowych C#. Otrzymuje ona typ symbologii oraz tekst do zakodowania.

## Krok 2: Wygeneruj kod DataBar Expanded Stacked i ustaw kolumny

Pierwszy przykład tworzy kod kreskowy z czterema kolumnami. Zmiana właściwości `Columns` wpływa na gęstość wizualną symbologii DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Dlaczego to ważne:** Liczba kolumn wpływa na ilość danych, które można przechować w kompaktowej przestrzeni. Ustawienie jej na 4 tworzy szerszy kod kreskowy, który pozostaje czytelny dla większości skanerów.

## Krok 3: Wygeneruj kod kreskowy z niestandardową liczbą wierszy

Drugi przykład pokazuje, jak kontrolować układ pionowy, ustawiając właściwość `Rows`. Konfiguracja trzech wierszy jest przydatna, gdy potrzebny jest wyższy kod kreskowy przy ograniczonej przestrzeni poziomej.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Dlaczego to ważne:** Dostosowanie liczby wierszy pozwala zmieścić kod kreskowy w wąskiej kolumnie, zachowując czytelność. Generator kodów kreskowych C# automatycznie przelicza rozmiar modułu, aby spełnić specyfikację.

## Krok 4: Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się samodzielny program, który łączy poprzednie kroki. Skopiuj kod do pliku `Program.cs`, zamień `YOUR_DIRECTORY` na istniejącą ścieżkę folderu i uruchom aplikację.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Oczekiwany wynik

Po uruchomieniu programu w docelowym katalogu pojawią się dwa pliki PNG:

* **DatabarCols4.png** – kod DataBar Expanded Stacked z czterema kolumnami  
* **DatabarRows3.png** – te same dane zakodowane w trzech wierszach  

Otwórz obrazy w dowolnym przeglądarce zdjęć; wyświetlają one ostre, skanowalne kody gotowe do druku lub osadzenia w plikach PDF.

## Jak wygenerować obraz kodu kreskowego o niestandardowych wymiarach

Jeśli potrzebujesz konkretnego rozmiaru obrazu, dostosuj właściwości `ImageHeight` i `ImageWidth` przed wywołaniem `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Zmiana wymiarów nie wpływa na zakodowane dane; jedynie skaluje ich wizualną reprezentację. Technika ta jest przydatna przy integracji kodów kreskowych w komponentach UI o stałych ograniczeniach układu.

## Typowe pułapki i wskazówki profesjonalistów

* **Separatory ścieżek:** Używaj łańcuchów dosłownych (`@"C:\Path\file.png"`) lub `Path.Combine`, aby uniknąć problemów ze znakami ucieczki w systemie Windows.  
* **Wymuszanie licencji:** Bez ważnej licencji wygenerowane obrazy zawierają znak wodny. Zastosuj licencję wcześnie w aplikacji:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Limity kodowania:** DataBar Expanded Stacked obsługuje maksymalnie 74 znaki numeryczne. Przekroczenie tego limitu powoduje wyjątek. Zweryfikuj długość wejścia przed utworzeniem generatora.  
* **Wydajność:** Ponowne użycie jednej instancji `BarcodeGenerator` do wielu zapisów zmniejsza alokację pamięci. Zmieniaj właściwości `Rows` lub `Columns` między zapisami tylko wtedy, gdy zakodowany tekst pozostaje ten sam.

## Kolejne kroki

Teraz, gdy potrafisz generować obrazy kodów kreskowych przy użyciu generatora kodów kreskowych C#, rozważ dalsze eksploracje:

* **Różne symbologie** – wypróbuj `EncodeTypes.QR`, `EncodeTypes.Code128` lub `EncodeTypes.Pdf417`.  
* **Dostosowanie kolorów** – ustaw `Parameters.Barcode.ForeColor` i `BackColor`, aby dopasować je do identyfikacji wizualnej marki.  
* **Osadzanie w PDF** – połącz wygenerowane PNG z Aspose.PDF, aby tworzyć dokumenty gotowe do druku.  

Te rozszerzenia pozwalają zbudować w pełni funkcjonalne rozwiązanie kodów kreskowych dla zastosowań w magazynach, logistyce lub handlu detalicznym.

---


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}