---
category: general
date: 2026-09-26
description: Dowiedz się, jak stworzyć obraz kodu kreskowego pocztowego w C#. Ten
  przewodnik pokazuje, jak wygenerować kod Planet i ustawić wysokość kodu kreskowego
  dla niestandardowego wyjścia.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: pl
lastmod: 2026-09-26
og_description: Twórz obraz kodu pocztowego w C# szybko. Skorzystaj z tego samouczka,
  aby wygenerować kod planet, ustawić wysokość kodu i uzyskać wysokiej jakości pliki
  PNG.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Tworzenie obrazu kodu pocztowego z niestandardowymi wysokościami w C# –
  przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Jak stworzyć obraz kodu kreskowego pocztowego o niestandardowych wysokościach
  w C#
url: /pl/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego pocztowego o niestandardowych wysokościach w C#

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego pocztowego** dla etykiet mailingowych, ten tutorial pokaże Ci dokładne kroki. Dowiesz się, jak wygenerować kod Planet, dostosować wysokość pasków i zapisać wynik jako plik PNG — wszystko przy użyciu biblioteki Aspose.BarCode dla .NET.

Tworzenie obrazu kodu kreskowego nie wymaga zewnętrznego narzędzia graficznego. Po zakończeniu tego przewodnika będziesz w stanie tworzyć zarówno kody o domyślnej wysokości, jak i o wysokości dostosowanej, zgodne ze standardami Planet i RM4SCC, gotowe do integracji w dowolnym procesie wysyłkowym.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE C#)  
* Aspose.BarCode dla .NET dodany przez NuGet (`Install-Package Aspose.BarCode`)  

Nie są potrzebne dodatkowe konfiguracje; biblioteka obsługuje renderowanie obrazu wewnętrznie.

## Krok 1: Utwórz projekt i zaimportuj przestrzenie nazw

Utwórz nową aplikację konsolową i dodaj wymagane dyrektywy `using`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Te przestrzenie nazw udostępniają klasę `BarcodeGenerator` oraz wyliczenie `EncodeTypes`, które wykorzystasz do **generowania kodu planet** i innych formatów pocztowych.

## Krok 2: Utwórz kod Planet z domyślną wysokością pasków

Pierwszy przykład tworzy kod Planet przy użyciu domyślnej wysokości pasków biblioteki. Demonstracja pokazuje podstawowy wynik przed zastosowaniem własnych wymiarów.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Dlaczego to ważne:** Domyślna wysokość jest odpowiednia dla większości drukarek etykiet, ale niektóre procesy wymagają wyższych pasków dla zwiększonej niezawodności skanowania. Powyższy kod dostarcza obraz referencyjny do porównania z wersją o niestandardowej wysokości.

## Krok 3: Zastosuj niestandardową wysokość pasków do kodu Planet

Aby **ustawić wysokość kodu ręcznie**, przypisz wartość w pikselach do `BarHeight.Pixels`. Poniższy fragment tworzy kod Planet o wysokości 100 pikseli.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Wskazówka:** Wybierz wysokość pasków dopasowaną do DPI Twojej drukarki. Dla drukarki 300 dpi, 100 pikseli to w przybliżeniu 0,33 cala, co często jest zalecane dla skanerów pocztowych.

## Krok 4: Wygeneruj kod RM4SCC z domyślną wysokością

RM4SCC to kolejna popularna symbologia pocztowa. Proces jest analogiczny do przykładu Planet, ale używa `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Ten krok potwierdza, że logika **generatora kodów z niestandardową wysokością** działa również dla innych formatów pocztowych.

## Krok 5: Zastosuj niestandardową wysokość do kodu RM4SCC

Na koniec, dostosuj wysokość pasków dla kodu RM4SCC w taki sam sposób, jak w przypadku kodu Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Oczekiwany wynik

Uruchomienie pełnego programu generuje cztery pliki PNG w katalogu wyjściowym projektu:

| Nazwa pliku                               | Wysokość pasków | Symbolika |
|-------------------------------------------|-----------------|-----------|
| `PostalPlanetBarHeightDefault.png`       | domyślna        | Planet    |
| `PostalPlanetBarHeight100Pixels.png`     | 100 px          | Planet    |
| `PostalRM4SCCBarHeightDefault.png`       | domyślna        | RM4SCC    |
| `PostalRM4SCCBarHeight100Pixels.png`     | 100 px          | RM4SCC    |

Każdy obraz przedstawia wyraźny, wysokokontrastowy kod gotowy do druku na etykietach mailingowych. Pliki PNG możesz otworzyć w dowolnym przeglądarce obrazów, aby zweryfikować wymiary pasków.

## Częste pytania i przypadki brzegowe

**Co zrobić, gdy potrzebna jest wysokość pasków w milimetrach zamiast w pikselach?**  
Biblioteka pracuje w pikselach, ponieważ bezpośrednio mapuje je na rozdzielczość bitmapy. Przelicz milimetry na piksele przy użyciu DPI drukarki:  
`pixels = (mm / 25.4) * DPI`. Następnie ustaw `BarHeight.Pixels` na obliczoną wartość.

**Czy mogę zmienić wysokość pasków po wywołaniu `Save`?**  
Nie. Obraz kodu jest renderowany w momencie wywołania `Save`. Wszystkie parametry należy ustawić przed wywołaniem tej metody.

**Czy większy X‑Dimension jest wymagany przy wyższych paskach?**  
Zwiększenie `XDimension` powoduje szersze moduły, co może poprawić czytelność na drukarkach o niskiej rozdzielczości. Jednak zwiększa to także całkowitą szerokość kodu. Testuj oba parametry, aby znaleźć optymalny kompromis dla rozmiaru etykiety.

**Czy ten sam kod zadziała na .NET Framework 4.8?**  
Tak. Aspose.BarCode obsługuje .NET Framework 4.6.2 i nowsze, więc możesz celować w starsze środowiska bez zmian.

## Pełny kod źródłowy do szybkiego skopiowania

Poniżej znajduje się kompletny, gotowy do uruchomienia program, który zawiera wszystkie opisane wyżej kroki.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Uruchom program, a konsola potwierdzi, że każdy obraz został zapisany. Teraz możesz osadzić te pliki PNG w szablonach etykiet mailingowych, wydrukować je lub wysłać do zewnętrznego API logistycznego.

## Podsumowanie

Wiesz już, jak **utworzyć obrazy kodów kreskowych pocztowych** w C# przy użyciu Aspose.BarCode. Przewodnik obejmował generowanie kodu Planet, regulację wysokości pasków oraz zastosowanie tej samej techniki do kodów RM4SCC. Kontrolując `XDimension` i `BarHeight.Pixels`, uzyskasz precyzyjne wyniki wizualne spełniające wymogi usług pocztowych.

Następnie odkryj powiązane tematy, takie jak **generowanie kodów QR do śledzenia**, **osadzanie kodów kreskowych w fakturach PDF** czy **przetwarzanie wsadowe wielu obrazów kodów**. Regulacja wysokości pasków to tylko jeden z elementów; możesz także dostosować kolory, dodać tekst czytelniczy lub eksportować do SVG dla zastosowań webowych.

Powodzenia w kodowaniu i niech Twoje przesyłki skanują się bezbłędnie!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu oraz krok‑po‑kroku wyjaśnienia, pomagające opanować dodatkowe funkcje API i eksplorować alternatywne podejścia w własnych projektach.

- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Create Postal Barcode Images – Change Barcode Height Easily](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}