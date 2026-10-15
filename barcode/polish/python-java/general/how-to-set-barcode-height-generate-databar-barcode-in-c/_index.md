---
category: general
date: 2026-10-12
description: Jak ustawić wysokość kodu kreskowego i wygenerować kod DataBar w C# przy
  użyciu Aspose.BarCode. Postępuj zgodnie z przewodnikiem krok po kroku z pełnym kodem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: pl
lastmod: 2026-10-12
og_description: Jak ustawić wysokość kodu kreskowego w C# i wygenerować kod DataBar
  przy użyciu Aspose.BarCode. Poznaj pełny kod, dlaczego każdy krok ma znaczenie i
  jak zmienić wysokość kodu kreskowego.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Jak ustawić wysokość kodu kreskowego i wygenerować kod DataBar w C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak ustawić wysokość kodu kreskowego, wygenerować kod DataBar w C#
url: /pl/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić wysokość kodu kreskowego, wygenerować kod DataBar w C#

Jeśli potrzebujesz **how to set barcode** wymiarów programowo, ten przewodnik pokaże Ci dokładne kroki. Nauczysz się, jak wygenerować kod DataBar Omni‑directional, dostosować jego wysokość i zapisać obie wersje jako pliki PNG.

Zmiana wysokości pasków kodu kreskowego jest częstym wymogiem, gdy integrujesz kody kreskowe w paragonach, etykietach produktów lub na ekranach mobilnych. Poniższy przykład używa biblioteki Aspose.BarCode, która obsługuje pełen zakres symbologii GS1 DataBar.

## Co osiągniesz

* **how to set barcode** wysokość dla kodu DataBar Omni‑directional  
* **generate barcode c#** kod, który tworzy dwa obrazy o różnych wysokościach  
* zrozumieć **how to create databar** symbole i dlaczego wysokość pasków ma znaczenie  
* zastosować logikę **change barcode height** bez ponownego tworzenia generatora  

Nie są wymagane żadne zewnętrzne narzędzia poza pakietem NuGet Aspose.BarCode oraz środowiskiem uruchomieniowym .NET 6+.

## Wymagania wstępne

* .NET 6 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolny edytor C#)  
* Aspose.BarCode dla .NET – zainstaluj za pomocą `dotnet add package Aspose.BarCode`  

> **Pro tip:** Użyj darmowej wersji próbnej licencji od Aspose, jeśli nie masz klucza komercyjnego; API działa w ten sam sposób.

## Krok 1: Zainstaluj pakiet Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, w której znajduje się klasa `BarcodeGenerator`, której użyjemy do **generate barcode c#** obrazów.

## Krok 2: Utwórz generator kodu DataBar

Pierwszym konkretnym działaniem dla **how to set barcode** parametrów jest utworzenie instancji `BarcodeGenerator` z żądaną symbologią i ciągiem danych.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` produkuje kompaktowy, omnidirectional DataBar, który może być skanowany pod każdym kątem — idealny dla małych etykiet.

## Krok 3: Ustaw wspólne parametry kodu kreskowego (w tym początkową wysokość paska)

Teraz odpowiadamy na **how to set barcode** X‑dimension i wysokość paska przed zapisaniem pierwszego obrazu.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension kontroluje ogólną szerokość każdego paska; ustawienie 2 piksele zapewnia czytelny, ostry obraz na większości ekranów. Krok **change barcode height** później ponownie użyje tego samego generatora, oszczędzając czas i pamięć.

## Krok 4: Zapisz pierwszy obraz kodu kreskowego (wysokość 30 pikseli)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Plik `DatabarHeight30.png` zawiera teraz kod DataBar z wysokością paska wynoszącą 30 pikseli.

## Krok 5: Zmień tylko wysokość paska na 60 pikseli

Aby zademonstrować **change barcode height**, modyfikujemy jedynie właściwość `BarHeight`. Wszystkie pozostałe ustawienia pozostają niezmienione, co jest najefektywniejszym sposobem na uzyskanie wielu rozmiarów z jednego generatora.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Krok 6: Zapisz drugi obraz kodu kreskowego (wysokość 60 pikseli)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Masz teraz dwa pliki PNG, każdy o innej wysokości paska, ale z identycznymi danymi i X‑dimension.

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się kompletny program, który możesz skopiować‑wkleić do nowej aplikacji konsolowej (`dotnet new console`) i od razu uruchomić.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Oczekiwany wynik

Uruchomienie programu tworzy dwa pliki w katalogu roboczym aplikacji:

* `DatabarHeight30.png` – kod DataBar z paskami o wysokości 30 pikseli.  
* `DatabarHeight60.png` – ten sam kod, ale każdy pasek jest dwa razy wyższy.

Oba obrazy można otworzyć w dowolnym przeglądarce obrazów lub osadzić bezpośrednio w plikach PDF, stronach HTML czy wydrukowanych etykietach.

## Dlaczego dostosowanie wysokości paska ma znaczenie

* **Scanning reliability:** Niektóre skanery mają trudności z bardzo krótkimi paskami na nośnikach o niskiej rozdzielczości; zwiększenie wysokości poprawia wykrywalność.  
* **Design constraints:** Aplikacja mobilna może wymagać kompaktowego kodu (30 px), podczas gdy wydrukowany paragon może potrzebować większego (60 px).  
* **Regulatory compliance:** Niektóre branże nakładają minimalną wysokość paska dla symboli GS1 DataBar.

Ponowne użycie tej samej instancji `BarcodeGenerator` eliminuje konieczność ponownego parsowania ciągu danych, co jest szczególnie korzystne w środowiskach o wysokiej przepustowości.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Zalecana modyfikacja |
|-----------|-------------------|
| Potrzeba innej X‑dimension | Zmień `XDimension.Pixels` przed pierwszym `Save`. |
| Chcesz inną symbologię (np. DataBar Stacked) | Użyj `EncodeTypes.DatabarStacked` przy konstruowaniu `BarcodeGenerator`. |
| Musisz osadzić kod w PDF | Użyj `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` i dodaj strumień do biblioteki PDF. |
| Działasz na .NET Framework 4.6 | Ten sam kod działa; wystarczy odwołać się do odpowiedniego zestawu Aspose.BarCode. |

## Porady pro dla niezawodnego generowania kodów kreskowych

* **Cache the generator** when you generate many barcodes with the same data but different sizes.  
* **

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z krok‑po‑kroku wyjaśnieniami, pomagając opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować i dostosowywać wysokość kodu kreskowego dla jednowymiarowego Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak tworzyć obrazy PNG databar w C# przy użyciu Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Jak generować kod kreskowy o niestandardowym rozmiarze i zapisać obraz w C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}