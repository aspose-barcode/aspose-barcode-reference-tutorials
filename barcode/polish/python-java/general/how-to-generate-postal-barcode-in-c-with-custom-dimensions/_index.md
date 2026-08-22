---
category: general
date: 2026-08-22
description: Poznaj sposób generowania kodu kreskowego pocztowego w C# oraz kontrolowania
  wysokości kreski, wymiaru X i formatu obrazu przy użyciu biblioteki generatora kodów
  kreskowych C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: pl
lastmod: 2026-08-22
og_description: Generuj kod kreskowy pocztowy w C# z pełną kontrolą nad wysokością
  pasków, wymiarem X i formatem obrazu. Postępuj zgodnie z tym samouczkiem krok po
  kroku, aby stworzyć idealne symbole pocztowe.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Wygeneruj kod kreskowy pocztowy w C# – pełny przewodnik z własnym rozmiarem
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Jak wygenerować kod kreskowy pocztowy w C# z niestandardowymi wymiarami
url: /pl/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy pocztowy w C# z niestandardowymi wymiarami

Jeśli potrzebujesz generować kod kreskowy pocztowy w C#, ten przewodnik pokaże Ci kompletny przepływ pracy. Zobaczysz, jak kontrolować wysokość pasków, dostosować wymiar X kodu kreskowego oraz wybrać odpowiedni format obrazu kodu kreskowego.

