---
category: general
date: 2026-07-15
description: twórz wielokierunkowy kod kreskowy w C# szybko z Aspose.BarCode – dowiedz
  się, jak generować kod kreskowy w C# z regulowaną wysokością kreski i wymiarem X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: pl
lastmod: 2026-07-15
og_description: Utwórz wszechkierunkowy kod kreskowy w C# z Aspose.BarCode. Opanuj,
  jak generować kod kreskowy w C# poprzez dostosowanie XDimension i BarHeight dla
  perfekcyjnych rezultatów.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Utwórz wszechkierunkowy kod kreskowy w C# – Kompletny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: tworzenie wszechkierunkowego kodu kreskowego w C# – przewodnik krok po kroku
url: /pl/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create omni-directional barcode w C# – Przewodnik krok po kroku

Zastanawiałeś się kiedyś, jak wygenerować kod kreskowy w C#, który spełnia specyfikację symbologii GS1 DataBar Omni‑Directional? Nie jesteś sam. W tym samouczku **utworzymy obrazy kodu kreskowego omni‑directional** od podstaw, dostosujemy wymiar X oraz wysokość pasków — wszystko przy użyciu biblioteki Aspose.BarCode.

Przeprowadzimy Cię przez realistyczny scenariusz: potrzebujesz kompaktowego, wysokiej gęstości kodu kreskowego na etykietę detaliczną i chcesz mieć pełną kontrolę nad jego rozmiarem wizualnym. Po zakończeniu będziesz mieć dwa pliki PNG — jeden z wysokością paska 30 px, a drugi 60 px — gotowe do wstawienia w dowolny proces drukowania.

## Wymagania wstępne

- .NET 6 (lub dowolny nowszy runtime .NET) zainstalowany na Twoim komputerze.  
- Visual Studio 2022 lub VS Code — dowolne ulubione IDE będzie odpowiednie.  
- Darmowy pakiet NuGet Aspose.BarCode dla .NET (`Aspose.BarCode`).

Inne zależności nie są wymagane. Jeśli nigdy nie korzystałeś z NuGet, po prostu otwórz konsolę Package Manager i uruchom:

```powershell
Install-Package Aspose.BarCode
```

## create omni-directional barcode – Zrozumienie podstaw

