---
category: general
date: 2026-10-02
description: Szybko utwórz kod kreskowy typu stacked databars w C#. Dowiedz się, jak
  ustawić XDimension, dostosować proporcje i eksportować obrazy PNG przy użyciu generatora
  kodów kreskowych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: pl
lastmod: 2026-10-02
og_description: Utwórz kod kreskowy stacked databars w C# z pełnym przykładem kodu.
  Dostosuj XDimension, zmień proporcje i zapisz pliki PNG w kilku linijkach.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Utwórz skumulowany kod kreskowy z paskami danych w C# – szybki poradnik
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Utwórz kod kreskowy ze skumulowanymi paskami danych w C# – przewodnik krok
  po kroku
url: /pl/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy stacked databars w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć kod kreskowy stacked databars** w projekcie .NET, ten samouczek pokaże Ci dokładnie, jak to zrobić. Zobaczysz, jak skonfigurować wymiar X, zmienić współczynniki proporcji i zapisać wynik jako pliki PNG — wszystko przy użyciu biblioteki Aspose.BarCode.

Generowanie kodu kreskowego stacked DataBar nie wymaga skomplikowanego potoku graficznego. Po zakończeniu tego przewodnika będziesz mieć dwa gotowe do użycia obrazy PNG ilustrujące różne współczynniki proporcji oraz zrozumiesz, dlaczego te parametry mają znaczenie dla niezawodności skanowania.

## Czego będziesz potrzebować

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+)
- Visual Studio 2022 lub dowolne IDE C#
- **Aspose.BarCode for .NET** pakiet NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Uprawnienia do zapisu w folderze, w którym zostaną zapisane pliki PNG

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nową aplikację konsolową (lub dodaj kod do istniejącego projektu) i zaimportuj wymagane przestrzenie nazw:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Dlaczego to ważne:** `Aspose.BarCode.Generation` dostarcza klasę `BarcodeGenerator`, natomiast `Aspose.BarCode` zawiera wyliczenie `BarCodeImageFormat` używane do zapisywania obrazów.

## Krok 2: Zainicjalizuj generator dla stacked omnidirectional DataBar

Wartość `EncodeTypes.DatabarStackedOmniDirectional` wybiera symbologię stacked DataBar. Ciąg danych musi spełniać format GS1 Application Identifier (AI); tutaj używamy przykładowej wartości GTIN‑14.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Dlaczego to ważne:** Wybrany typ kodowania informuje bibliotekę, aby renderowała kod kreskowy *stacked*, co jest niezbędne dla etykiet o wysokiej gęstości, gdzie przestrzeń pionowa jest ograniczona.

## Krok 3: Zdefiniuj rozmiar modułu (wymiar X) w pikselach

Wymiar X kontroluje szerokość najmniejszego słupka (tzw. „modułu”). Wartość 2 piksele sprawdza się w większości wyjść o rozdzielczości ekranu.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dlaczego to ważne:** Skanery interpretują szerokość modułu jako podstawową jednostkę miary. Zbyt mała wartość może powodować rozmyte wydruki; zbyt duża marnuje miejsce.

## Krok 4: Zapisz pierwszy obraz z współczynnikiem proporcji 15

Właściwość `AspectRatio` wpływa na stosunek wysokości do szerokości każdego segmentu stacked. Współczynnik proporcji 15 jest powszechnym domyślnym ustawieniem dla aplikacji detalicznych.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Dlaczego to ważne:** Niższy współczynnik proporcji daje bardziej płaski kod kreskowy, co może ułatwić skanowanie na niektórych materiałach etykietowych. Format PNG zachowuje jakość bezstratną do testów.

## Krok 5: Zmień współczynnik proporcji na 30 i zapisz drugi obraz

Zwiększenie współczynnika proporcji sprawia, że każdy segment stacked jest wyższy, co może poprawić niezawodność skanowania na tle o niskim kontraście.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Dlaczego to ważne:** Różni detaliści lub partnerzy logistyczni mogą wymagać określonych wymiarów kodu kreskowego. Udostępnienie obu wersji pozwala szybko porównać wydajność skanowania.

