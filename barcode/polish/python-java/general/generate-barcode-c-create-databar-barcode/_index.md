---
category: general
date: 2026-07-21
description: Szybko generuj kod kreskowy w C# za pomocą Aspose.BarCode. Dowiedz się,
  jak tworzyć kod DataBar, dostosować rozmiar kodu kreskowego i wyeksportować obraz
  kodu kreskowego w kilku prostych krokach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: pl
lastmod: 2026-07-21
og_description: Generuj kod kreskowy w C# przy użyciu Aspose.BarCode. Utwórz kod DataBar,
  dostosuj jego rozmiar i natychmiast wyeksportuj obraz.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Generuj kod kreskowy C# – Twórz kody DataBar o niestandardowym rozmiarze
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Generuj kod kreskowy C# – Utwórz kod DataBar
url: /pl/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego C# – Tworzenie kodu DataBar

Chcesz **generate barcode C#** bez przeszukiwania niekończących się dokumentacji? Jesteś we właściwym miejscu. W tym przewodniku przeprowadzimy Cię przez tworzenie **DataBar barcode**, dostosowywanie jego wymiarów oraz ostateczne **exporting the barcode image** — wszystko przy użyciu kilku linijek C#.

Wyobraź sobie, że potrzebujesz kompaktowej etykiety produktu, która zmieści się na małej etykiecie półkowej. Symbolika DataBar Expanded Stacked rozwiązuje problem, a przy użyciu Aspose.BarCode możesz precyzyjnie kontrolować liczbę kolumn lub wierszy. Gotowy? Zanurzmy się.

## Co osiągniesz

- **Create a DataBar barcode** (wariant „expanded stacked”) od podstaw.  
- **Customize barcode size** poprzez bezpośrednie ustawienie kolumn lub wierszy.  
- **Change barcode dimensions** w locie, bez ponownego budowania generatora.  
- **Export barcode image** do PNG (lub dowolnego formatu obsługiwanego przez Aspose).  

Bez zewnętrznych usług, bez nieporządkowych konfiguracji — po prostu czysty, gotowy do uruchomienia kod C#.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również na .NET Framework 4.7+).  
- Ważna licencja Aspose.BarCode for .NET (lub możesz uruchomić w trybie próbnym).  
- IDE według własnego wyboru — Visual Studio, Rider lub VS Code będą odpowiednie.  

Jeśli jeszcze nie zainstalowałeś pakietu NuGet, uruchom:

```bash
dotnet add package Aspose.BarCode
```

To wszystko — żadnych innych zależności.

## Krok 1: Konfiguracja generatora kodów kreskowych (Jak **generate barcode C#**)

Najpierw potrzebujemy instancji `BarcodeGenerator` wskazującej na symbologię **DataBar Expanded Stacked**. Ten obiekt jest silnikiem, który później tworzy obraz.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Dlaczego to ważne*: Enum `EncodeTypes.DatabarExpandedStacked` informuje Aspose, że chcemy wersję stacked, co jest idealne dla wąskich przestrzeni. Tekst, który podajemy, staje się zakodowaną wartością; możesz go zamienić na dowolny ciąg numeryczny wymagany przez Twoją aplikację.

## Krok 2: **Customize barcode size** – ustaw kolumny

Kody DataBar pozwalają wpływać na gęstość wizualną, określając liczbę **columns** *lub* **rows**. Zacznijmy od kolumn. Liczba wierszy zostanie automatycznie obliczona, aby kod był prawidłowy.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Wskazówka*: Kolumny wpływają na szerokość kodu. Więcej kolumn → szerszy kod, co może poprawić niezawodność skanowania na drukarkach o niskiej rozdzielczości.

## Krok 3: **Export barcode image** z ustawieniem kolumn

Teraz zapisujemy obraz na dysk. Możesz wybrać PNG, JPEG, BMP lub nawet SVG. Oto PNG dla wyraźnego, bezstratnego wyniku.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Expected result** – Otwórz `DatabarCols4.png` i powinieneś zobaczyć starannie ułożony DataBar z czterema kolumnami. Wygląda jak gęsty stos pionowych pasków, idealny dla małej etykiety.

## Krok 4: **Change barcode dimensions** – ustaw wiersze zamiast tego

Czasami potrzebny jest wyższy kod zamiast szerszego. Przełącz się na kontrolę wierszy; Aspose automatycznie przeliczy kolumny.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Dlaczego przełączyć?* Wiersze wpływają na wysokość kodu. Więcej wierszy sprawia, że symbol jest wyższy, co może być przydatne, gdy masz pionową przestrzeń, ale ograniczoną szerokość.

## Krok 5: **Export barcode image** z ustawieniem wierszy

Zapisz drugą wersję. Zauważ, że nazwa pliku odzwierciedla zmianę; możesz także zachować oba obrazy do porównania.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Result** – `DatabarRows3.png` teraz wyświetla wyższą wersję tych samych danych, wciąż idealnie skanowalną.

## Pełny działający przykład

Łącząc wszystko razem, oto samodzielna aplikacja konsolowa, którą możesz skopiować i od razu uruchomić:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Uruchom program, a następnie otwórz dwa pliki PNG. Teraz **generated barcode C#**, **customized barcode size**, **changed barcode dimensions** i **exported the barcode image** — wszystko w mniej niż minutę.

## Częste pytania i przypadki brzegowe

- **What if I need a different image format?**  
  Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp`, `Gif` lub `Svg`. API automatycznie obsługuje konwersję.

- **Can I change both rows and columns simultaneously?**  
  Technicznie możesz ustawić oba, ale Aspose nada priorytet ostatniej zmienionej właściwości. Bezpieczniej jest ustawić *jedną* wymiar i pozwolić bibliotece obliczyć drugą, aby uzyskać prawidłowy DataBar.

- **How do I apply a foreground/background color?**  
  Użyj `barcodeGen.Parameters.Barcode.ForegroundColor` i `BackgroundColor`. Przykład:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked obsługuje do 74 znaków numerycznych (lub 30 alfanumerycznych). Przekroczenie tego limitu powoduje wyrzucenie wyjątku.

## Kolejne kroki

Teraz, gdy opanowałeś podstawy **create databar barcode**, rozważ:

- Dodanie **text annotations** pod kodem (`barcodeGen.Parameters.CaptionAbove.Text`).
- Osadzenie PNG bezpośrednio w PDF przy użyciu Aspose.PDF.
- Generowanie kodów kreskowych masowo poprzez iterację po pliku CSV z identyfikatorami produktów.

Każdy z tych tematów opiera się na tym samym obiekcie `BarcodeGenerator`, więc nie będziesz musiał zaczynać od zera.

---

**Bottom line**: teraz wiesz, jak **generate barcode C#**, **customize barcode size**, **change barcode dimensions** i **export barcode image** przy użyciu Aspose.BarCode. Eksperymentuj z wartościami kolumn/wierszy, zmieniaj formaty obrazów i integruj kod w swoim systemie inwentaryzacji lub POS. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera pełne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generowanie obrazu kodu kreskowego – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generowanie kodu DataMatrix – Profesjonalny przewodnik z Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}