---
category: general
date: 2026-09-29
description: Utwórz kod kreskowy planet w C# z wypełnionymi i pustymi paskami – przewodnik
  krok po kroku z użyciem Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: pl
lastmod: 2026-09-29
og_description: Szybko utwórz kod kreskowy planet w C#. Dowiedz się, jak renderować
  wypełnione paski, przełączać na puste paski i regulować wymiar X przy użyciu Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Utwórz kod kreskowy planety z wypełnionymi i pustymi paskami – samouczek
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak stworzyć kod kreskowy planety z wypełnionymi i pustymi słupkami
url: /pl/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy planet z wypełnionymi i pustymi paskami

Jeśli potrzebujesz **utworzyć kod kreskowy planet** w C#, ten przewodnik pokaże Ci dokładnie, jak wygenerować zarówno wersje z wypełnionymi, jak i pustymi paskami. Zobaczysz, jak ustawić szerokość paska (X‑dimension), przełączyć właściwość `FilledBars` oraz zapisać wyniki jako pliki PNG — wszystko przy użyciu biblioteki Aspose.Barcode.

Generowanie kodów kreskowych pocztowych jest powszechnym wymogiem w systemach wysyłkowych, aplikacjach list mailingowych i pulpitach logistycznych. Po zakończeniu tego samouczka będziesz mieć dwa gotowe do użycia pliki PNG, które możesz osadzić w raportach, e‑mailach lub wydrukach.

## Wymagania wstępne

| Wymaganie | Dlaczego jest ważne |
|-------------|----------------|
| .NET 6.0 or later | Zapewnia środowisko uruchomieniowe dla przykładu w C#. |
| Visual Studio 2022 (or any C# IDE) | Umożliwia kompilację i uruchomienie kodu. |
| **Aspose.Barcode for .NET** NuGet package | Dostarcza klasę `BarcodeGenerator` oraz `EncodeTypes.Planet`. Zainstaluj ją poleceniem `dotnet add package Aspose.Barcode`. |
| Write permission to a folder on disk | Metoda `Save` zapisuje pliki PNG w podanej ścieżce. |

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy (lub dodaj kod do istniejącego) i odwołaj się do przestrzeni nazw Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Te dyrektywy `using` zapewniają dostęp do `BarcodeGenerator`, `EncodeTypes` oraz wyliczeń formatów obrazu potrzebnych w tym samouczku.

## Krok 2: Utwórz kod kreskowy Planet z domyślnymi (wypełnionymi) paskami

Pierwszy kod kreskowy używa domyślnego renderowania biblioteki, które wypełnia paski.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Dlaczego to działa:**  
`EncodeTypes.Planet` informuje Aspose.Barcode, aby użył symboliki **Planet**, będącej kodem pocztowym stosowanym przez United States Postal Service. Właściwość `XDimension` kontroluje szerokość każdego paska; ustawienie jej na 4 piksele powoduje, że kod kreskowy dobrze drukuje się na standardowych drukarkach etykiet. Domyślnie `FilledBars` ma wartość `true`, więc paski są wypełnione.

## Krok 3: Utwórz kod kreskowy Planet z pustymi paskami

Aby wygenerować te same dane z *pustymi* paskami, wystarczy odwrócić flagę `FilledBars`, pozostawiając pozostałe ustawienia niezmienione.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Dlaczego to jest ważne:**  
Niektóre systemy mailingowe wymagają stylu **empty‑bars**, aby poprawić czytelność, gdy kod kreskowy jest drukowany na ciemnym tle lub przy użyciu kontrastowego schematu kolorów. Ustawiając `FilledBars = false`, generator rysuje jedynie kontury pasków, pozostawiając ich wnętrze przezroczyste.

## Oczekiwany wynik

Po uruchomieniu programu, folder `C:\Barcodes` (lub wybrana przez Ciebie ścieżka) zawiera dwa pliki PNG:

| Plik | Opis wizualny |
|------|---------------------|
| `PlanetFilledBars.png` | Paski są solidnymi czarnymi prostokątami na białym tle. |
| `PlanetEmptyBars.png`  | Paski są czarnymi konturami; wnętrze każdego paska jest przezroczyste (pokazuje tło). |

Oba obrazy kodują ten sam ciąg numeryczny `"123456"` i mają szerokość paska 4 piksele, co zapewnia spójny wygląd poza stylem wypełnienia.

## Typowe warianty i przypadki brzegowe

### Zmiana szerokości paska

Jeśli Twoja drukarka etykiet wymaga innej szerokości paska, zmodyfikuj wartość `XDimension.Pixels`. Dla drukarek wysokiej rozdzielczości wartość **2** lub **3** piksele może być lepsza; dla drukarek niskiej rozdzielczości **5** lub **6** pikseli może poprawić niezawodność skanowania.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Użycie innego formatu obrazu

Aspose.Barcode obsługuje PNG, JPEG, BMP, GIF i TIFF. Zamień `BarCodeImageFormat.Png` na inną wartość wyliczenia, aby dopasować do swojego dalszego przepływu pracy.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generowanie wielu kodów kreskowych w pętli

Gdy potrzebujesz partii kodów kreskowych Planet (np. dla listy mailingowej), otocz logikę generatora pętlą `foreach` i zmieniaj ciąg danych w każdej iteracji.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Obsługa nieprawidłowego wejścia

Symbolika Planet akceptuje wyłącznie ciągi numeryczne o długości **5‑8** cyfr. Podanie nieprawidłowej wartości powoduje wyrzucenie `ArgumentException`. Zabezpiecz się przed tym przy pomocy prostej metody walidacji.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Porada: Zweryfikuj kod kreskowy za pomocą emulatora skanera

Aspose.Barcode zawiera klasę `BarcodeReader`, którą możesz użyć do potwierdzenia, że wygenerowany obraz dekoduje się do pierwotnych danych.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Jeśli wyjście pokazuje `"123456"` dla obu plików, kod kreskowy został wygenerowany prawidłowo.

## Zakończenie

Teraz wiesz, jak **utworzyć kod kreskowy planet** w C# zarówno w stylu wypełnionych, jak i pustych pasków, kontrolować **Planet barcode XDimension** oraz zapisywać wyniki w formacie PNG przy użyciu biblioteki **Aspose.Barcode**. Dostosuj szerokość paska, zmień format obrazu lub iteruj po kolekcji wartości, aby dopasować się do dowolnego przepływu pracy z kodami pocztowymi.

Następnie możesz zbadać:

* **Dodawanie tekstu czytelnego dla człowieka** pod kodem kreskowym (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Osadzanie kodów kreskowych w dokumentach PDF** przy użyciu Aspose.PDF.
* **Generowanie innych symbolik pocztowych** takich jak **USPS POSTNET** lub **Intelligent Mail**.

Śmiało eksperymentuj z parametrami i integruj kod w swoim systemie wysyłkowym lub mailingowym. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}