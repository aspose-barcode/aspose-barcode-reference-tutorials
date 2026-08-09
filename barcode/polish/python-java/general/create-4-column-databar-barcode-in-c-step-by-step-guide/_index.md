---
category: general
date: 2026-08-09
description: Szybko utwórz kod kreskowy 4‑kolumnowy databar w C# przy użyciu Aspose.BarCode.
  Dowiedz się, jak skonfigurować kolumny, wiersze i zapisać obrazy PNG w tym zwięzłym
  przewodniku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create 4‑column databar barcode
- databar expanded stacked
- barcode generator c#
- set barcode rows
- barcode image format
language: pl
lastmod: 2026-08-09
og_description: Utwórz kod kreskowy 4‑kolumnowy databar w C# przy użyciu Aspose.BarCode,
  a następnie dostosuj wiersze i wyeksportuj obrazy PNG dla swojej aplikacji.
og_image_alt: Screenshot of a 4‑column DataBar Expanded Stacked barcode generated
  in C#
og_title: Utwórz kod kreskowy databar 4‑kolumnowy w C# – szybki samouczek
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  headline: Create 4‑column databar barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create 4‑column databar barcode in C# quickly with Aspose.BarCode.
    Learn how to configure columns, rows, and save PNG images in this concise guide.
  name: Create 4‑column databar barcode in C# – step‑by‑step guide
  steps:
  - name: Configure DataBar Expanded Stacked columns
    text: If you need a different column count, simply change the integer assigned
      to `Columns`. The property accepts values from 1 to 4 for the expanded stacked
      variant.
  - name: Save the barcode image
    text: The `BarCodeImageFormat` enumeration provides several options (`Png`, `Jpeg`,
      `Bmp`, `Gif`, `Tiff`). PNG is loss‑less and works well for most web and desktop
      scenarios.
  - name: Set barcode rows dynamically
    text: 'You can compute the row count at runtime based on input data:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- DataBar
title: Tworzenie 4‑kolumnowego kodu kreskowego Databar w C# – przewodnik krok po kroku
url: /pl/python-java/general/create-4-column-databar-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy DataBar 4‑kolumnowy w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć 4‑kolumnowy kod kreskowy DataBar** w C#, ten samouczek pokaże Ci dokładnie, jak to zrobić. Przejdziemy przez generowanie kodu kreskowego DataBar Expanded Stacked, skonfigurowanie czterech kolumn i zapisanie wyniku jako obrazu PNG.

W tym przewodniku nauczysz się, jak:

* Zainicjalizować `BarcodeGenerator` dla symbolu **DataBar Expanded Stacked**.  
* Ustawić liczbę kolumn na 4 (główny wymóg).  
* Skorygować liczbę wierszy, gdy potrzebny jest układ stosowany z trzema wierszami.  
* Wyeksportować kod kreskowy jako PNG przy użyciu odpowiedniego **formatu obrazu kodu kreskowego**.

Wystarczy biblioteka Aspose.BarCode for .NET (wersja 23.10 lub nowsza) oraz środowisko programistyczne .NET 6+ takie jak Visual Studio 2022. Nie są wymagane dodatkowe zależności.

---

## Jak utworzyć 4‑kolumnowy kod kreskowy DataBar

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator`, która obsługuje symbologię **DataBar Expanded Stacked**. Ta klasa kapsułkuje wszystkie opcje renderowania, co ułatwia przełączanie się między układami opartymi na kolumnach a układami opartymi na wierszach.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for DataBar Expanded Stacked
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        
        // 2️⃣ Set the barcode to use a 4‑column layout
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image as PNG
        generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to działa:**  
`EncodeTypes.DatabarExpandedStacked` informuje Aspose.BarCode, aby wygenerował wersję układaną (stacked) rodziny DataBar. Właściwość `DataBar.Columns` kontroluje, ile pionowych modułów zajmuje kod kreskowy. Ustawienie jej na 4 spełnia wymóg **utworzenia 4‑kolumnowego kodu kreskowego DataBar**. Na koniec, `Save` zapisuje wizualną reprezentację na dysk przy użyciu **formatu obrazu kodu kreskowego** `Png`.

### Konfiguracja kolumn DataBar Expanded Stacked

Jeśli potrzebujesz innej liczby kolumn, po prostu zmień liczbę całkowitą przypisaną do `Columns`. Właściwość akceptuje wartości od 1 do 4 dla wariantu Expanded Stacked.

```csharp
// Example: switch to a 2‑column layout
generator.Parameters.Barcode.DataBar.Columns = 2;
```

*Wskazówka:* Zawsze testuj wygenerowany kod kreskowy przy użyciu skanera obsługującego rodzinę DataBar, ponieważ sam wygląd wizualny nie gwarantuje czytelności.

### Zapisz obraz kodu kreskowego

Wyliczenie `BarCodeImageFormat` oferuje kilka opcji (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG jest bezstratny i dobrze sprawdza się w większości scenariuszy webowych i desktopowych.

```csharp
generator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
```

Jeśli potrzebujesz innego formatu, zamień `Png` na żądaną wartość wyliczenia. Zapisany plik może być osadzony bezpośrednio w HTML, PDF‑ach lub wydrukowany na etykietach.

## Utwórz kod kreskowy z niestandardowymi wierszami

Czasami potrzebny jest układ stosowany (stacked) z określoną liczbą wierszy zamiast kolumn. Ta sama klasa `BarcodeGenerator` udostępnia właściwość `Rows` w tym celu.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class RowExample
{
    static void Main()
    {
        // 1️⃣ Initialise a generator for the same symbology
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the barcode to use a 3‑row layout
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 3️⃣ Save the image as PNG
        rowGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego wiersze mają znaczenie:**  
Gdy kod kreskowy w układzie stacked jest wyższy niż szerszy, właściwość `Rows` określa, na ile poziomych części podzielony jest symbol. Ustawienie `Rows = 3` tworzy trzy‑wierszowy kod kreskowy stacked, co jest przydatne przy wąskich szerokościach etykiet.

### Ustaw wiersze kodu kreskowego dynamicznie

Możesz obliczyć liczbę wierszy w czasie wykonywania na podstawie danych wejściowych:

```csharp
int desiredRows = GetRowsFromUser(); // your custom logic
rowGenerator.Parameters.Barcode.DataBar.Rows = desiredRows;
```

Ta elastyczność pozwala **ustawić wiersze kodu kreskowego** bez konieczności rekompilacji aplikacji.

## Pełny przykład end‑to‑end

Poniżej znajduje się pojedynczy program, który generuje zarówno kod kreskowy 4‑kolumnowy, jak i 3‑wierszowy, demonstrując, jak obie konfiguracje mogą współistnieć.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class FullExample
{
    static void Main()
    {
        // ---------- 4‑column barcode ----------
        BarcodeGenerator colGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4; // create 4‑column databar barcode
        colGen.Save("DatabarCols4.png", BarCodeImageFormat.Png);

        // ---------- 3‑row barcode ----------
        BarcodeGenerator rowGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3; // set barcode rows to 3
        rowGen.Save("DatabarRows3.png", BarCodeImageFormat.Png);

        // Output confirmation
        System.Console.WriteLine("Barcodes generated:");
        System.Console.WriteLine(" - DatabarCols4.png (4 columns)");
        System.Console.WriteLine(" - DatabarRows3.png (3 rows)");
    }
}
```

