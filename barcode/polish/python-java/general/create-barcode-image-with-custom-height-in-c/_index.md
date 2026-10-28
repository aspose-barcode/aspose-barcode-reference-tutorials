---
category: general
date: 2026-10-28
description: Utwórz obraz kodu kreskowego w C# i dowiedz się, jak dostosować wysokość
  za pomocą API BarcodeGenerator. Przewodnik krok po kroku, jak ustawić własną wysokość
  kodu kreskowego i zmienić wysokość pasków.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: pl
lastmod: 2026-10-28
og_description: Utwórz obraz kodu kreskowego w C# i natychmiast zobacz, jak dostosować
  wysokość. Skorzystaj z tego pełnego przykładu, aby ustawić własną wysokość kodu
  kreskowego przy użyciu BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Utwórz obraz kodu kreskowego o niestandardowej wysokości w C# – pełny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Utwórz obraz kodu kreskowego o niestandardowej wysokości w C#
url: /pl/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego o niestandardowej wysokości w C#

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** i kontrolować jego wymiary, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Korzystając z biblioteki Aspose.BarCode .NET możesz wygenerować kod GS1‑Databar Omni‑Directional, a następnie **jak dostosować wysokość**, aby spełnić dowolne wymagania układu.

Przejdziesz przez kompletny, uruchamialny program, który demonstruje **generator kodów kreskowych w C#**, wyjaśnia każdą ustawioną właściwość i pokazuje dwa różne wyniki — jeden z wysokością paska 30 pikseli, a drugi z wysokością paska 60 pikseli. Po zakończeniu będziesz mógł **zmienić wysokość kodu kreskowego** programowo dla dowolnego typu kodu obsługiwanego przez bibliotekę.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.6+)
- Visual Studio 2022 lub dowolny edytor, który potrafi budować projekty C#
- Pakiet NuGet Aspose.BarCode dla .NET (`Install-Package Aspose.BarCode`)
- Podstawowa znajomość składni C#

> **Porada:** Jeśli używasz potoku CI, dodaj pakiet NuGet do pliku `csproj`, aby kompilacja przywracała go automatycznie.

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy i dodaj wymagane instrukcje `using`. Przestrzenie nazw dają dostęp do `BarcodeGenerator`, `EncodeTypes` oraz pomocników formatu obrazu.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Dlaczego to ważne:** Importowanie właściwych przestrzeni nazw zapobiega błędom kompilacji i sprawia, że API jest widoczne w IntelliSense.

## Krok 2: Zainicjalizuj **generator kodów kreskowych w C#** dla kodu GS1‑Databar Omni‑Directional

Konstruktor przyjmuje dwa argumenty: typ kodu kreskowego (`EncodeTypes.DatabarOmniDirectional`) oraz ciąg danych. Ciąg danych musi być zgodny z formatem identyfikatora aplikacji GS1, np. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Wyjaśnienie:** Obiekt `BarcodeGenerator` jest punktem wejścia dla wszystkich ustawień związanych z kodami kreskowymi. Gdy masz tę instancję, możesz dostosowywać wymiary, kolory i format wyjściowy.

## Krok 3: Zdefiniuj wspólny wymiar X (szerokość w pikselach najwęższego paska)

Wymiar X równy 2 pikselom jest dobrym punktem wyjścia dla większości scenariuszy wyświetlania na ekranie.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dlaczego ustawia się wymiar X?** Kontroluje on całkowitą szerokość kodu kreskowego. Utrzymanie go w stałej wartości zapewnia, że zmiana wysokości paska nie zaburzy wizualnej równowagi.

## Krok 4: **Utwórz obraz kodu kreskowego** o wysokości paska 30 pikseli

Teraz konfigurujemy wysokość paska, zapisujemy pierwszy obraz, a następnie zmieniamy wysokość dla drugiego.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Wynik:** Otrzymujesz plik PNG, w którym każdy pionowy pasek ma wysokość 30 pikseli. Wymiar X pozostaje 2 piksele, więc całkowita szerokość nie ulega zmianie.

## Krok 5: **Jak dostosować wysokość** – zmień wysokość paska na 60 pikseli

