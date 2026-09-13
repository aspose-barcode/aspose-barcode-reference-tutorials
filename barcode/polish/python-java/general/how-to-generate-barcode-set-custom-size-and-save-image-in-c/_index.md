---
category: general
date: 2026-09-13
description: Dowiedz się, jak generować kod kreskowy w C#, dostosować rozmiar kodu
  kreskowego i zapisać obraz kodu kreskowego jako PNG przy użyciu Aspose.BarCode.
  Kompletny przewodnik krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: pl
lastmod: 2026-09-13
og_description: Jak wygenerować kod kreskowy w C# z niestandardowym rozmiarem i zapisać
  obraz kodu kreskowego jako PNG. Przeczytaj ten kompletny przewodnik dla Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Jak wygenerować kod kreskowy, ustawić niestandardowy rozmiar i zapisać obraz
  w C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Jak wygenerować kod kreskowy, ustawić własny rozmiar i zapisać obraz w C#
url: /pl/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować zestaw kodów kreskowych o niestandardowym rozmiarze i zapisać obraz w C#

Jeśli potrzebujesz **jak wygenerować kod kreskowy** w aplikacji .NET, ten tutorial pokaże Ci pełne rozwiązanie. Zobaczysz, jak dostosować **niestandardowy rozmiar kodu kreskowego** oraz **zapisać obraz kodu kreskowego** przy użyciu kilku linii kodu C#.

Generowanie kodów kreskowych jest powszechnym wymogiem w systemach inwentaryzacji, etykietach wysyłkowych i aplikacjach punktu sprzedaży. Po zakończeniu tego przewodnika będziesz mieć działający program, który tworzy dwa kody DataBar‑Stacked‑Omnidirectional, każdy o innym współczynniku proporcji, i zapisuje je jako pliki PNG na dysku.

**Prerequisites**

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 lub dowolne IDE dla C#
- Aspose.BarCode for .NET (bezpłatna wersja próbna lub licencjonowany pakiet NuGet)

---

## Jak wygenerować kod kreskowy przy użyciu Aspose.BarCode

Biblioteka Aspose.BarCode ukrywa szczegóły niskiego poziomu standardów kodów kreskowych, pozwalając skupić się na danych, które chcesz zakodować, oraz na wyglądzie wizualnym, którego potrzebujesz.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Dlaczego każdy wiersz ma znaczenie

| Krok | Wyjaśnienie |
|------|-------------|
| **1️⃣ Utwórz generator** | Enum `EncodeTypes.DatabarStackedOmniDirectional` informuje Aspose, jaką symbologię kodu kreskowego użyć. Ciąg `"(01)12345678901231"` jest zgodny z formatem danych GS1‑128, gdzie `(01)` jest identyfikatorem aplikacji dla GTIN. |
| **2️⃣ Ustaw wymiar X** | `XDimension.Pixels` definiuje szerokość pojedynczego modułu kodu kreskowego (najmniejszego paska). Zmiana tej wartości jest podstawowym sposobem uzyskania **niestandardowego rozmiaru kodu kreskowego** bez modyfikacji zakodowanych danych. |
| **3️⃣ Ustaw proporcje i zapisz** | `DataBar.AspectRatio` kontroluje stosunek wysokości do szerokości symboli DataBar. Proporcja 15 daje stosunkowo krótki, szeroki kod, natomiast 30 sprawia, że jest wyższy. `Save` zapisuje wizualną reprezentację do pliku PNG, spełniając wymóg **zapisać obraz kodu kreskowego**. |
| **4️⃣ Zmień proporcje i zapisz ponownie** | Ponowne użycie tej samej instancji generatora pozwala tworzyć wiele obrazów o różnych cechach wizualnych przy niezmienionych danych. |

---

## Dostosowywanie niestandardowego rozmiaru kodu kreskowego poza wymiarem X

Choć `XDimension.Pixels` ustawia szerokość modułu, możesz także precyzyjnie dopasować ogólne wymiary kodu kreskowego, łącząc dwie właściwości:

1. **`BarHeight`** – explicite wysokość w pikselach.  
2. **`BarWidth`** – explicite szerokość w pikselach (nadpisuje wymiar X).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** Podczas drukowania kodów kreskowych zawsze testuj wygenerowany obraz w ostatecznym rozmiarze druku. Szerokość modułu 2 px sprawdza się na ekranie, ale etykiety drukowane często wymagają co najmniej 4 px, aby pozostały czytelne.

---

## Wybór odpowiedniego formatu obrazu przy zapisywaniu kodu kreskowego

Aspose.BarCode obsługuje PNG, JPEG, BMP, GIF i TIFF. PNG jest bezstratny i zachowuje ostre krawędzie, co czyni go najbezpieczniejszym wyborem dla większości zastosowań. Jeśli potrzebujesz mniejszego pliku do użytku w sieci, JPEG z jakością ustawioną na 90 działa dobrze, ale pamiętaj, że artefakty kompresji mogą wpływać na niezawodność skanowania.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się samodzielna aplikacja konsolowa, którą możesz skopiować, wkleić i uruchomić. Demonstruje **jak wygenerować kod kreskowy**, modyfikować **niestandardowy rozmiar kodu kreskowego** oraz **zapisać obraz kodu kreskowego** w dwóch różnych formatach.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Oczekiwany wynik w konsoli**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Cztery pliki obrazów pojawią się w programie

## Co powinieneś się nauczyć dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generować kod PDF417 przy użyciu Aspose – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generować kod Aztec z niestandardowymi proporcjami przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}