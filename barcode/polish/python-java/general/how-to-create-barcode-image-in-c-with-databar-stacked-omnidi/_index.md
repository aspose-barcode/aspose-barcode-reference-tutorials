---
category: general
date: 2026-11-17
description: Utwórz obraz kodu kreskowego w C# przy użyciu biblioteki Barcode Generator.
  Skorzystaj z tego przewodnika, aby krok po kroku nauczyć się generować kody DataBar
  stacked omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: pl
lastmod: 2026-11-17
og_description: Utwórz obraz kodu kreskowego w C# w zwięzłym przykładzie. Dowiedz
  się, jak generować kody DataBar stacked omnidirectional przy użyciu biblioteki Barcode
  Generator.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Tworzenie obrazu kodu kreskowego w C# – kompletny przewodnik po kodach DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak utworzyć obraz kodu kreskowego w C# z DataBar stacked omnidirectional
url: /pl/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego w C# z DataBar stacked omnidirectional

Jeśli potrzebujesz **create barcode image** w aplikacji .NET, ten tutorial pokazuje kompletną, gotową‑do‑uruchomienia rozwiązanie. Zobaczysz dokładnie, jak używać API **Barcode Generator C#**, aby wygenerować stacked omnidirectional DataBar, który jest formatem objętym zapytaniem *how to generate databar*.

Przewodnik przechodzi przez każdy wymagany krok — od instalacji biblioteki po precyzyjne dostosowanie współczynnika proporcji — tak abyś mógł skopiować kod, uruchomić go i od razu otrzymać plik PNG. Nie ma potrzeby przeglądania dodatkowej dokumentacji.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany (przykład działa również z .NET Framework 4.7+)
* Środowisko programistyczne, takie jak Visual Studio 2022 lub VS Code
* Pakiet NuGet **Aspose.BarCode for .NET** (biblioteka udostępniająca `BarcodeGenerator`)

Możesz dodać pakiet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Użyj flagi `--version`, aby zablokować pakiet do najnowszej stabilnej wersji, np. `dotnet add package Aspose.BarCode --version 23.9`.

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy i odwołaj się do wymaganych przestrzeni nazw. Ten krok przygotowuje środowisko dla kodu **barcode generator c#**, który pojawi się dalej.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

Przestrzeń nazw `Aspose.BarCode.Generation` zawiera klasę `BarcodeGenerator`, będącą rdzeniem przepływu pracy **create barcode image**.

## Krok 2: Zainicjalizuj BarcodeGenerator dla stacked omnidirectional DataBar

Generator potrzebuje dwóch informacji: typu kodu kreskowego oraz danych do zakodowania. Wartość wyliczeniowa `EncodeTypes.DatabarStackedOmniDirectional` wybiera dokładny wariant DataBar wymagany w scenariuszach *how to generate databar*.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Dlaczego to ważne:* Wybranie prawidłowej wartości `EncodeTypes` zapewnia, że powstały obraz spełnia specyfikacje branżowe dla skanowania w handlu detalicznym.

## Krok 3: Zdefiniuj rozmiar modułu (wymiar X) w pikselach

Gęstość wizualna kodu kreskowego jest kontrolowana przez wymiar X. Ustawienie go na rozsądną wartość w pikselach gwarantuje czytelność obrazu zarówno na ekranie, jak i w druku.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Jeśli potrzebujesz większego kodu kreskowego do druku o niskiej rozdzielczości, zwiększ odpowiednio wartość w pikselach.

## Krok 4: Dostosuj współczynnik proporcji DataBar, aby wiersze były wyższe

Stacked omnidirectional DataBar składa się z dwóch wierszy. Modyfikacja `AspectRatio` pozwala kontrolować wysokość każdego wiersza, co może być przydatne, gdy domyślny rozmiar wydaje się zbyt ciasny.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Współczynnik proporcji `15` jest powszechnym wyborem dla etykiet detalicznych; możesz eksperymentować z wartościami od `10` do `20`, aby spełnić konkretne wymagania układu.

## Krok 5: Zapisz wygenerowany kod kreskowy jako obraz PNG

Na koniec zapisz obraz na dysku. PNG jest bezstratny, co czyni go idealnym do dalszego przetwarzania lub osadzania w plikach PDF.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Uruchomienie programu tworzy plik o nazwie **DatabarAspectRatio15.png** w katalogu wyjściowym projektu. Otworzenie pliku pokazuje czysty, wysokokontrastowy kod kreskowy gotowy do skanowania.

### Oczekiwany wynik

Zapisany obraz wygląda podobnie do ilustracji poniżej (rzeczywisty wizualny przykład został pominięty dla zwięzłości).

*Alt text for the example image:* **create barcode image** – plik PNG wyświetlający stacked omnidirectional DataBar z współczynnikiem proporcji 15.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Different payload length** | Zastąp ciąg GTIN dowolną prawidłową treścią DataBar (np. `(01)01234567890123`). |
| **Higher resolution for large prints** | Zwiększ `XDimension.Pixels` do 4 lub 5 i opcjonalnie ustaw `Resolution` w `Parameters.Image`. |
| **Other DataBar formats** | Użyj `EncodeTypes.DatabarStacked` dla dwuwierszowego wariantu stacked bez możliwości omnidirectional. |
| **Saving as JPEG** | Zmień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` i opcjonalnie ustaw `Quality`. |

Te warianty odpowiadają na szersze pytanie *how to generate databar*, pokazując, że ten sam generator może być ponownie skonfigurowany dla wielu rodzin DataBar.

## Pełny kod źródłowy

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Skopiuj kod do pliku `Program.cs`, przywróć pakiety NuGet i uruchom `dotnet run`. Konsola potwierdzi lokalizację obrazu, a Ty możesz otworzyć PNG, aby zweryfikować rezultat **create barcode image**.

## Zakończenie

Teraz wiesz, jak **create barcode image** w C# przy użyciu biblioteki Barcode Generator oraz jak **generate DataBar** z precyzyjną kontrolą rozmiaru i współczynnika proporcji. Kompletny przykład demonstruje wszystkie niezbędne ustawienia — od inicjalizacji `BarcodeGenerator` po eksport pliku PNG — dzięki czemu możesz zintegrować tworzenie kodów kreskowych w dowolnej aplikacji .NET bez dodatkowych poszukiwań.

### Co dalej?

* Poznaj inne symbologie kodów kreskowych przy użyciu `EncodeTypes` (np. QR, Code128) – naturalne rozszerzenie przepływu pracy **barcode generator c#**.
* Połącz wygenerowany obraz z raportami PDF lub Excel przy użyciu Aspose.PDF lub Aspose.Cells.
* Dostosuj kolor, dodaj marginesy lub osadź kod kreskowy w interfejsie web API do generowania na żądanie.

Śmiało eksperymentuj z parametrami i niech kod będzie solidną podstawą dla wszystkich przyszłych projektów związanych z kodami kreskowymi. Szczęśliwego kodowania!

## Co powinieneś się nauczyć dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Jak utworzyć stacked DataBar w C# – przewodnik krok po kroku](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}