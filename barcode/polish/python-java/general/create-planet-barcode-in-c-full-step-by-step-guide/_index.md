---
category: general
date: 2026-07-18
description: Szybko twórz kod kreskowy Planet w C#. Dowiedz się, jak generować wypełnione
  i puste paski, ustawiać wymiar X oraz zapisywać obrazy PNG – wszystko w jednym samouczku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: pl
lastmod: 2026-07-18
og_description: Twórz kod kreskowy Planet natychmiast. Ten przewodnik pokazuje, jak
  ustawić wymiar X, przełączać się między wypełnionymi a pustymi paskami oraz eksportować
  pliki PNG za pomocą Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Stwórz kod kreskowy planety w C# – Kompletny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Utwórz Planet Barcode w C# – Pełny przewodnik krok po kroku
url: /pl/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy Planet w C# – Pełny przewodnik krok po kroku

Czy kiedykolwiek potrzebowałeś **utworzyć kod kreskowy planet** obrazy, ale nie byłeś pewien, które właściwości dostosować? Nie jesteś sam. Wielu programistów napotyka problem, gdy domyślne wypełnione paski nie spełniają wymagań specyfikacji lub gdy szerokość paska musi odpowiadać DPI drukarki.  

W tym samouczku dowiesz się dokładnie, jak **utworzyć kod kreskowy planet** pliki przy użyciu biblioteki Aspose.BarCode, jak kontrolować **piksele XDimension**, oraz jak przełączać się między **wypełnionymi paskami** a **pustymi paskami** bez przepisywania kodu. Na końcu będziesz mieć dwa pliki PNG — jeden z pełnymi paskami, a drugi z pustymi paskami — gotowe dla każdego systemu pocztowego oczekującego symbologii Planet.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa także na .NET Framework 4.7 +)  
- Pakiet NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)  
- Podstawowa znajomość C# (zobaczysz później, dlaczego używamy instrukcji `using`)  
- Zapisywalny folder na dysku, w którym zostaną zapisane pliki PNG  

Jeśli masz to wszystko, możemy od razu przejść do implementacji.

## Krok 1 – Skonfiguruj projekt i dodaj bibliotekę

