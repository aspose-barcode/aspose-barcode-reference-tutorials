---
category: general
date: 2026-07-18
description: Dowiedz się, jak generować obrazy kodów kreskowych za pomocą generatora
  kodów kreskowych .NET i łatwo zmieniać wysokość kodu kreskowego dla symboli GS1‑Databar
  Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: pl
lastmod: 2026-07-18
og_description: Generator kodów kreskowych .net pozwala szybko tworzyć obrazy kodów
  kreskowych. Ten przewodnik pokazuje, jak generować kody kreskowe, dostosować wysokość
  pasków i zapisywać pliki PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Zmień wysokość kodu kreskowego przy użyciu generatora kodów kreskowych .NET
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET generator kodów kreskowych – zmień wysokość kodu kreskowego
url: /pl/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – zmiana wysokości kodu kreskowego

Zastanawiałeś się kiedyś **jak generować obrazy kodów kreskowych** bez używania dziesiątek narzędzi firm trzecich? W świecie .NET istnieje zaskakująco prosty sposób, a kluczowym elementem jest **.net barcode generator**. Dzięki kilku liniom C# możesz stworzyć symbol GS1‑Databar Omni‑Directional, dostosować wysokość pasków i zapisać wynik jako plik PNG.

Jeśli tworzysz system inwentaryzacji, drukarkę etykiet wysyłkowych lub dowolną aplikację potrzebującą kodu do zeskanowania, ten samouczek przeprowadzi Cię od zera do działającego kodu kreskowego w kilka minut. Przejdziemy przez kompletny kod, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i pokażemy, jak **zmienić wysokość kodu kreskowego** nie łamiąc specyfikacji.

## Czego będziesz potrzebować