**Oczekiwany wynik:**  
Dwa pliki PNG pojawiają się w katalogu roboczym aplikacji:

* `DatabarCols4.png` – kod kreskowy DataBar Expanded Stacked z czterema pionowymi kolumnami.  
* `DatabarRows3.png` – ta sama symbologia ułożona w trzy poziome wiersze.

Oba obrazy można otworzyć w dowolnym przeglądarce obrazów lub osadzić w kontrolce UI.

---

## Częste pytania i przypadki brzegowe

| Question | Answer |
|----------|--------|
| *Czy mogę użyć innej symbologii kodu kreskowego?* | Tak. Zastąp `EncodeTypes.DatabarExpandedStacked` inną wartością `EncodeTypes` (np. `EncodeTypes.QR`), ale właściwości `Columns` i `Rows` są specyficzne dla rodzin DataBar. |
| *Co jeśli ciąg danych przekracza maksymalną długość?* | Symbologia DataBar Expanded Stacked obsługuje maksymalnie 61 znaków numerycznych. Przekroczenie tego limitu powoduje wyrzucenie `ArgumentException`. Zweryfikuj dane wejściowe przed przypisaniem ich do generatora. |
| *Czy muszę zwolnić zasoby `BarcodeGenerator`?* | `BarcodeGenerator` implementuje `IDisposable`. W długotrwałej usłudze, otocz go blokiem `using` lub wywołaj `Dispose()` ręcznie, aby zwolnić zasoby natywne. |
| *Czy mogę generować SVG zamiast PNG?* | Oczywiście. Użyj `BarCodeImageFormat.Svg` w metodzie `Save`. |
| *Czy biblioteka jest kompatybilna z .NET Core?* | Aspose.BarCode for .NET obsługuje .NET Core 3.1, .NET 5, .NET 6 i nowsze. Nie są wymagane zmiany w kodzie. |

## Podsumowanie

Teraz wiesz, jak **utworzyć 4‑kolumnowy kod kreskowy DataBar** w C# przy użyciu Aspose.BarCode, jak dostosować układ przy użyciu wierszy oraz jak wyeksportować wynik w wygodnym **formacie obrazu kodu kreskowego**. Pełny przykład pokazuje zarówno konfiguracje oparte na kolumnach, jak i na wierszach, dając solidną podstawę dla każdego scenariusza drukowania etykiet lub skanowania mobilnego.

**Kolejne kroki**

* Eksperymentuj z różnymi ładunkami danych i weryfikuj kompatybilność ze skanerami.  
* Zbadaj dodatkowe opcje stylizacji, takie jak kolory pierwszego planu/tła (`generator.Parameters.Barcode.Color`).  
* Połącz kod kreskowy z innymi grafikami przy użyciu API `Graphics` w celu stworzenia niestandardowych projektów etykiet.  

Śmiało dostosuj kod do projektów ASP.NET Core, Windows Forms lub Xamarin — Aspose.BarCode działa na wszystkich platformach .NET. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Następujące samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obraz kodu kreskowego DotCode – wiersze i kolumny (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Utwórz obraz kodu kreskowego c# – Konfiguracja wierszy i kolumn Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Jak utworzyć rozszerzony kod tekstowy dotcode przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}