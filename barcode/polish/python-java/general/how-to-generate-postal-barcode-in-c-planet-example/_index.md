---
category: general
date: 2026-10-28
description: Generuj kod kreskowy pocztowy w C# używając formatu Planet. Ten przykład
  kodu kreskowego Planet pokazuje, jak ustawić szerokość kodu kreskowego i zapisać
  zarówno wypełnione, jak i puste paski.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: pl
lastmod: 2026-10-28
og_description: Generuj kod pocztowy w C# z pełnym przykładem kodu kreskowego Planet.
  Naucz się ustawiać szerokość kodu kreskowego, tworzyć wypełnione paski i generować
  obrazy pustych pasków.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Generowanie kodu kreskowego pocztowego w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy pocztowy w C# – przykład planet
url: /pl/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy pocztowy w C# – przykład Planet

Jeśli potrzebujesz wygenerować kod kreskowy pocztowy w C#, ten przewodnik poprowadzi Cię przez pełne rozwiązanie. Zobaczysz praktyczny przykład kodu kreskowego Planet, który koduje ciąg numeryczny, pozwala ustawić szerokość kodu kreskowego i zapisuje zarówno obrazy wypełnionych, jak i pustych pasków.

Tworzenie kodu kreskowego pocztowego nie wymaga skomplikowanego procesu budowania. Po zakończeniu tego samouczka będziesz mógł zintegrować generowanie kodów kreskowych z dowolną aplikacją .NET, dostosować wymiar X i wybrać, czy paski mają być wypełnione, czy puste.

## Wymagania wstępne

* Zainstalowany .NET 6.0 SDK lub nowszy  
* Środowisko programistyczne C# (Visual Studio, VS Code lub Rider)  
* Pakiet NuGet **Aspose.BarCode for .NET** (wersja 23.10 lub nowsza)  

Możesz dodać pakiet za pomocą następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

Poniższe fragmenty kodu zakładają, że dodałeś `using Aspose.BarCode.Generation;` na początku swojego pliku.

## Generowanie kodu kreskowego pocztowego z symboliką Planet

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator`, która używa symboliki Planet. Planet jest formatem kodu kreskowego pocztowego używanym przez kilka krajowych usług pocztowych.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to jest ważne:**  
`EncodeTypes.Planet` informuje bibliotekę, aby użyła standardu kodu kreskowego Planet, który koduje dane numeryczne w serii pasków i przerw. Konstruktor otrzymuje ciąg danych (`"123456"` w tym przypadku), który chcesz zakodować.

Uruchomienie programu generuje dwa pliki PNG w katalogu roboczym wykonywalnego pliku:

* **PostalPlanetFilledBars.png** – paski są renderowane jako solidne czarne prostokąty.  
* **PostalPlanetEmptyBars.png** – paski są renderowane jako białe prostokąty z czarnym obramowaniem, przydatne przy drukowaniu na ciemnym tle.

## Ustaw szerokość kodu kreskowego (wymiar X) w pikselach

Wizualny rozmiar kodu kreskowego jest kontrolowany przez wymiar X, który definiuje szerokość pojedynczego paska. Dostosowanie tej wartości zapewnia prawidłowe skanowanie kodu przy zamierzonej rozdzielczości druku.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Dlaczego warto to ustawić:**  
Większy wymiar X ułatwia skanowanie kodu przy skanerach o niskiej rozdzielczości, podczas gdy mniejsza wartość zmniejsza ogólny rozmiar obrazu przy druku o wysokiej gęstości. Domyślna szerokość to 2 piksele; 4 piksele to powszechny kompromis dla większości drukarek biurkowych.

Możesz eksperymentować z różnymi wartościami:

| Piksele | Typowe zastosowanie |
|--------|---------------------|
| 2      | Etykiety wysokiej gęstości |
| 4      | Standardowe drukowanie biurowe |
| 6‑8    | Oznakowanie dużego formatu |

**Wskazówka:** Zawsze testuj wygenerowany kod kreskowy przy użyciu docelowego skanera po zmianie wymiaru X.

## Przykład kodu kreskowego Planet – wypełnione vs puste paski

Kod kreskowy Planet może być renderowany z solidnymi (wypełnionymi) paskami lub z obrysowanymi (pustymi) paskami. Właściwość `FilledBars` przełącza to zachowanie.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Dlaczego możesz wybrać puste paski:**  
Puste paski poprawiają kontrast na ciemnych opakowaniach, ponieważ biały środek każdego paska wyróżnia się na ciemnym tle. Wypełnione paski są domyślne i dobrze działają na jasnych nośnikach.

**Oczekiwany wynik:**  

*Oba obrazy wyświetlają te same zakodowane dane (`123456`).* Jedyną wizualną różnicą jest styl pasków. Poniżej znajduje się opis tekstowy tego, co zobaczysz:

* **Filled bars image:** Solidne czarne pionowe paski na białym tle.  
* **Empty bars image:** Czarne obramowania tworzące ten sam wzór, z białymi wnętrzami.

Możesz otworzyć pliki PNG w dowolnej przeglądarce obrazów, aby zweryfikować, że wzór odpowiada specyfikacji Planet.

## Dostosowanie dodatkowych właściwości kodu kreskowego (opcjonalnie)

Chociaż powyższe podstawowe kroki obejmują większość scenariuszy, możesz chcieć dopracować inne ustawienia:

| Właściwość | Opis | Typowa wartość |
|------------|------|----------------|
| `Barcode.Color` | Kolor pierwszoplanowy pasków | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Kolor wypełnienia tła | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Tekst czytelny dla człowieka wyświetlany pod kodem kreskowym | Ten sam co zakodowane dane lub własna etykieta |
| `Barcode.ImageFormat` | Format wyjściowy (PNG, JPEG, BMP, itp.) | `BarCodeImageFormat.Png` |

Przykład ustawienia własnego koloru pierwszoplanowego:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Te opcjonalne poprawki pomogą dopasować kod do identyfikacji wizualnej firmy lub spełnić określone wymagania drukowania.

## Częste pułapki i jak ich unikać

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|--------------|
| Barcode is unreadable | X‑dimension too small for the printer’s DPI | Increase `XDimension.Pixels` to 4 or higher |
| Image file is corrupted | Missing write permissions in the target folder | Use an absolute path or ensure the directory exists |
| Wrong symbology used | Passing `EncodeTypes.Code128` instead of `EncodeTypes.Planet` | Verify the `EncodeTypes` argument matches the postal format |

**Porada:** Zawsze generuj testowy kod kreskowy i skanuj go przy użyciu docelowego sprzętu przed wdrożeniem do produkcji.

## Pełny, działający przykład

Poniżej znajduje się samodzielna aplikacja konsolowa, która zawiera wszystkie omówione kroki. Skopiuj kod do nowego projektu konsolowego .NET i uruchom go, aby zobaczyć dwa pliki PNG pojawiające się w folderze wyjściowym.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Kroki weryfikacji:**  

1. Zbuduj projekt (`dotnet build`).  
2. Uruchom plik wykonywalny (`dotnet run`).  
3. Zlokalizuj `PostalPlanetFilledBars.png` i `PostalPlanetEmptyBars.png` w folderze `bin/Debug/net6.0`.  
4. Otwórz każdy obraz; powinieneś zobaczyć serię pionowych pasków reprezentujących ciąg numeryczny


## Co warto nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy Planet z wypełnionymi i pustymi paskami](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Jak ustawić szerokość i wygenerować kod kreskowy Planet w C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Utwórz kod kreskowy pocztowy w C# – pełny przykład generatora](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}