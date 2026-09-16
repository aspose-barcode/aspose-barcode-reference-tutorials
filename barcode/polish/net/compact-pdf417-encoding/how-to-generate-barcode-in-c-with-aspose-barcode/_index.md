---
category: general
date: 2026-09-16
description: Dowiedz się, jak generować kod kreskowy i ustawiać jego rozmiar w C#.
  Przewodnik krok po kroku z użyciem Aspose.BarCode do tworzenia obrazu Micro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: pl
lastmod: 2026-09-16
og_description: Jak wygenerować kod kreskowy w C# i ustawić jego rozmiar przy użyciu
  Aspose.BarCode. Przejdź przez ten zwięzły samouczek, aby stworzyć plik PNG z kodem
  Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Jak generować kod kreskowy w C# – kompletny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz wiedzieć **jak wygenerować kod kreskowy** w projekcie .NET, ten samouczek przeprowadzi Cię przez cały proces przy użyciu biblioteki Aspose.BarCode. Dowiesz się także, jak **ustawić rozmiar kodu kreskowego**, aby obraz pasował do Twojego interfejsu użytkownika lub wymagań drukowania.

Poradnik obejmuje wszystko, od instalacji pakietu NuGet po skonfigurowanie symbolu Micro PDF417 i zapisanie go jako plik PNG. Po zakończeniu będziesz mieć działający przykład kodu, który możesz wkleić do dowolnej aplikacji konsolowej lub webowej w C#.

## Czego będziesz potrzebować

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+)
- Visual Studio 2022 lub dowolne IDE obsługujące C#
- Dostęp do Internetu w celu pobrania pakietu NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Podstawowa znajomość składni C#

## Jak wygenerować kod kreskowy przy użyciu Aspose.BarCode

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator`, która wie, jaką symbologię użyć i jakie dane zakodować.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Dlaczego to ważne:** `EncodeTypes.MicroPdf417` informuje bibliotekę, aby wyprodukowała kompaktową odmianę PDF417, idealną dla małych etykiet lub odcisków podobnych do kodu QR. Ciąg znaków `"Micro data"` staje się czytelną dla człowieka treścią osadzoną w kodzie kreskowym.

## Ustaw rozmiar i wymiary kodu kreskowego

Czytelny kod kreskowy musi mieć odpowiedni wymiar modułu (X) oraz wystarczającą liczbę kolumn, aby pomieścić dane. To tutaj **ustawiasz rozmiar kodu kreskowego**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** kontroluje szerokość najmniejszego paska („modułu”). Wartość `2` piksele dobrze sprawdza się przy wyświetlaniu na ekranie; zwiększ ją przy drukowaniu w wysokiej rozdzielczości.
- **Pdf417.Columns** ogranicza liczbę pionowych kolumn. Format Micro PDF417 obsługuje maksymalnie 7 kolumn; `4` zapewnia zrównoważony rozmiar bez utraty pojemności danych.

> **Pro tip:** Jeśli wygenerowany obraz wygląda na zbyt mały, podnieś `XDimension.Pixels` do `3` lub `4`. Odwrotnie, w przypadku ograniczonej przestrzeni UI, możesz obniżyć go do `1`, ale upewnij się, że skaner, którego zamierzasz używać, nadal będzie w stanie odczytać symbol.

## Zapisz obraz kodu kreskowego

Po skonfigurowaniu rozmiaru po prostu instruujesz generator, aby zapisał obraz na dysku.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Metoda `Save` akceptuje dowolny format obsługiwany przez Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG jest bezstratny, zachowując ostre krawędzie potrzebne do niezawodnego skanowania.

**Oczekiwany wynik:** Plik o nazwie `micro.png` pojawi się w katalogu roboczym projektu. Po otwarciu zobaczysz mały, wysokokontrastowy kod Micro PDF417 gotowy do testowania dowolnym standardowym skanerem.

## Pełny przykład

Połączenie wszystkich elementów daje Ci samodzielny program, który możesz uruchomić od razu.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Uruchom program (`dotnet run` z konsoli) i zobaczysz komunikat potwierdzający. Wygenerowany PNG może być osadzony w raportach, wydrukowany na etykietach produktów lub wyświetlony na stronie internetowej.

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|---|---|
| **Czy mogę generować inne typy kodów kreskowych?** | Tak. Zastąp `EncodeTypes.MicroPdf417` dowolną wartością z wyliczenia `EncodeTypes` (np. `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Co zrobić, jeśli potrzebuję większego obrazu?** | Zwiększ `XDimension.Pixels` lub użyj `generator.Parameters.Image.Width/Height`, aby wymusić konkretny rozmiar w pikselach. |
| **Czy biblioteka obsługuje przezroczyste tła?** | Ustaw `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` przed wywołaniem `Save`. |
| **Jak odczytać kod kreskowy?** | Użyj `Aspose.BarCode.BarCodeReader` na zapisanym obrazie; automatycznie wykrywa symbologię. |
| **Czy PNG jest bezpieczny do druku?** | PNG jest bezstratny, ale przy drukowaniu w CMYK rozważ zapis jako TIFF (`BarCodeImageFormat.Tiff`). |

## Zakończenie

Teraz wiesz **jak generować kod kreskowy** w C# oraz jak **ustawić rozmiar kodu kreskowego** przy użyciu Aspose.BarCode. Pełny przykład demonstruje tworzenie symbolu Micro PDF417, dostosowywanie jego wymiarów i eksportowanie pliku PNG. Dzięki tej podstawie możesz eksplorować inne symbologie, dostosowywać kolory lub integrować generowanie kodów kreskowych w usługach ASP.NET Core.

### Kolejne kroki

- Spróbuj wygenerować kod QR (`EncodeTypes.QR`) i porównać rozmiary modułów.  
- Eksperymentuj z `generator.Parameters.Image`, aby dodać marginesy lub zmienić DPI dla gotowego do druku wyjścia.  
- Połącz generowanie kodów kreskowych z **Aspose.PDF**, aby osadzić obraz bezpośrednio w raporcie PDF.

Miłego kodowania i ciesz się elastycznością, jaką Aspose.BarCode wnosi do Twoich projektów .NET związanych z kodami kreskowymi!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletny działający kod z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować obraz kodu PDF417 w C# przy użyciu Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak wygenerować kod PDF417 przy użyciu Aspose – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak wygenerować kod kreskowy w C# – Kompletny przewodnik Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}