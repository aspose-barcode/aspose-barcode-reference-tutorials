---
category: general
date: 2026-08-19
description: Twórz pliki PNG z kodem databar w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak generować obrazy databar, konfigurować parametry databar i zapisywać wynik
  w formacie PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: pl
lastmod: 2026-08-19
og_description: Twórz pliki PNG z kodem databar w C# przy użyciu Aspose.BarCode. Ten
  poradnik przeprowadzi Cię krok po kroku przez generowanie obrazów databar, konfigurowanie
  parametrów databar, takich jak wymiar X i współczynnik proporcji, oraz zapisywanie
  wysokiej jakości plików PNG do druku lub użytku w sieci.
og_image_alt: create databar PNG example
og_title: Tworzenie obrazów PNG z paskiem danych w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Jak tworzyć obrazy PNG z kodem databar w C# i Aspose.BarCode
url: /pl/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć obrazy PNG databar przy użyciu C# i Aspose.BarCode

Jeśli potrzebujesz **tworzyć databar PNG** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, uruchamialny przykład, który generuje stosowane omnidirectional DataBar kody, konfiguruje kluczowe parametry i zapisuje dwa pliki PNG o różnych proporcjach.

Generowanie obrazu DataBar nie polega jedynie na wywołaniu jednej metody. Musisz także **skonfigurować parametry databar**, takie jak wymiar X (szerokość modułu) oraz proporcje, aby spełnić specyfikacje druku lub skanowania. Po zakończeniu tego samouczka zrozumiesz **jak generować grafiki databar**, które działają niezawodnie w rzeczywistych scenariuszach.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 lub dowolne IDE zgodne z C#
- Ważna licencja na **Aspose.BarCode for .NET** (bezpłatna wersja ewaluacyjna działa do testów)
- Podstawowa znajomość składni C#

> **Wskazówka:** Jeśli nie masz jeszcze licencji, możesz poprosić o tymczasowy klucz ewaluacyjny w portalu Aspose. API zachowuje się tak samo; zmienia się tylko znak wodny.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz swój projekt w Visual Studio, kliknij prawym przyciskiem myszy rozwiązanie i wybierz **Manage NuGet Packages**. Wyszukaj `Aspose.BarCode` i zainstaluj najnowszą stabilną wersję.

```bash
dotnet add package Aspose.BarCode
```

To polecenie dodaje zestaw `Aspose.BarCode` do Twojego projektu i udostępnia klasę `BarcodeGenerator`.

## Krok 2: Zainicjalizuj generator kodów kreskowych dla stosowanego omnidirectional DataBar

Konstruktor `BarcodeGenerator` przyjmuje dwa argumenty: typ kodu kreskowego oraz surowy ciąg danych. Dla stosowanego omnidirectional DataBar używasz `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Dlaczego to ważne:** Stała `EncodeTypes.DatabarStackedOmniDirectional` informuje bibliotekę, aby wygenerowała kod kreskowy, który może być odczytany z dowolnej orientacji, co jest idealne dla etykiet na półkach sklepowych.

## Krok 3: Skonfiguruj wymiar X (szerokość modułu) w pikselach

Wymiar X kontroluje rozmiar najmniejszego elementu kreski. Ustawienie go w pikselach daje precyzyjną kontrolę nad ostatecznym rozmiarem obrazu.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Wartość **2 piksele** stanowi dobry kompromis między czytelnością a kompaktowością dla większości drukarek etykiet. Dostosuj tę wartość, jeśli potrzebujesz większych lub mniejszych modułów.

## Krok 4: Ustaw pierwszą proporcję i zapisz PNG

Proporcja wpływa na wysokość stosowanego DataBar. Proporcja **15** daje stosunkowo krótki kod kreskowy, podczas gdy **30** sprawia, że jest wyższy.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapisuje wygenerowany kod kreskowy do pliku PNG. PNG jest bezstratny, co zachowuje ostre krawędzie potrzebne skanerom kodów kreskowych.

## Krok 5: Zmień proporcję i zapisz drugi PNG

Możesz ponownie użyć tej samej instancji `BarcodeGenerator`, aby tworzyć warianty, po prostu zmieniając proporcję.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Teraz masz dwa pliki PNG — `DatabarAspectRatio15.png` i `DatabarAspectRatio30.png` — każdy o innej gęstości wizualnej.

## Krok 6: Zweryfikuj wynik

Otwórz wygenerowane pliki PNG w dowolnym przeglądarce obrazów. Powinieneś zobaczyć czysty, wysokokontrastowy kod DataBar. Skanowanie obrazów smartfonowym skanerem kodów kreskowych potwierdza, że obie proporcje dekodują się do pierwotnej wartości GTIN `12345678901231`.

![create databar PNG example](databar_example.png)

*Powyższy obraz pokazuje dwa pliki PNG obok siebie. Lewy obraz używa proporcji 15, prawy używa proporcji 30.*

## Typowe warianty i przypadki brzegowe

| Scenariusz | Co zmienić | Powód |
|------------|------------|-------|
| **Inne dane** | Zastąp ciąg `(01)12345678901231` dowolnym prawidłowym identyfikatorem aplikacji GS1 i danymi | Pozwala kodować identyfikatory produktów, numery seryjne itp. |
| **Wyższa rozdzielczość** | Zwiększ `XDimension.Pixels` do 3 lub 4 | Potrzebne, gdy kod kreskowy będzie drukowany w dużych rozmiarach lub skanowany z daleka. |
| **Inne typy DataBar** | Użyj `EncodeTypes.DatabarStacked` lub `EncodeTypes.DatabarExpanded` | Wybierz typ, który najlepiej pasuje do układu etykiety. |
| **Przezroczyste tło** | Przekaż `BarCodeImageFormat.Png` wraz z `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Przydatne przy nakładaniu kodu kreskowego na kolorowe etykiety. |

> **Uwaga:** Ustawienie wymiaru X, który jest zbyt mały (< 1 piksela), może spowodować, że kod kreskowy będzie wyglądał na rozmyty po

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować i dostosowywać wysokość kodu kreskowego dla jednowymiarowego Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Utwórz jednowymiarowe kodowanie GS1 Databar przy użyciu Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generuj kod Databar Aspose.BarCode przy użyciu .NET API – konfiguracja wierszy i kolumn](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}