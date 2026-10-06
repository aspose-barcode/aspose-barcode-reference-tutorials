---
category: general
date: 2026-09-16
description: Dowiedz się, jak ustawić szerokość, jak tworzyć puste paski oraz jak
  wypełniać paski podczas generowania kodu kreskowego Planet przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: pl
lastmod: 2026-09-16
og_description: Jak ustawić szerokość, tworzyć puste paski i wypełniać paski podczas
  generowania kodu kreskowego Planet przy użyciu Aspose.BarCode – kompletny przewodnik
  krok po kroku.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Jak ustawić szerokość i wygenerować kod kreskowy Planet w C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak ustawić szerokość i wygenerować kod kreskowy Planet w C#
url: /pl/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić szerokość i wygenerować kod kreskowy Planet w C#

Jeśli potrzebujesz **jak ustawić szerokość** dla kodu kreskowego Planet, ten przewodnik pokazuje kompletny proces. Zobaczysz także **jak zrobić puste** paski, **jak wypełnić paski**, oraz dokładne kroki **generowania kodu kreskowego Planet** przy użyciu Aspose.BarCode dla .NET.

Generowanie kodu kreskowego w stylu pocztowym Planet jest powszechne przy tworzeniu aplikacji etykiet mailingowych lub integracji z usługami pocztowymi. Po zakończeniu tego samouczka będziesz mieć gotowy do uruchomienia program konsolowy, który tworzy zarówno obraz z wypełnionymi paskami, jak i obraz z pustymi paskami, używając tego samego ciągu danych.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 lub dowolne IDE kompatybilne z C#
- Pakiet NuGet Aspose.BarCode dla .NET (`Aspose.BarCode`)  
  Zainstaluj za pomocą:

```bash
dotnet add package Aspose.BarCode
```

Nie wymaga dodatkowej konfiguracji; biblioteka obsługuje kodowanie obrazu wewnętrznie.

## Krok 1: Utwórz projekt konsolowy i dodaj bibliotekę

Otwórz terminal i uruchom:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Tworzy to plik `Program.cs`, w którym napiszemy logikę kodu kreskowego.

## Krok 2: Napisz kod – jak ustawić szerokość i wygenerować kod kreskowy Planet

Otwórz `Program.cs` i zamień jego zawartość na poniższy kompletny przykład:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Dlaczego każdy krok ma znaczenie

- **Jak ustawić szerokość**: Właściwość `XDimension.Pixels` bezpośrednio wpływa na fizyczny rozmiar każdego paska. Wybranie wartości od 2 do 6 pikseli zapewnia równowagę między czytelnością na ekranie a jakością druku.
- **Jak zrobić puste**: Ustawienie `FilledBars = false` nakazuje generatorowi rysowanie jedynie konturów pasków. Ten styl jest przydatny przy druku „światło‑na‑ciemności” lub gdy chcesz, aby widoczna była tekstura papieru.
- **Jak wypełnić paski**: Domyślne `FilledBars = true` tworzy solidne czarne paski, co jest standardem dla większości skanerów pocztowych.
- **Generowanie kodu kreskowego Planet**: Użycie `EncodeTypes.Planet` wybiera specyficzne kodowanie wymagane przez United States Postal Service (USPS) dla kodów Planet.

## Krok 3: Zbuduj i uruchom program

Z folderu projektu wykonaj:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście konsoli podobne do:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

W katalogu projektu pojawiają się dwa pliki PNG:

- `PostalPlanetFilledBars.png` – solidne czarne paski (domyślny styl)
- `PostalPlanetEmptyBars.png` – kontur pasków (styl pusty)

Otwórz je w dowolnym przeglądarce obrazów, aby zweryfikować, że szerokość paska odpowiada ustawieniu 4 piksele oraz że wersja pusta pokazuje nie wypełnione paski.

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|--------|
| *Czy mogę użyć innego formatu obrazu?* | Tak. Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Gif` w zależności od potrzeb. |
| *Co zrobić, jeśli kod kreskowy stanie się zbyt szeroki dla mojej etykiety?* | Zmniejsz `XDimension.Pixels` (np. do `2`) lub zwiększ szerokość modułu drukarki etykiet. |
| *Czy muszę ręcznie ustawiać `Height`?* | Biblioteka automatycznie oblicza wysokość na podstawie kodowania. Możesz nadpisać ją za pomocą `Parameters.Barcode.BarHeight`. |
| *Czy styl pustych pasków jest obsługiwany przez wszystkie drukarki?* | Większość nowoczesnych drukarek termicznych obsługuje zarówno wypełnione, jak i puste style, ale sprawdź to przy pomocy testowego wydruku, jeśli używasz starszego urządzenia. |
| *Jak dodać czytelną dla człowieka etykietę pod kodem kreskowym?* | Użyj `Parameters.Caption`, aby włączyć i sformatować etykietę; ustaw `CaptionAbove` na `false`, aby umieścić ją poniżej. |

## Porady profesjonalne

- **Ponowne użycie tego samego generatora** tylko wtedy, gdy wszystkie parametry pozostają identyczne. Zmiana `FilledBars` po zapisaniu nie wpływa na już zapisany obraz, więc ponowne utworzenie instancji (jak pokazano) zapewnia czysty start.
- **Generowanie wsadowe**: Umieść kod w pętli i zmieniaj `data` w każdej iteracji, aby stworzyć serię kodów Planet dla masowej wysyłki.
- **Wydajność**: Przy tysiącach kodów kreskowych utwórz jedną instancję `BarcodeGenerator`, dostosuj `XDimension` i `FilledBars` w razie potrzeby i ponownie używaj obiektu, aby zmniejszyć alokacje pamięci.

## Zakończenie

Teraz wiesz **jak ustawić szerokość**, **jak zrobić puste**, **jak wypełnić paski** oraz dokładne kroki **generowania kodu kreskowego Planet** przy użyciu Aspose.BarCode w C#. Kompletny, działający przykład tworzy zarówno pliki PNG z wypełnionymi, jak i pustymi paskami, gotowe do integracji w dowolnym procesie etykietowania.

Następnie odkryj powiązane tematy, takie jak **jak dodać kody QR do tej samej etykiety**, **personalizacja kolorów kodu kreskowego** lub **osadzanie kodu kreskowego w dokumencie PDF**. Każdy z nich opiera się na tych samych podstawach przedstawionych tutaj. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obraz kodu kreskowego Planet w C# – Jak wygenerować kod pocztowy](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Jak utworzyć kod kreskowy Code128 z pustymi paskami w Javie](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Jak wygenerować obraz kodu kreskowego w Javie przy użyciu Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}