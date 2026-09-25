---
category: general
date: 2026-08-22
description: Jak szybko generować kod kreskowy i dowiedzieć się, jak zmienić rozmiar
  kodu kreskowego podczas eksportowania obrazu kodu kreskowego jako PNG przy użyciu
  Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: pl
lastmod: 2026-08-22
og_description: Jak generować kod kreskowy w C# i łatwo zmienić rozmiar kodu kreskowego
  przed eksportem obrazu kodu kreskowego jako PNG. Postępuj zgodnie z tym kompletnym
  przewodnikiem.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Jak generować obrazy kodów kreskowych o niestandardowym rozmiarze w C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak generować obrazy kodów kreskowych o niestandardowym rozmiarze w C#
url: /pl/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować obrazy kodów kreskowych o niestandardowym rozmiarze w C#

Jeśli potrzebujesz **how to generate barcode** do automatyzacji pocztowej, śledzenia zapasów lub biletów na wydarzenia, ten przewodnik pokazuje kompletną, gotową do uruchomienia rozwiązanie w C#. Dowiesz się także, jak **how to change barcode size** oraz **export barcode image** w formacie PNG bez opuszczania IDE.

Użyjemy biblioteki Aspose.BarCode, ponieważ obsługuje symbologię OneCode, pozwala kontrolować wymiary piksel po pikselu i obsługuje eksport obrazu jednym wywołaniem metody. Po zakończeniu samouczka będziesz mieć cztery pliki PNG — każdy przedstawiający kod kreskowy OneCode z inną liczbą cyfr.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+)
- Visual Studio 2022 (lub dowolny edytor C#, którego preferujesz)
- Odwołanie NuGet do **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Podstawowa znajomość składni C#

> **Pro tip:** Jeśli testujesz bibliotekę, Aspose oferuje darmowy 30‑dniowy trial, który zawiera wszystkie funkcje kodów kreskowych.

## Krok 1: Utwórz minimalny projekt konsolowy

Utwórz nową aplikację konsolową i dodaj pakiet Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Wygenerowany plik `Program.cs` będzie zawierał pełną logikę generowania kodów kreskowych.

## Krok 2: How to generate barcode – utwórz metodę wielokrotnego użytku

Poniżej znajduje się samodzielna metoda, która przyjmuje ciąg danych, żądaną nazwę pliku oraz opcjonalne parametry rozmiaru. Metoda ta demonstruje podstawowy wzorzec **how to generate barcode**.

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
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Dlaczego ta metoda jest ważna

- **Encapsulation:** Wszystkie ustawienia związane z rozmiarem znajdują się w jednym miejscu, co ułatwia wywoływanie metody z różnymi wymiarami.
- **Reusability:** Możesz ponownie używać tej samej metody dla dowolnej długości ciągu OneCode, co jest istotne, ponieważ OneCode akceptuje tylko 20‑31 cyfr.
- **Clarity:** Komentarze oznaczone emoji prowadzą czytelników przez trzy logiczne fazy — inicjalizację, zmianę rozmiaru i eksport.

## Krok 3: Zmiana rozmiaru kodu kreskowego dla różnych wymagań

Czasami skaner oczekuje wyższego kodu kreskowego, lub układ wydruku wymaga węższego modułu. Właściwość `XDimension.Pixels` kontroluje szerokość pojedynczego modułu kodu kreskowego, natomiast `BarHeight.Pixels` ustawia całkowitą wysokość.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Kluczowe punkty przy zmianie rozmiaru:**

- **Minimum X‑dimension:** Technicznie dopuszczalny jest 1 piksel, ale większość skanerów wymaga co najmniej 2 pikseli do niezawodnego odczytu.
- **Maximum height:** Nie ma sztywnego limitu, ale bardzo wysokie kody kreskowe mogą przekraczać obszar drukowalny na standardowych etykietach.
- **Aspect ratio:** Utrzymuj zrównoważony stosunek wysokości do szerokości modułu (≈12‑15 × szerokość modułu), aby uniknąć zniekształceń.

## Krok 4: Eksport obrazu kodu kreskowego w innych formatach (opcjonalnie)

Metoda `Save` akceptuje kilka wartości `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Jeśli potrzebujesz bezstratnego formatu wektorowego, możesz zamiast tego wyeksportować do `Svg`.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Eksportowanie jako PNG jest najczęstszym wyborem, ponieważ zachowuje ostre krawędzie i jest szeroko wspierane przez przeglądarki internetowe oraz procesy drukowania.

## Oczekiwany wynik

Uruchomienie programu tworzy cztery pliki PNG w folderze projektu:

- `PostalOneCodeBarcode20Digits.png` – kod OneCode o 20 cyfrach
- `PostalOneCodeBarcode25Digits.png` – kod OneCode o 25 cyfrach
- `PostalOneCodeBarcode29Digits.png` – kod OneCode o 29 cyfrach
- `PostalOneCodeBarcode31Digits.png` – kod OneCode o 31 cyfrach

Każdy obraz będzie wyglądał podobnie do poniższego zastępczego (rzeczywista grafika zależy od podanych danych liczbowych).

![Przykład generowania kodu kreskowego](https://example.com/placeholder.png "Przykład generowania kodu kreskowego")

*Tekst alternatywny obrazu zawiera główne słowo kluczowe dla dostępności i SEO.*

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|--------|
| **Co jeśli ciąg danych jest krótszy niż 20 cyfr?** | OneCode wymaga minimum 20 cyfr. Dodaj wiodące zera do ciągu lub użyj innej symbologii (np. Code128). |
| **Czy mogę generować kody kreskowe w środowisku wielowątkowym?** | Tak. `BarcodeGenerator` nie jest bezpieczny wątkowo, więc należy utworzyć osobny generator dla każdego wątku. |
| **Jak ustawić kolor tła?** | Użyj `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` przed wywołaniem `Save`. |
| **Czy istnieje sposób, aby osadzić obraz bezpośrednio w stronie HTML?** | Zapisz obraz do `MemoryStream`, przekonwertuj na Base64 i osadź przy pomocy `<img src="data:image/png;base64,..." />`. |

## Zakończenie

Teraz wiesz, jak **how to generate barcode** obrazy w C# przy użyciu Aspose.BarCode, jak **change barcode size** poprzez dostosowanie X‑dimension i wysokości pasków oraz jak **export barcode image** pliki w formacie PNG (lub innych). Wielokrotnego użytku metoda `GenerateOneCode` pozwala stworzyć dowolny kod OneCode od 20 do 31 cyfr jedną linią kodu.

Od tego momentu możesz:

- Eksperymentować z innymi symbologiami (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Zintegrować generator z API webowym, które zwraca obrazy kodów kreskowych na żądanie.
- Połączyć wyjście PNG z biblioteką PDF, aby osadzać kody kreskowe na etykietach wysyłkowych.

Miłego kodowania i zachęcam do dzielenia się własnymi wariacjami w komentarzach!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generować i dostosowywać wysokość kodu kreskowego One-Dimensional Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}