Najpierw utwórz nową aplikację konsolową (lub dowolny projekt C#) i odwołaj się do biblioteki **Planet barcode generator**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Pro tip:** W Visual Studio kliknij prawym przyciskiem myszy projekt → *Manage NuGet Packages* → wyszukaj **Aspose.BarCode** i kliknij *Install*. Dzięki temu uzyskasz dostęp do `BarcodeGenerator` oraz wszystkich **parametrów BarcodeGenerator**, których będziesz potrzebował.

## Krok 2 – Zainicjuj generator kodu kreskowego Planet

Teraz faktycznie **tworzymy generator kodu kreskowego planet** i podajemy mu dane, które chcemy zakodować (`"123456"` w tym przykładzie). Enum `EncodeTypes.Planet` informuje bibliotekę, której symbologii użyć.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Dlaczego to ważne:** Flaga `EncodeTypes.Planet` automatycznie stosuje prawidłową sumę kontrolną i zasady układu dla pocztowego kodu kreskowego Planet, więc nie musisz ich obliczać ręcznie.

## Krok 3 – Skonfiguruj X‑Dimension (szerokość paska)

Większość drukarek oczekuje, że każdy pasek będzie miał określoną liczbę pikseli. Tutaj ustawiamy **piksele XDimension** na `4`, co jest typową wartością dla termicznych drukarek 203 dpi.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Edge case:** Jeśli celujesz w drukarkę 300 dpi, możesz potrzebować `3` lub `5` pikseli. Dostosuj tę wartość zgodnie z dokumentacją swojego urządzenia.

## Krok 4 – Zapisz wersję z wypełnionymi paskami

Domyślnie generator tworzy **wypełnione paski** (solidne czarne prostokąty). Zapiszmy je na dysku:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Zastąp `YOUR_DIRECTORY` ścieżką absolutną lub względną, do której aplikacja ma prawo zapisu. Po wykonaniu tej linii znajdziesz plik PNG wyglądający jak klasyczny kod kreskowy Planet — idealny do testów z czytnikiem pocztowym.

## Krok 5 – Przełącz na puste paski

Czasami usługi pocztowe wymagają stylu „pustych pasków”, gdzie paski są wycięte z białego tła zamiast pomalowane na czarno. Biblioteka udostępnia prosty przełącznik:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Ustawienie `FilledBars` na `false` mówi rendererowi, aby odwrócił logikę wypełniania pasków. Nie ma potrzeby tworzenia nowej instancji `BarcodeGenerator`; wystarczy zmodyfikować istniejące **parametry BarcodeGenerator**.

## Krok 6 – Zapisz wersję z pustymi paskami

Na koniec wyeksportuj drugi obraz:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Teraz masz dwa odrębne pliki PNG, każdy spełniający inny wymóg wizualny.

## Pełny działający przykład

Składając wszystkie elementy razem, oto kompletny, gotowy do skopiowania program:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Oczekiwany wynik** (w konsoli):

```
Both Planet barcode images have been generated successfully.
```

A w `C:\Barcodes\` zobaczysz:

- `PostalPlanetFilledBars.png` – solidne czarne paski  
- `PostalPlanetEmptyBars.png` – białe paski z czarnymi konturami  

Otwórz je w dowolnym przeglądarce obrazów; oba powinny spełniać specyfikację Planet.

## Często zadawane pytania i wskazówki

### „Czy mogę zmienić format obrazu?”

Oczywiście. Metoda `Save` akceptuje `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` itd. Wystarczy zamienić `BarCodeImageFormat.Png` na żądany format.

### „Co zrobić, jeśli potrzebuję innej wysokości kodu kreskowego?”

Użyj `planetBarcode.Parameters.Barcode.BarHeight` (w punktach), aby zwiększyć lub zmniejszyć rozmiar pionowy. Na przykład:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### „Czy da się dodać czytelny dla człowieka podpis?”

Tak. Ustaw właściwość `CodeText` w `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### „Czy muszę zwolnić generator?”

`BarcodeGenerator` implementuje `IDisposable`. Owiń go w blok `using`, jeśli tworzysz wiele kodów kreskowych w pętli:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### „A co z obsługą błędów?”

Umieść wywołania `Save` w bloku `try…catch`, aby przechwycić `IOException` (problemy z dyskiem) lub `ArgumentException` (nieprawidłowe parametry). Przykład:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Podsumowanie

Omówiliśmy wszystko, co potrzebne, aby **utworzyć kod kreskowy planet** obrazy w C#:

1. Zainicjuj **generator kodu kreskowego Planet** z własnymi danymi.  
2. Dostosuj **piksele XDimension**, aby pasowały do specyfikacji drukarki.  
3. Zapisz PNG z **wypełnionymi paskami**.  
4. Przełącz `FilledBars`, aby uzyskać **puste paski**.  
5. Zapisz drugi PNG.  

Od tego momentu możesz eksplorować więcej **parametrów BarcodeGenerator**, eksperymentować z innymi symbologiami (`EncodeTypes.Postnet`, `EncodeTypes.Code128` itp.) lub integrować obrazy w przepływie pracy pocztowej.

---

**Gotowy na kolejny krok?** Spróbuj dodać kod QR do tego samego dokumentu lub wygenerować batch kodów Planet z listy CSV przy użyciu pętli `foreach`. API Aspose.BarCode jest na tyle elastyczne, że obsłuży operacje masowe, niestandardowe kolory, a nawet wektorowy format SVG.

Jeśli napotkasz problemy, zostaw komentarz poniżej lub sprawdź oficjalną dokumentację Aspose.BarCode, aby zgłębić zaawansowane funkcje. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}