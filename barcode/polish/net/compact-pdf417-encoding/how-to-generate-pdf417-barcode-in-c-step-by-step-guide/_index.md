---
category: general
date: 2026-09-10
description: Szybko generuj kod kreskowy PDF417 w C#. Dowiedz się, jak generować PDF417
  i jak zmienić rozmiar kodu kreskowego za pomocą Aspose.BarCode w kilku linijkach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: pl
lastmod: 2026-09-10
og_description: Generuj kod kreskowy PDF417 w C# natychmiast. Ten samouczek pokazuje,
  jak wygenerować PDF417 i jak zmienić rozmiar kodu kreskowego przy użyciu Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz zwięzły, gotowy do uruchomienia przykład, który tworzy kod kreskowy PDF417, pozwala kontrolować jego rozmiar i zapisuje wynik jako obraz PNG.

Generowanie kodu kreskowego PDF417 jest powszechnym wymogiem w systemach inwentaryzacji, kartach pokładowych i śledzeniu dokumentów. W tym samouczku omawiamy także **jak zmienić rozmiar kodu kreskowego**, aby kod dostosowywał się do różnych potrzeb drukowania lub wyświetlania na ekranie.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+)
* Visual Studio 2022 lub dowolne IDE C#
* Pakiet NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Podstawowa znajomość aplikacji konsolowych C#

## Project setup

1. Utwórz nowy projekt konsolowy:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Dodaj odwołanie do Aspose.BarCode (zobacz wymagania wstępne).  

3. Otwórz `Program.cs` i zamień jego zawartość na pełny przykład poniżej.

## Step 1: Generate PDF417 barcode

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` skonfigurowanej dla symbologii **PDF417**. Ten obiekt jest punktem wejścia dla wszystkich operacji na kodach kreskowych.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Dlaczego to ważne* – Wartość wyliczenia `EncodeTypes.Pdf417` informuje Aspose.BarCode, aby użył standardu PDF417, a drugi argument dostarcza danych, które będą kodowane. Generator posiada teraz pełny obiekt kodu kreskowego, który możesz dostosować przed zapisaniem.

## Step 2: How to change barcode size (module size)

Kody PDF417 składają się z małych kwadratowych modułów. Dostosowanie rozmiaru modułu zmienia ogólne wymiary obrazu bez zmiany kodowanych danych.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Dlaczego to ważne* – Większy `XDimension` daje większy kod kreskowy odpowiedni do druku w wysokiej rozdzielczości; mniejsza wartość jest lepsza dla wyświetlania na ekranie. Domyślnie jest to zazwyczaj 1 px, co może wyglądać ciasno na nowoczesnych monitorach.

## Step 3: Configure layout – columns and rows

PDF417 pozwala określić liczbę kolumn i wierszy, co wpływa zarówno na kształt kodu, jak i jego zdolność korekcji błędów.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Dlaczego to ważne* – Więcej kolumn sprawia, że kod jest szerszy, a więcej wierszy – wyższy. Dostosuj te wartości, aby pasowały do dostępnej przestrzeni w interfejsie użytkownika lub na etykiecie drukowanej.

## Step 4: Save the barcode image

Na koniec zapisz kod kreskowy do pliku. Używamy PNG, ponieważ zachowuje ostre krawędzie i obsługuje przezroczystość.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Uruchomienie programu tworzy `LayoutPdf417.png` w folderze wyjściowym projektu. Obraz będzie wyglądał tak:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="generate PDF417 barcode example showing 4 columns and 9 rows"}

*Wskazówka*: Jeśli potrzebujesz innego formatu obrazu (JPEG, BMP, TIFF), zamień `BarCodeImageFormat.Png` na odpowiednią wartość wyliczenia.

## How to generate PDF417 – alternative data sources

Powyższy kod używa na sztywno zapisanego ciągu `"Layout test"`. W rzeczywistych scenariuszach często pobierasz dane z bazy danych, pliku lub wejścia użytkownika.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Reszta kroków (rozmiar, układ, zapisywanie) pozostaje niezmieniona. To pokazuje **jak wygenerować PDF417** z dynamicznych źródeł bez dodatkowej złożoności.

## Common pitfalls and how to avoid them

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Kod kreskowy jest rozmyty | `XDimension` ustawiono zbyt nisko dla rozdzielczości wyjściowej | Zwiększ `XDimension.Pixels` lub zapisz w formacie wektorowym, takim jak SVG (`BarCodeImageFormat.Svg`) |
| Tekst nie mieści się w wybranym układzie | Zbyt wiele znaków dla wybranych wierszy/kolumn | Zredukuj liczbę wierszy/kolumn lub podziel dane na wiele kodów kreskowych |
| Plik obrazu nie został utworzony | Folder wyjściowy nie istnieje lub brakuje uprawnień do zapisu | Upewnij się, że katalog istnieje (`Directory.CreateDirectory`) i aplikacja ma odpowiednie uprawnienia |

## Verifying the barcode

Po wygenerowaniu obrazu możesz go zweryfikować przy użyciu dowolnej aplikacji skanującej PDF417 (telefony komórkowe mają darmowe skanery) lub wbudowanego czytnika Aspose.BarCode:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Jeśli wynik zgadza się z oryginalnym tekstem, proces **generowania kodu kreskowego PDF417** zakończył się sukcesem.

## Full, runnable example

Poniżej znajduje się kompletny program, który możesz skopiować i wkleić do `Program.cs`. Zawiera wszystkie dyrektywy using, obsługę błędów i komentarze.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Uruchomienie tego programu wypisuje:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Masz teraz **kompletną, samodzielną rozwiązanie** do generowania kodów kreskowych PDF417 i kontrolowania ich rozmiaru.

## Conclusion

W tym samouczku nauczyłeś się, jak **wygenerować kod kreskowy PDF417** w C# przy użyciu Aspose.BarCode, jak **zmienić rozmiar kodu kreskowego** poprzez regulację wymiaru X oraz jak konfigurować kolumny i wiersze w celu kontroli układu. Pokazaliśmy także, jak programowo zweryfikować wynik i jak dostosować kod do danych dynamicznych.

Następnie możesz zgłębić:

* **Jak generować PDF417** z dostosowywaniem poziomu korekcji błędów (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Eksport do **formatów wektorowych** (SVG, EPS) dla nieskończonego skalowania
* Osadzanie kodu kreskowego w dokumencie PDF przy użyciu **Aspose.PDF**

Eksperymentuj z różnymi rozmiarami modułów i opcjami układu, aby dopasować je do konkretnych wymagań UI lub druku. Szczęśliwego kodowania!

## What Should You Learn Next?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 z Aspose – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [dostosuj rozmiar kodu kreskowego – przewodnik C# do generowania kodów PDF417](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Jak zapisać kod kreskowy w C# – generowanie kodów PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}