Kody kreskowe pocztowe są używane przez usługi pocztowe na całym świecie, a niezawodna implementacja musi zapewniać spójne wymiary w różnych symbologiach. W tym tutorialu nauczysz się korzystać z klasy **BarcodeGenerator**, zmieniać szerokość kodu kreskowego i zapisywać wynik jako PNG, JPEG lub inny obsługiwany format.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany  
* Odwołanie do pakietu NuGet **Aspose.BarCode** (lub dowolnej kompatybilnej biblioteki generatora kodów kreskowych w C#)  
* Podstawową znajomość składni C# oraz Visual Studio lub ulubionego IDE  

Nie potrzebujesz żadnych zewnętrznych usług; kod działa w pełni na komputerze klienta.

## Krok 1: Konfiguracja projektu i import przestrzeni nazw

Utwórz nową aplikację konsolową i dodaj bibliotekę kodów kreskowych. Poniższe instrukcje `using` dają dostęp do generatora i wyliczeń formatów obrazu.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

Klasa `BarcodeGenerator` jest rdzeniem API generatora kodów kreskowych w C#. Tworzy obiekt, który przechowuje wszystkie parametry renderowania.

## Krok 2: Wygenerowanie podstawowego kodu kreskowego pocztowego z domyślnymi wymiarami

Pierwszy przykład tworzy kod Planet przy użyciu domyślnej wysokości pasków. Demonstracja minimalnej konfiguracji potrzebnej do wygenerowania kodu kreskowego pocztowego.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Dlaczego to działa*: Gdy pomijasz właściwość `BarHeight`, biblioteka stosuje standardową wysokość zdefiniowaną dla wybranej symbologii. `XDimension` kontroluje **wymiar X kodu kreskowego**, co bezpośrednio wpływa na całkowitą szerokość symbolu.

## Krok 3: Zmiana szerokości kodu kreskowego i zwiększenie wysokości pasków

Często potrzebny jest wyższy pasek, aby spełnić określone wytyczne pocztowe. Poniższy kod ustawia niestandardową wysokość pasków na 100 pikseli, zachowując tę samą wartość X.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Dlaczego regulować wysokość*: Właściwość `BarHeight` kontroluje pionowy rozmiar każdego paska. Dla usług pocztowych wymagających minimalnej wysokości, ustawienie tej wartości zapewnia zgodność bez wpływu na kodowanie.

## Krok 4: Wygenerowanie kodu RM4SCC z ustawieniami domyślnymi

RM4SCC to kolejna popularna symbologia pocztowa. Poniższy kod odzwierciedla przykład Planet, ale zmienia wyliczenie `EncodeTypes`.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Ponieważ biblioteka automatycznie wybiera odpowiednią domyślną wysokość dla RM4SCC, otrzymujesz obraz zgodny ze standardem przy użyciu jednego wiersza kodu.

## Krok 5: Zmiana wysokości pasków dla kodu RM4SCC

Jeśli system pocztowy wymaga wyższego paska, możesz zmodyfikować wysokość dokładnie tak, jak zrobiłeś to dla Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Wskazówka*: Wyliczenie **formatu obrazu kodu kreskowego** zawiera `Jpeg`, `Bmp`, `Tiff` i `Gif`. Wybierz format, który pasuje do Twojego łańcucha przetwarzania danych.

## Krok 6: Eksploracja innych formatów obrazu i precyzyjne dostrajanie wymiarów

Poniżej znajduje się kompaktowy fragment kodu, który pokazuje, jak przełączać format wyjściowy i eksperymentować z różnymi wymiarami X.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Dlaczego iterować*: Pętla generuje macierz obrazów ilustrującą, jak **zmiana szerokości kodu kreskowego** (poprzez wymiar X) wpływa na ogólny wygląd. Pokazuje również, że ten sam generator może wyprowadzać wiele typów **formatu obrazu kodu kreskowego** bez dodatkowych zmian w kodzie.

## Typowe pułapki i jak ich unikać

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| Paski wydają się zbyt cienkie | Wymiar X ustawiony na 1 piksel lub mniej | Ustaw `XDimension.Pixels` na co najmniej 2 dla czytelności |
| Obraz jest rozmyty | Zapis jako JPEG z wysoką kompresją | Użyj `BarCodeImageFormat.Png` dla wyjścia bezstratnego |
| Nieoczekiwany rozmiar przy druku | DPI nie uwzględnione | Ustaw `barcodeGenerator.Parameters.ImageResolution.Dpi`, jeśli drukarka wymaga konkretnego DPI |
| Nieprawidłowa symbologia | Użycie `EncodeTypes.Planet` dla danych RM4SCC | Wybierz właściwą wartość `EncodeTypes`, która odpowiada specyfikacji usługi pocztowej |

## Weryfikacja wyniku

Po uruchomieniu kodu otwórz dowolny z wygenerowanych plików PNG. Powinieneś zobaczyć wyraźny, prostokątny kod kreskowy z równomiernymi pionowymi paskami. Wysokość pasków będzie odpowiadać ustawionej wartości (np. 100 pikseli), a całkowita szerokość odzwierciedli **wymiar X kodu kreskowego**, który skonfigurowałeś.

Jeśli potrzebujesz osadzić obraz na stronie internetowej, format PNG działa natywnie w przeglądarkach. Dla raportów PDF możesz przekonwertować PNG na tablicę bajtów i wstawić go przy użyciu biblioteki PDF.

## Pełny przykład – wszystkie kroki w jednym programie

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

Uruchomienie tego programu tworzy cztery pliki PNG w `C:\Barcodes\`. Każdy plik demonstruje inną kombinację **generowania kodu kreskowego pocztowego**, **wymiaru X kodu kreskowego** i **formatu obrazu kodu kreskowego**.

## Zakończenie

Teraz wiesz, jak generować kod kreskowy pocztowy w C# i w pełni kontrolować wysokość pasków, szerokość modułu oraz format wyjściowy. Dostosowując **wymiar X kodu kreskowego** i używając odpowiedniego **formatu obrazu kodu kreskowego**, możesz spełnić dowolną specyfikację pocztową i integrować symbole w aplikacjach desktopowych, webowych lub mobilnych.

Następnie odkryj zaawansowane funkcje, takie jak dodawanie tekstu czytelnego dla człowieka, stosowanie palet kolorów lub osadzanie kodu kreskowego w dokumentach PDF. Te tematy wykorzystują te same koncepcje **generatora kodów kreskowych C#**, które właśnie opanowałeś, więc możesz z pewnością rozwijać tę bazę.

## Co powinieneś się nauczyć dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które budują na technikach przedstawionych w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i eksplorować alternatywne podejścia implementacyjne w własnych projektach.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}