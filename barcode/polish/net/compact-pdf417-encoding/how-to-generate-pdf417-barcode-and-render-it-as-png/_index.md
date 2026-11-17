---
category: general
date: 2026-11-17
description: Dowiedz się, jak wygenerować kod kreskowy PDF417, ustawić jego rozmiar
  i wyrenderować go jako obraz przy użyciu C#. Kompletny przewodnik krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: pl
lastmod: 2026-11-17
og_description: Wygeneruj kod kreskowy PDF417 w C# i renderuj go jako obraz. Postępuj
  zgodnie z tym przewodnikiem, aby ustawić rozmiar kodu kreskowego i zapisać plik
  PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Generowanie kodu kreskowego PDF417 i renderowanie jako PNG – przewodnik
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Jak wygenerować kod kreskowy PDF417 i wyrenderować go jako PNG
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 i wyświetlić go jako PNG

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten tutorial pokaże Ci dokładnie, jak to zrobić. Zobaczysz, jak ustawić rozmiar kodu kreskowego, skonfigurować układ oraz **wyświetlić kod kreskowy jako obraz** przy użyciu kilku linijek kodu C#.

Generowanie kodu kreskowego PDF417 jest powszechne, gdy chcesz zakodować dużą ilość danych do skanowania na urządzeniach mobilnych lub drukarkach. Po zakończeniu tego przewodnika będziesz mieć gotowy plik PNG, który możesz osadzić w raportach, e‑mailach lub stronach internetowych.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy zainstalowany  
- IDE C# takie jak Visual Studio 2022 (dowolny edytor działa)  
- Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolna kompatybilna biblioteka dostarczająca `BarcodeGenerator`)  

Możesz dodać pakiet za pomocą:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz projekt konsolowy C#

Najpierw skonfiguruj minimalną aplikację konsolową, która będzie zawierać kod generujący kod kreskowy.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Wskazówka:** Trzymaj metodę `Main` krótką i deleguj ciężkie operacje do metod pomocniczych. To poprawia czytelność i ułatwia testowanie jednostkowe.

## Krok 2: Wygeneruj kod kreskowy PDF417 o niestandardowym rozmiarze

Teraz **wygenerujemy kod kreskowy PDF417** i określimy rozmiar modułu (wymiar X). Wymiar X kontroluje szerokość każdego małego kwadratu kodu kreskowego, skutecznie ustalając ogólny rozmiar kodu.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Dlaczego ustawiać wymiar X?

Krok **jak ustawić rozmiar kodu kreskowego** jest ważny, ponieważ zbyt mały wymiar X może sprawić, że kod będzie nieczytelny dla skanerów o niskiej rozdzielczości, a zbyt duży marnuje miejsce. Wartość `2` piksele dobrze sprawdza się w większości wyświetlaczy i scenariuszy drukowania.

## Krok 3: Wywołaj metodę generującą z `Main`

Połącz wszystko, wywołując `GeneratePdf417` z żądanym tekstem i lokalizacją wyjściową.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Uruchomienie programu tworzy plik `LayoutPdf417.png` zawierający kod kreskowy:

![Wygenerowany kod kreskowy PDF417](/images/layout-pdf417.png "Kod kreskowy PDF417 wygenerowany przez kod tutoriala"){: .align-center alt="Wygenerowany kod kreskowy PDF417 zapisany jako PNG"}

> **Oczekiwany wynik:** Plik PNG o rozmiarze około 200 × 100 px (w zależności od ustawień kolumn/wierszy), który wyświetla wyraźny wzór PDF417 gotowy do skanowania.

## Krok 4: Zweryfikuj działanie kodu kreskowego

Aby upewnić się, że kod kreskowy jest prawidłowy:

1. Otwórz plik PNG w dowolnej przeglądarce obrazów.  
2. Użyj aplikacji na smartfonie do skanowania kodów kreskowych, która obsługuje PDF417 (np. Google Lens, QR & Barcode Scanner).  
3. Zeskanuj obraz; aplikacja powinna zwrócić tekst *Layout demo*.

Jeśli skanowanie się nie powiedzie, sprawdź ponownie wymiar X oraz wartości kolumn/wierszy — większe moduły poprawiają czytelność na kamerach o niskiej rozdzielczości.

## Typowe warianty i przypadki brzegowe

| Scenariusz | Dostosowanie |
|------------|--------------|
| **Więcej danych** (np. URL) | Zwiększ `Columns` lub `Rows`, aby pomieścić dodatkowe codewords. |
| **Wysokiej rozdzielczości druk** | Podnieś `XDimension.Pixels` do 3‑4 px, aby uzyskać ostrzejsze paski. |
| **Przezroczyste tło** | Użyj `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Inny format obrazu** | Zastąp `BarCodeImageFormat.Png` przez `Jpeg` lub `Bmp` w razie potrzeby. |

Te warianty odpowiadają na pytanie **jak wygenerować PDF417** dla różnych wymagań, zachowując jednocześnie identyczną logikę podstawową.

## Podsumowanie

Teraz wiesz, jak **wygenerować kod kreskowy PDF417**, **ustawić rozmiar kodu kreskowego** i **wyświetlić kod kreskowy jako obraz** przy użyciu C#. Pełny, działający przykład tworzy plik PNG, który można osadzić w dowolnym miejscu, gdzie potrzebny jest kod kreskowy odczytywany maszynowo.

Następnie, zapoznaj się z powiązanymi tematami, takimi jak **osadzanie PNG w PDF** (sprawdź *render barcode to PDF*), lub **generowanie innych kodów 2‑D** jak kody QR. Dostosuj parametry układu do projektu UI i eksperymentuj z opcjami kolorów w celu budowania marki.

Miłego kodowania i niech Twoje kody kreskowe wykonują ciężką pracę!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 w C# – kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Jak wygenerować mikro PDF417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak ustawić poziom błędu w kodzie PDF417 – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}