- .NET 6.0 lub nowszy (API działa tak samo na .NET Framework 4.7+)
- Odwołanie do biblioteki kodów kreskowych (np. Aspose.BarCode for .NET – te same klasy są używane w wielu komercyjnych zestawach)
- Środowisko programistyczne (Visual Studio, Rider lub VS Code z rozszerzeniem C#)
- Folder, w którym masz uprawnienia do zapisu – samouczek zapisze tam pliki PNG

To wszystko. Nie potrzebujesz dodatkowych pakietów NuGet poza samą biblioteką kodów kreskowych.

## Używanie .net barcode generator do zmiany wysokości kodu kreskowego

Poniżej znajduje się **kompletny, działający program konsolowy**. Wklej go do nowego projektu C#, dostosuj folder wyjściowy i naciśnij F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

| Linia | Powód |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Tworzy **.net barcode generator** z wybraną symbologią i danymi. Enum `EncodeTypes.DatabarOmniDirectional` informuje bibliotekę, aby użyła formatu GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimension określa szerokość najcieńszego paska. Ustawienie na *2 piksele* zapewnia wyraźny obraz na większości monitorów przy jednoczesnym utrzymaniu małego rozmiaru pliku. |
| `BarHeight.Pixels = 30;` | To krok **zmiany wysokości kodu kreskowego**, który określa, jak wysokie będą poszczególne paski. Wysokość 30 pikseli to dobre domyślne ustawienie dla małych etykiet. |
| `generator.Save(...);` | Zapisuje kod kreskowy do pliku PNG. PNG jest bezstratny, co oznacza, że skanery widzą dokładny wygenerowany wzór. |
| `BarHeight.Pixels = 60;` | Tutaj ponownie **zmieniamy wysokość kodu kreskowego** – tym razem na 60 pikseli. Biblioteka automatycznie renderuje symbol z nowym wymiarem przy drugim wywołaniu `Save`. |
| `Console.WriteLine(...);` | Daje szybki komunikat zwrotny, że proces zakończył się bez wyjątków. |

> **Porada:** Jeśli potrzebujesz wyjścia o wyższej rozdzielczości do druku, zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Tiff` i zwiększ właściwość `Resolution` (np. `generator.Parameters.ImageResolution = 300;`). Wysokość pasków nadal będzie zachowana, tylko zostanie wyrenderowana przy wyższej DPI.

## Jak generować obrazy kodów kreskowych z różnymi ustawieniami

Powyższy fragment obejmuje podstawy, ale w rzeczywistych scenariuszach często potrzebne są dodatkowe modyfikacje:

### Dostosowanie X‑dimension dla większych wydruków
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Zwiększenie X‑dimension powoduje, że cały kod kreskowy staje się większy, nie zmieniając zakodowanych danych. Jest to przydatne przy drukowaniu na dużych etykietach.

### Zmiana formatu wyjściowego
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG skaluje się nieskończenie, co jest idealne dla skanerów internetowych, które potrzebują wyraźnych wektorów.

### Dodawanie tekstu czytelnego dla człowieka
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Włączenie `CodeTextVisible` dodaje surowe dane pod kodem kreskowym, co jest przydatne do weryfikacji podczas testów.

## Typowe pułapki przy **zmianie wysokości kodu kreskowego**

1. **Zbyt mała wysokość** – Niektóre skanery wymagają minimalnej wysokości paska (często 10 mm w jednostkach fizycznych). Jeśli ustawisz `BarHeight.Pixels` zbyt nisko, wygenerowany obraz może być nieczytelny dla rzeczywistego skanera. Zawsze testuj na docelowym sprzęcie.
2. **Niezgodność X‑dimension i wysokości** – Duża wysokość paska połączona z małą X‑dimension może wyglądać na rozciągniętą i powodować błędy dekodowania. Dąż do zrównoważonego stosunku (około 3:1 do 5:1), chyba że specyfikacja wymaga inaczej.
3. **Zapomnienie o zresetowaniu parametrów** – Generator zachowuje stan między zapisami. Jeśli zmienisz `BarHeight` dla jednego obrazu i ponownie użyjesz tej samej instancji dla innego kodu kreskowego, poprzednia wysokość pozostanie. Zresetuj właściwość lub utwórz nowy `BarcodeGenerator` dla każdego odrębnego kodu.

## Pełny przykład od początku do końca (włącznie z instalacją NuGet)

Jeśli zaczynasz od zera, wykonaj następujące kroki, aby uruchomić projekt:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Zastąp automatycznie wygenerowany `Program.cs` kodem z poprzedniego bloku, **pamiętaj, aby zamienić `YOUR_DIRECTORY`** na coś w rodzaju `Path.Combine(Environment.CurrentDirectory, "output")`. Następnie:

```bash
dotnet run
```

Powinieneś zobaczyć dwa pliki PNG w folderze `output`:

- `DatabarBarHeight30Pixels.png` – kompaktowy kod kreskowy o wysokości 30 pikseli.
- `DatabarBarHeight60Pixels.png` – wyższa wersja o wysokości 60 pikseli.

Oba obrazy będą wyglądały podobnie, ale drugi będzie miał wyraźnie dłuższe paski, co ułatwi odczyt skanerom o niskiej rozdzielczości.

![Barcode height example](/images/barcode-height.png){alt="Wynik .net barcode generator pokazujący różne wysokości pasków"}

## Podsumowanie i kolejne kroki

Omówiliśmy, jak **generować obrazy kodów kreskowych** przy użyciu **.net barcode generator**, precyzyjnie dostosowaliśmy właściwość **change barcode height** i zapisaliśmy wyniki w formacie PNG. Najważniejsze wnioski to:

- Utwórz generator z odpowiednim `EncodeTypes`.
- Kontroluj rozmiar wizualny za pomocą `XDimension` i `BarHeight`.
- Wywołuj `Save` po każdej zmianie, aby zapisać nowy obraz.
- Dostosuj rozdzielczość, format,

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak utworzyć rozszerzony kod tekstowy dotcode przy użyciu Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}