**Symbologia GS1 DataBar Omni‑Directional** została zaprojektowana do skanowania w dowolnej orientacji, co czyni ją idealną dla etykiet przy krawędzi półki. Gdy wywołujesz `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, biblioteka wykonuje ciężką pracę: koduje dane, stosuje reguły symbologii i przygotowuje obraz rastrowy.

> **Porada:** Zawsze otaczaj surowe dane odpowiednim formatem identyfikatora aplikacji (AI), np. `"(01)12345678901231"` dla GTIN‑14. Dzięki temu skaner wie, co oznaczają cyfry.

## Krok 1 – Konfiguracja generatora kodu kreskowego (how to generate barcode c#)

Najpierw tworzymy obiekt generatora. To podstawa **how to generate barcode c#** z użyciem Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Wartość wyliczenia `EncodeTypes.DatabarOmniDirectional` informuje silnik, której symbologii użyć. Drugi argument to ciąg surowych danych, już otoczony identyfikatorem GTIN AI.

## Krok 2 – Dostosowanie wymiaru X (barcode XDimension)

**Wymiar X kodu kreskowego** kontroluje szerokość najmniejszego paska. Wartość 2 px to dobre wyważenie między czytelnością a kompaktowością dla większości drukarek etykiet.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jeśli potrzebujesz drobniejszego lub grubszego wyglądu, po prostu zmień liczbę. Pamiętaj: wymiar X jest podstawową jednostką; wszystkie pozostałe szerokości pasków są wielokrotnościami tej wartości.

## Krok 3 – Utworzenie pierwszego obrazu z wysokością paska 30 px (barcode BarHeight)

Teraz ustawiamy **wysokość paska (BarHeight)** na 30 px i zapisujemy obraz. Powoduje to powstanie kodu kreskowego o umiarkowanym rozmiarze, który dobrze pasuje do standardowej etykiety.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapisuje plik PNG na dysku. Możesz zamienić `BarCodeImageFormat.Jpeg`, jeśli wolisz wyjście w formacie JPEG.

## Krok 4 – Zwiększenie wysokości paska do 60 px dla większych etykiet (barcode BarHeight)

Czasami potrzebny jest większy kod kreskowy — na przykład dla etykiety półkowej, która znajduje się dalej od skanera. Podwójmy wysokość.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Zauważ, że **nie** musimy ponownie tworzyć generatora; po prostu modyfikujemy parametr i ponownie używamy tego samego obiektu. To oszczędza pamięć i utrzymuje kod w porządku.

## Krok 5 – Zapisanie drugiego obrazu (how to generate barcode c#)

Na koniec zapisujemy drugi plik PNG. Masz teraz dwa pliki różniące się jedynie wysokością paska.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Oczekiwany wynik

- `DatabarBarHeight30Pixels.png` – kod kreskowy omni‑directional o wysokości 30 px.  
- `DatabarBarHeight60Pixels.png` – te same dane, ale z kodem kreskowym o wysokości 60 px.

Otwórz pliki w dowolnym przeglądarce obrazów; zobaczysz wyraźne, skanowalne paski, które spełniają specyfikację GS1 DataBar Omni‑Directional.

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli potrzebuję innego wymiaru X?

Po prostu przypisz nową wartość przed wywołaniem `Save`. Dla ultra‑wysokiej gęstości druku możesz zejść do 1 px, ale najpierw przetestuj ze swoim skanerem — niektóre urządzenia mają problemy z paskami mniejszymi niż 2 px.

### Czy mogę dodać tekst czytelny dla człowieka pod kodem kreskowym?

Tak. Ustaw `barcodeGenerator.Parameters.Barcode.CodeText` na ciąg znaków i opcjonalnie zmień `barcodeGenerator.Parameters.Barcode.CodeLocation` na `BarCodeTextLocation.Below`. Jest to przydatne w środowiskach detalicznych, gdzie numer GTIN musi być widoczny.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Czy PNG jest najlepszym formatem do druku?

PNG jest bezstratny, co zachowuje ostre krawędzie potrzebne skanerom kodów kreskowych. Jeśli Twój system downstream wymaga innego formatu (TIFF, BMP), po prostu zmień wyliczenie `BarCodeImageFormat`.

## Pełny działający przykład (create omni-directional barcode)

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Skopiuj i wklej go do nowego projektu konsolowego i naciśnij **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Uruchom program, sprawdź folder wyjściowy i zobaczysz dwa pliki PNG dokładnie tak, jak opisano.

## Podsumowanie

Pokazaliśmy, jak **generować kod C#** tworzący **create omni-directional barcode** przy użyciu Aspose.BarCode. Dzięki dostosowaniu **barcode XDimension** i **barcode BarHeight** uzyskujesz precyzyjną kontrolę nad rozmiarem wizualnym bez utraty niezawodności skanowania.

## Co dalej?

- Eksperymentuj z innymi ustawieniami **GS1 DataBar Omni-Directional**, takimi jak `Color` czy `Margin`.  
- Łącz wiele kodów kreskowych na jednej płaszczyźnie przy użyciu `Graphics` w celu tworzenia złożonych projektów etykiet.  
- Zintegruj generator z API webowym, aby Twoja platforma e‑commerce mogła generować kody kreskowe na żądanie.

Masz własny pomysł, którym chcesz się podzielić? Dodaj komentarz i kontynuujmy dyskusję. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod kreskowy – konfiguracja Code 39 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak utworzyć strefę ciszy (quiet zone) dla ITF-14 przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak utworzyć strefę ciszy (quiet zone) dla Code 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}