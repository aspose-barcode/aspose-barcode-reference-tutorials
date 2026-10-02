---
category: general
date: 2026-08-06
description: Generuj obraz kodu kreskowego w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak generować Databar, dostosować niestandardowy rozmiar kodu kreskowego oraz
  zmienić wysokość kodu kreskowego za pomocą prostego kodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: pl
lastmod: 2026-08-06
og_description: Generuj obraz kodu kreskowego w C# przy użyciu Aspose.BarCode. Ten
  samouczek pokazuje, jak stworzyć kod Databar Omnidirectional, dostosować jego rozmiar
  i efektywnie zmienić wysokość kodu kreskowego.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Generowanie obrazu kodu kreskowego w C# – pełny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Generowanie obrazu kodu kreskowego w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie obrazu kodu kreskowego w C# z Aspose.BarCode

Jeśli potrzebujesz **generować obraz kodu kreskowego** programowo, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Niezależnie od tego, czy tworzysz system inwentaryzacji detalicznej, czy portal śledzenia logistycznego, zobaczysz kompletny przepływ pracy tworzenia kodu Databar Omnidirectional, dostosowywania jego wymiarów i zapisywania wyniku jako plik PNG.

Generowanie obrazu kodu kreskowego jest powszechnym wymaganiem, ale programiści często zastanawiają się **jak wygenerować Databar** o dokładnie potrzebnym rozmiarze. W tym samouczku nauczysz się tworzyć kod Databar, dostosowywać jego szerokość i wysokość oraz zmieniać wysokość kodu kreskowego bez przepisywania całego generatora.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
* Visual Studio 2022 (lub dowolne IDE obsługujące C#)
* Ważna licencja Aspose.BarCode for .NET (darmowa wersja ewaluacyjna działa do testów)
* Podstawowa znajomość składni C#

## Krok 1: Zainstaluj Aspose.BarCode

Dodaj pakiet NuGet Aspose.BarCode do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

Pakiet zawiera klasę `BarcodeGenerator` używaną w całym tym samouczku. Po instalacji przywróć projekt, aby pobrać zależności.

## Krok 2: Utwórz podstawowy generator kodów kreskowych

Pierwsza linia kodu tworzy **generator kodów kreskowych**, który wygeneruje symbol Databar Omnidirectional. Enum `EncodeTypes.DatabarOmniDirectional` informuje bibliotekę, jaką symbologię użyć, a ciąg danych jest zgodny ze składnią identyfikatora aplikacji GS1.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Dlaczego to ważne:** Obiekt `BarcodeGenerator` jest punktem wejścia dla każdej operacji związanej z kodem kreskowym. Wybierając `DatabarOmniDirectional`, zapewniasz, że wynik jest zgodny ze standardem GS1 dla skanowania w handlu detalicznym.

## Krok 3: Ustaw niestandardowy wymiar X (szerokość modułu)

Wymiar X kontroluje szerokość najcieńszego paska. Ustawienie go na małą wartość w pikselach daje kompaktowy kod kreskowy, podczas gdy większe wartości zwiększają ogólną szerokość.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Wyjaśnienie:** Wymiar X o wartości 2 piksele jest powszechnym wyborem dla ekranów o wysokiej rozdzielczości. Dostosuj tę wartość, jeśli potrzebujesz większej lub mniejszej gęstości wizualnej.

## Krok 4: Wygeneruj pierwszy obraz kodu kreskowego o określonej wysokości

Wysokość kodu kreskowego jest niezależna od wymiaru X. Tutaj ustawiamy wysokość paska na **30 px**, a następnie zapisujemy obraz jako PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Wynik:** Masz teraz plik o nazwie `DatabarBarHeight30Pixels.png`, który przedstawia kod Databar o wysokości 30 px. To demonstruje możliwość **niestandardowego rozmiaru kodu kreskowego** dla konkretnego zastosowania, takiego jak mała etykieta.

## Krok 5: Zmień wysokość kodu kreskowego dla większej wersji

Jeśli ten sam kod kreskowy ma pojawić się na większej etykiecie, wystarczy zmodyfikować właściwość wysokości i ponownie użyć tej samej instancji generatora.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego możesz ponownie używać generatora:** Zmiana `BarHeight.Pixels` aktualizuje wewnętrzny układ bez tworzenia nowego obiektu, co oszczędza pamięć i zachowuje niezmieniony ciąg danych. To zalecany sposób **zmiany wysokości kodu kreskowego** w locie.

## Krok 6: Zweryfikuj wynik

Otwórz dwa pliki PNG w dowolnym przeglądarce obrazów. Powinieneś zobaczyć dwa kody Databar Omnidirectional, które kodują ten sam GTIN, ale różnią się rozmiarem w pionie:

* `DatabarBarHeight30Pixels.png` – 30 px wysokości, odpowiedni dla kompaktowych paragonów.
* `DatabarBarHeight60Pixels.png` – 60 px wysokości, idealny dla większych etykiet na krawędzi półki.

Oba obrazy zachowują ten sam wymiar X, więc stosunek pasków do przerw pozostaje spójny, podczas gdy ogólna wysokość skaluje się.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Jak sobie radzić |
|-----------|------------------|
| **Inna symbologia kodu kreskowego** | Zastąp `EncodeTypes.DatabarOmniDirectional` inną wartością wyliczeniową (np. `EncodeTypes.Code128`). Reszta kodu pozostaje niezmieniona. |
| **Wymiary nie‑pikselowe** | Użyj `generator.Parameters.Barcode.XDimension.Millimeters` lub `BarHeight.Millimeters`, jeśli potrzebujesz fizycznych pomiarów do wydruku gotowego. |
| **Przezroczyste tło** | Ustaw `generator.Parameters.ImageBackgroundColor = Color.Transparent;` przed wywołaniem `Save`. |
| **Wyjście wysokiej rozdzielczości** | Zwiększ zarówno `XDimension.Pixels`, jak i `BarHeight.Pixels` proporcjonalnie, lub zapisz jako `BarCodeImageFormat.Tiff` dla jakości bezstratnej. |
| **Wiele kodów kreskowych w jednym obrazie** | Utwórz osobne instancje `BarcodeGenerator`, renderuj każdą do `Bitmap`, a następnie połącz je przy użyciu `Graphics.DrawImage`. |

**Porada:** Zawsze testuj wygenerowany kod kreskowy rzeczywistym skanerem przed wdrożeniem do produkcji. Skanery mogą różnie interpretować bardzo cienkie paski w zależności od oświetlenia i jakości czujnika.

## Pełny kod źródłowy do odniesienia

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Skopiuj kod do nowego projektu konsolowego, uruchom go, a zobaczysz dwa pliki PNG pojawiające się w folderze wyjściowym.

## Najczęściej zadawane pytania

**Q:** Czy mogę generować kod kreskowy bez instalacji licencji?  
**A:** Wersja ewaluacyjna Aspose.BarCode działa bez licencji, ale dodaje mały znak wodny. Do użytku produkcyjnego zastosuj zakupioną licencję używając `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q:** Czy zmiana wymiaru X wpływa na czytelność?  
**A:** Tak. Bardzo małe wymiary X mogą sprawić, że kod kreskowy będzie nieczytelny na drukarkach o niskiej rozdzielczości. Minimalnie 1 px dla renderowania na ekranie jest zalecane; do druku użyj co najmniej 0,25 mm.

**Q:** Co zrobić, jeśli potrzebuję wygenerować kod kreskowy w formacie JPEG?  
**A:** Zastąp `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. Możesz także ustawić `generator.Parameters.ImageQuality`, aby kontrolować kompresję.

## Zakończenie

Teraz wiesz, jak **generować obraz kodu kreskowego** w C# przy użyciu Aspose.BarCode, jak **tworzyć kod Databar**, dostosować **niestandardowy rozmiar kodu kreskowego** oraz **zmienić wysokość kodu kreskowego** na żądanie. Pełny przykład demonstruje najczęstszy przepływ pracy, a tabela wariantów przygotowuje Cię do radzenia sobie z rzeczywistymi przypadkami brzegowymi.

Następnie odkryj powiązane tematy, takie jak **osadzanie kodów kreskowych w dokumentach PDF**, **generowanie wielu kodów kreskowych wsadowo** oraz **używanie kodów QR do płatności mobilnych**. Każdy z tych scenariuszy opiera się na tych samych zasadach przedstawionych tutaj, więc możesz pewnie rozwijać tę wiedzę.

Szczęśliwego kodowania i niech Twoje kody kreskowe skanują się bezbłędnie!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i zbadać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj obraz kodu kreskowego – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak wygenerować kod kreskowy – konfiguracja Code 39 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}