## Pełny, działający przykład

Poniżej znajduje się kompletny program, który możesz skopiować i wkleić do `Program.cs`. Kompiluje się i uruchamia bez modyfikacji po zainstalowaniu pakietu NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu tworzy dwa pliki w folderze wykonywania:

| Nazwa pliku                  | Współczynnik proporcji | Opis wizualny |
|------------------------------|------------------------|----------------|
| `DatabarAspectRatio15.png`   | 15                     | Krótszy, bardziej płaski kod kreskowy stacked |
| `DatabarAspectRatio30.png`   | 30                     | Wyższy, bardziej wydłużony kod kreskowy stacked |

Możesz otworzyć pliki PNG dowolną przeglądarką obrazów, aby zweryfikować, że kod kreskowy renderuje się poprawnie.

![Przykład kodu kreskowego stacked databars](placeholder-image.png){alt="Przykład kodu kreskowego stacked databars"}

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę użyć innego wymiaru X?** | Tak. Typowe wartości mieszczą się w przedziale od 1 do 4 pikseli. Większe wartości zwiększają rozmiar kodu kreskowego, ale mogą poprawić czytelność na drukarkach o niskiej rozdzielczości. |
| **Co zrobić, jeśli potrzebuję innej symbologii?** | Zastąp `EncodeTypes.DatabarStackedOmniDirectional` inną wartością `EncodeTypes`, taką jak `DatabarStacked` (nie‑omnidirectional) lub `DatabarLimited`. |
| **Jak zmienić format wyjściowy?** | Użyj `BarCodeImageFormat.Jpeg`, `Gif` lub `Bmp` w wywołaniu `Save`. |
| **Czy format GTIN‑14 jest obowiązkowy?** | Symbologia DataBar oczekuje ciągu numerycznego z prefiksem odpowiedniego AI (np. `(01)` dla GTIN‑14). Dostosuj dane do swojego przypadku użycia. |
| **A co z ustawieniami DPI?** | Generator respektuje właściwość `Resolution`. Dla wydruków wysokiej rozdzielczości ustaw `barcodeGen.Parameters.ImageResolution.DpiX` i `DpiY` odpowiednio. |

## Porady profesjonalne

- **Batch generation:** Owiń logikę zapisu w pętli i podaj listę GTIN‑ów, aby automatycznie wygenerować tysiące kodów kreskowych.
- **Validation:** Użyj `barcodeGen.Validate()` przed zapisem, aby wcześnie wykryć nieprawidłowe dane.
- **Performance:** Ponowne użycie tej samej instancji `BarcodeGenerator` (z jedynie zmianą parametrów) jest szybsze niż tworzenie nowego obiektu dla każdego obrazu.

## Kolejne kroki

Teraz, gdy możesz **utworzyć kod kreskowy stacked databars** z niestandardowymi współczynnikami proporcji, rozważ dalsze eksplorowanie:

- Dodanie tekstu czytelnego dla człowieka pod kodem kreskowym (`barcodeGen.Parameters.Barcode.CodeText`).
- Eksport do **PDF** w celu uzyskania drukowalnych arkuszy etykiet (`BarCodeImageFormat.Pdf`).
- Integrację generatora z interfejsem web API, aby udostępniać kody kreskowe na żądanie.
- Eksperymentowanie z innymi **drugorzędnymi słowami kluczowymi**, takimi jak *C# barcode generator* i *barcode aspect ratio*, aby dopasować implementację do konkretnego sprzętu.

Miłego kodowania i ciesz się elastycznością, jaką Aspose.BarCode wprowadza do Twoich projektów kodów kreskowych w C#!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy databar stacked w C# – przewodnik krok po kroku](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [databar stacked omnidirectional barcode w C# – Kompletny przewodnik](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Jak utworzyć obrazy PNG databar w C# i Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}