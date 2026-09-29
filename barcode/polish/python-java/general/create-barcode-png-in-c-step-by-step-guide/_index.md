---
category: general
date: 2026-08-03
description: Utwórz plik PNG z kodem kreskowym w C# i dowiedz się, jak zmienić proporcje
  obrazu DataBar. Skorzystaj z tego pełnego przykładu z kodem i wskazówkami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: pl
lastmod: 2026-08-03
og_description: Utwórz plik PNG z kodem kreskowym w C# i zobacz, jak zmienić proporcje
  dla kodów DataBar. Ten przewodnik dostarcza gotowy do uruchomienia kod oraz praktyczne
  wskazówki.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Utwórz plik PNG z kodem kreskowym w C# – pełny przykład z kontrolą proporcji
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Tworzenie pliku PNG z kodem kreskowym w C# – przewodnik krok po kroku
url: /pl/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz plik PNG z kodem kreskowym w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć plik PNG z kodem kreskowym** w C#, ten poradnik pokaże Ci dokładnie, jak to zrobić. Wygenerujesz stosowany omnidirectional DataBar, zapiszesz go jako plik PNG i dowiesz się **jak zmienić współczynnik proporcji**, aby dopasować go do różnych środowisk skanowania.

Poradnik obejmuje wszystko, czego potrzebujesz: wymagane pakiety, kompletny, gotowy do uruchomienia program oraz wyjaśnienia, dlaczego każde ustawienie ma znaczenie. Po zakończeniu będziesz mieć dwa pliki PNG — jeden z współczynnikiem proporcji 15 i drugi z 30 — gotowe do testów lub użycia w produkcji.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy zainstalowany
- Visual Studio 2022 (lub dowolne IDE C#)
- Odwołanie NuGet do **Aspose.BarCode** (biblioteka udostępniająca `BarcodeGenerator`)
- Uprawnienia do zapisu w katalogu, w którym będą zapisywane pliki PNG

Możesz dodać pakiet Aspose.BarCode za pomocą następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nową aplikację konsolową i zaimportuj przestrzenie nazw wymagane do generowania kodów kreskowych oraz operacji I/O.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Dlaczego to ważne:** Importowanie `Aspose.BarCode.Generation` daje dostęp do `BarcodeGenerator`. Trzymanie kodu wewnątrz `Main` sprawia, że przykład jest samodzielny i łatwy do uruchomienia.

## Krok 2: Utwórz generator kodu kreskowego dla stosowanego omnidirectional DataBar

Zainicjuj `BarcodeGenerator` z typem `EncodeTypes.DatabarStackedOmniDirectional` oraz przykładowym ciągiem danych GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Dlaczego to ważne:** Wybrany typ kodowania generuje wysokiej gęstości DataBar, który może być odczytany przez większość nowoczesnych skanerów. Ciąg danych jest zgodny z formatem GS1 Application Identifier (01), powszechnym dla identyfikatorów produktów.

## Krok 3: Zdefiniuj wymiar X (szerokość modułu) w pikselach

Ustaw szerokość modułu, aby kontrolować ogólny rozmiar kodu kreskowego bez wpływu na jego czytelność.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to ważne:** Wymiar X równy 2 pikselom daje kod kreskowy, który nie jest ani za mały dla skanerów, ani za duży dla typowych przestrzeni etykiet.

## Krok 4: Zapisz pierwszy plik PNG z współczynnikiem proporcji 15

Dostosuj współczynnik proporcji DataBar, a następnie zapisz obraz jako plik PNG.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Dlaczego to ważne:** Współczynnik proporcji kontroluje stosunek wysokości do szerokości stosowanego DataBar. Współczynnik 15 jest powszechnym domyślnym ustawieniem, które równoważy czytelność i wysokość etykiety.

## Krok 5: Zmień współczynnik proporcji na 30 i zapisz drugi plik PNG

Zmodyfikuj tę samą instancję generatora, aby używać większego współczynnika proporcji, a następnie zapisz drugi obraz.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Dlaczego to ważne:** Zwiększenie współczynnika proporcji rozciąga kod kreskowy w pionie, co może poprawić niezawodność skanowania na urządzeniach o niskiej rozdzielczości lub gdy etykieta jest drukowana na wąskim nośniku.

## Oczekiwany wynik

Uruchomienie programu tworzy dwa pliki PNG:

| Plik                               | Współczynnik proporcji | Przybliżone wymiary (piksele) |
|------------------------------------|------------------------|-------------------------------|
| `DatabarAspectRatio15.png`         | 15                     | 200 × 300 (szerokość × wysokość) |
| `DatabarAspectRatio30.png`         | 30                     | 200 × 600 (szerokość × wysokość) |

Oba obrazy zawierają wyraźny, możliwy do zeskanowania kod DataBar, który koduje identyfikator GS1 `(01)12345678901231`.

## Częste pytania i przypadki brzegowe

### Jak zmienić inne właściwości wizualne?

Możesz dostosować kolor pierwszego planu, kolor tła lub dodać tekst czytelny dla człowieka za pomocą obiektu `generator.Parameters.Barcode`. Na przykład:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Co zrobić, jeśli potrzebuję innego formatu obrazu?

Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Gif` w zależności od potrzeb. PNG pozostaje najlepszym wyborem dla bezstratnych obrazów kodów kreskowych.

### Czy współczynnik proporcji wpływa na szybkość skanowania?

Wyższe współczynniki proporcji zwiększają wysokość kodu kreskowego, co może poprawić niezawodność skanowania na urządzeniach, które mają problemy z krótkimi stosowanymi symbolami. Jednak bardzo wysokie kody kreskowe mogą nie zmieścić się na małych etykietach, dlatego przetestuj je na docelowym sprzęcie.

### Czy mogę generować wiele kodów kreskowych w pętli?

Tak. Utwórz nową instancję `BarcodeGenerator` dla każdego ciągu danych lub ponownie użyj tej samej instancji, aktualizując `CodeText` i `DataBar.AspectRatio`. To podejście zmniejsza narzut związany z alokacją obiektów.

## Porady profesjonalne

- **Reuse the generator**: Zmiana tylko `CodeText` lub `AspectRatio` unika ponownego tworzenia obiektu, co przyspiesza przetwarzanie wsadowe.
- **Validate the output**: Użyj skanera ręcznego lub aplikacji mobilnej, aby potwierdzić, że wygenerowany PNG odczytuje się poprawnie przed wdrożeniem do produkcji.
- **File naming**: Umieść współczynnik proporcji w nazwie pliku (jak pokazano), aby śledzić warianty podczas testów.

## Zakończenie

Teraz wiesz, jak **utworzyć pliki PNG z kodem kreskowym** w C# i dokładnie **jak zmienić współczynnik proporcji** dla stosowanych omnidirectional DataBar. Pełny przykład demonstruje inicjalizację, ustawienie wymiaru X, manipulację współczynnikiem proporcji oraz zapisywanie obrazu — wszystko w jednym, uruchamialnym programie.

Od tego momentu możesz eksplorować dodatkowe typy kodów kreskowych, eksperymentować z kolorami lub zintegrować generator z większym systemem raportowania lub inwentaryzacji. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe poradniki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz plik PNG z kodem kreskowym – Współczynnik proporcji DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak dostosować kod kreskowy – Współczynnik proporcji Codablock F z Aspose.BarCode dla .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}