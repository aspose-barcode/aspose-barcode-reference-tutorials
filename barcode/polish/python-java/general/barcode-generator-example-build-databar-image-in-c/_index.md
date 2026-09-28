---
category: general
date: 2026-07-18
description: Przykład generatora kodów kreskowych pokazujący, jak ustawić wymiary
  i wygenerować obraz kodu DataBar Stacked Omni‑Directional w C#. Szybko poznaj typy
  kodowania kodów kreskowych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: pl
lastmod: 2026-07-18
og_description: Przykład generatora kodów kreskowych prowadzi Cię krok po kroku, jak
  ustawić wymiary, wybrać typy kodowania i tworzyć obrazy kodów kreskowych w projektach
  C# przy minimalnym kodzie.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Przykład generatora kodów kreskowych – szybkie tworzenie obrazu DataBar
  w C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Przykład generatora kodów kreskowych – Tworzenie obrazu DataBar w C#
url: /pl/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych – Tworzenie obrazu DataBar w C#

Czy kiedykolwiek potrzebowałeś **przykładu generatora kodów kreskowych**, który naprawdę generuje rzeczywisty kod kreskowy, nie wyrywając sobie włosów? Nie jesteś sam. Większość programistów napotyka problem, gdy próbuje ustalić **jak ustawić wymiary** dla kodu DataBar Stacked Omni‑Directional, zwłaszcza gdy dokumentacja jest ukryta pod warstwą żargonu.

W tym samouczku przejdziemy krok po kroku przez kompletny, gotowy do uruchomienia program w C#, który pokazuje **jak generować obrazy databar**, wybiera odpowiednie **barcode encode types**, i w końcu **create barcode image c#** pliki, które możesz wkleić do dowolnego projektu. Bez zbędnego balastu — tylko kod, który możesz skopiować‑wkleić, oraz uzasadnienie każdej linii.

## Czego będziesz potrzebować

- **.NET 6** (lub dowolna nowsza wersja .NET) – API, którego używamy, celuje w .NET Standard, więc działa także na .NET Framework.  
- **Aspose.BarCode for .NET** – biblioteka udostępniająca `BarcodeGenerator`. Możesz ją pobrać z NuGet za pomocą `Install-Package Aspose.BarCode`.  
- **IDE C#** – Visual Studio, Rider lub VS Code będą odpowiednie.  
- Folder na dysku, w którym zostaną zapisane pliki PNG (kod tworzy `DatabarAspectRatio15.png` i `DatabarAspectRatio30.png`).

Masz wszystko? Świetnie—zanurzmy się.

## Przykład generatora kodów kreskowych – Inicjalizacja generatora

Najpierw potrzebujemy instancji `BarcodeGenerator` skonfigurowanej dla symbologii **DataBar Stacked Omni‑Directional**. To jest **barcode encode type**, z którym będziemy pracować.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Dlaczego to ma znaczenie:** `EncodeTypes.DatabarStackedOmniDirectional` mówi Aspose dokładnie, którą symbologię ma renderować. Jeśli wybierzesz niewłaściwy typ, skaner nie rozpozna kodu kreskowego, bez względu na to, jak ładny będzie obraz.

## Jak ustawić wymiary dla kodu kreskowego

Czytelność kodu kreskowego zależy od jego **X‑dimension** (szerokość najcieńszego paska). W większości przypadków wartość 2 piksele działa dobrze, ale możesz ją dostosować do swojego drukarki lub ekranu.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Wskazówka:** Jeśli kiedykolwiek zastanawiasz się **jak ustawić wymiary** dla innej rodziny kodów, ta sama łańcuchowa właściwość (`Parameters.Barcode.XDimension`) ma zastosowanie — po prostu zmień wartość `Pixels`.

## Jak wygenerować DataBar Stacked Omni‑Directional