Aby zademonstrować **niestandardową wysokość kodu kreskowego**, po prostu przypisz nową wartość do tej samej właściwości i ponownie zapisz.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Kluczowa obserwacja:** Właściwość `BarHeight` jest zmienna; nie musisz ponownie tworzyć instancji `BarcodeGenerator`. Dzięki temu generowanie wielu rozmiarów w pętli lub procesie wsadowym jest tanie.

## Krok 6: Zweryfikuj wynik

Uruchom program konsolowy (`dotnet run`). Po wykonaniu powinieneś zobaczyć dwa pliki PNG w folderze wyjściowym projektu:

- `DatabarBarHeight30Pixels.png` – krótkie paski (30 px)
- `DatabarBarHeight60Pixels.png` – wysokie paski (60 px)

Oba obrazy zawierają te same zakodowane dane, ale ich wizualna wysokość się różni, co jest przydatne przy integracji kodów kreskowych w formularzach, etykietach produktów lub komponentach UI o różnych ograniczeniach przestrzennych.

![Create barcode image with custom height](barcode-example.png){.align-center width="600" alt="Utwórz obraz kodu kreskowego o niestandardowej wysokości"}

> **Wskazówka:** Otwórz pliki PNG w dowolnej przeglądarce obrazów. Wyższy kod kreskowy powinien mieć dokładnie podwójną wysokość w pionie w porównaniu do krótszego, przy zachowaniu identycznego odstępu w poziomie.

## Krok 7: Typowe warianty i przypadki brzegowe

| Situation | Recommended setting |
|-----------|---------------------|
| **Drukowanie na drukarce etykiet o wysokiej rozdzielczości** | Użyj większego wymiaru X (np. 4 px) i zwiększ `BarHeight` proporcjonalnie. |
| **Wyświetlanie na ekranie o niskiej rozdzielczości DPI** | Utrzymaj `XDimension` na poziomie 1 px i `BarHeight` w przedziale 20‑40 px dla czytelności. |
| **Generowanie kodów QR lub kodów 2‑D** | Właściwość `BarHeight` jest ignorowana; użyj `EncodeTypes.QR` i zamiast tego dostosuj `ImageHeight`. |
| **Masowa generacja wielu wysokości** | Iteruj po tablicy wysokości i wywołuj `Save` w pętli; nie ma potrzeby ponownego tworzenia generatora w każdej iteracji. |

### Obsługa nieprawidłowych wysokości

Biblioteka zgłasza `ArgumentOutOfRangeException`, jeśli ustawisz `BarHeight` na wartość nie‑dodatnią. Zabezpiecz się przed tym prostym sprawdzeniem:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Pełny kod źródłowy (gotowy do skopiowania)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Dlaczego to działa:** Wszystkie wymagane ustawienia (`EncodeTypes`, `XDimension`, `BarHeight`) są stosowane przed każdym wywołaniem `Save`. Ta sama instancja `BarcodeGenerator` jest ponownie używana, co jest zarówno oszczędne pod względem pamięci, jak i czytelne.

## Zakończenie

Teraz wiesz, jak **utworzyć pliki obrazu kodu kreskowego** w C# i precyzyjnie **zmienić wysokość kodu kreskowego** przy użyciu API `BarcodeGenerator`. Poprzez dostosowanie `BarHeight.Pixels` uzyskujesz **niestandardową wysokość kodu kreskowego** bez konieczności ponownego tworzenia generatora, co czyni rozwiązanie idealnym do dynamicznego tworzenia etykiet, renderowania UI lub potoków przetwarzania wsadowego.

Następnie poznaj powiązane tematy, takie jak **jak dostosować szerokość**, **dodawanie tekstu czytelnego dla człowieka** lub **eksport do SVG w celu skalowalnego użycia w sieci**. Ten sam schemat — ustaw właściwość, wywołaj `Save` — ma zastosowanie w tych scenariuszach, pozwalając Ci pewnie rozbudować ten przykład.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak zmienić wysokość kodu kreskowego w C# – Kompletny przewodnik](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Przykład generatora kodów kreskowych – tworzenie kodów Planet i RM4SCC z niestandardową wysokością](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Jak utworzyć kod rm4scc i kontrolować jego wysokość w C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}