Teraz, gdy generator jest gotowy, pobawimy się właściwością **aspect ratio**. Kontroluje ona stosunek wysokości do szerokości DataBar, pozwalając uzyskać krótki, kwadratowy symbol lub wysoki, wąski.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Co się dzieje?** `AspectRatio = 15` mówi silnikowi, aby słupki były 15‑krotnie wyższe niż szerokie. Powstały plik PNG zostaje zapisany tuż obok twojego pliku wykonywalnego.

## Create Barcode Image C# – Zmiana współczynnika proporcji

Pokażmy elastyczność, zmieniając współczynnik na 30 i zapisując drugi plik.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

Po uruchomieniu programu otrzymasz dwa pliki PNG:

| Plik | Współczynnik proporcji | Przybliżony rozmiar |
|------|------------------------|---------------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Otwórz je w dowolnym przeglądarce obrazów — powinieneś zobaczyć czyste, skanowalne symbole DataBar.

## Przegląd typów kodów kreskowych (Opcjonalnie, ale przydatny)

Jeśli jesteś ciekawy innych **barcode encode types** obsługiwanych przez Aspose, oto szybka ściągawka:

| Enum EncodeTypes | Opis |
|------------------|------|
| `EncodeTypes.Code128` | Wysokiej gęstości alfanumeryczny |
| `EncodeTypes.QR` | Kod macierzowy 2‑D |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar dla handlu detalicznego |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Nasze skupienie** – kompaktowy, omnidirectional |

Znajomość właściwego enumu oszczędza wiele prób i błędów przy przełączaniu projektów.

## Częste pułapki i jak ich unikać

- **Brak pakietu NuGet** – Kod nie skompiluje się bez `Aspose.BarCode`. Najpierw uruchom `dotnet add package Aspose.BarCode`.  
- **Nieprawidłowa ścieżka pliku** – Jeśli używasz ścieżki bezwzględnej, sprawdź podwójne ukośniki (`\\`) w Windows. Ścieżki względne (tak jak pokazano) są bardziej przenośne.  
- **Zbyt ekstremalny współczynnik proporcji** – Współczynniki powyżej 50 mogą sprawić, że kod będzie za wysoki dla typowych skanerów. Trzymaj się zakresu 15‑30 dla większości zastosowań.

## Pełny kod źródłowy (Gotowy do kopiowania)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Uruchom program (`dotnet run` lub naciśnij **F5** w Visual Studio) i zobacz komunikat w konsoli potwierdzający, że pliki znajdują się na dysku.

![Przykładowy wynik generatora kodów kreskowych pokazujący kod DataBar z współczynnikiem proporcji 15](placeholder/path/to/image.png){: .align-center alt="Przykładowy wynik generatora kodów kreskowych pokazujący kod DataBar z współczynnikiem proporcji 15"}

## Podsumowanie

Właśnie ukończyliśmy **przykład generatora kodów kreskowych**, który demonstruje **jak ustawić wymiary**, wybiera właściwe **barcode encode types**, i w końcu **create barcode image c#** pliki, które możesz osadzić gdziekolwiek. Kod jest niewielki, koncepcje przejrzyste, a Ty masz solidną bazę do rozbudowy rozwiązania — np. dodania podpisów tekstowych, obrotu obrazu lub przejścia na inną symbologię.

### Co dalej?

- Eksperymentuj z **różnymi X‑dimension** aby zobaczyć, jak zmienia się tolerancja skanera.  
- Wypróbuj inne **EncodeTypes**, takie jak `Code128` czy `QR`, aby poszerzyć swój zestaw narzędzi.  
- Zautomatyzuj generowanie wsadowe: iteruj po pliku CSV z identyfikatorami produktów i generuj PNG dla każdego.

Jeśli napotkasz problem, zostaw komentarz poniżej lub sprawdź dokumentację Aspose.BarCode — jest pełna przykładów uzupełniających to, co tutaj omówiliśmy.

Miłego kodowania i niech twoje kody kreskowe zawsze skanują się za pierwszym razem!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}