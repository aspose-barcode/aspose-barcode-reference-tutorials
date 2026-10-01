---
category: general
date: 2026-08-22
description: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu generatora DataBar
  Stacked Omni‑Directional. Dowiedz się, jak ustawić wymiar X i współczynnik proporcji
  dla wyjścia PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: pl
lastmod: 2026-08-22
og_description: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu generatora DataBar
  Stacked Omni‑Directional. Postępuj zgodnie z instrukcją krok po kroku, aby dostosować
  wymiar X i proporcje.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Jak zmienić rozmiar kodu kreskowego w C# – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu DataBar Stacked
url: /pl/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić rozmiar kodu kreskowego w C# przy użyciu DataBar Stacked Omni‑Directional

Jeśli potrzebujesz **jak zmienić rozmiar kodu kreskowego** w aplikacji .NET, ten przewodnik pokazuje dokładne kroki przy użyciu generatora kodów kreskowych DataBar Stacked Omni‑Directional. Zobaczysz, jak kontrolować wymiar X w pikselach, dostosować proporcje kodu kreskowego i zapisać wynik jako plik PNG.

Zmiana rozmiaru kodu kreskowego jest często wymagana, gdy przestrzeń na drukowanej etykiecie jest ograniczona lub gdy potrzebny jest obraz o wyższej rozdzielczości dla kanałów cyfrowych. Ten tutorial obejmuje wszystko, czego potrzebujesz – od inicjalizacji generatora po wygenerowanie dwóch obrazów o różnych rozmiarach.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Odwołanie do pakietu NuGet **Aspose.BarCode for .NET**  
* Podstawowa znajomość składni C#  

Nie są wymagane dodatkowe konfiguracje; kod działa na Windows, Linux i macOS.

## Jak zmienić rozmiar kodu kreskowego w C# – krok po kroku

Poniższe sekcje dzielą proces na odrębne, wielokrotnego użytku kroki. Każdy krok wyjaśnia **dlaczego** kod jest potrzebny, a nie tylko **co** robi.

### Krok 1: Utwórz generator kodu kreskowego DataBar Stacked Omni‑Directional

Obiekt generatora przechowuje wszystkie ustawienia kodu kreskowego. Przekazując `EncodeTypes.DatabarStackedOmniDirectional` oraz przykładowe dane, tworzysz prawidłowy kod gotowy do dalszej personalizacji.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Why this matters* – Klasa **C# barcode generator** enkapsuluje algorytm kodowania. Rozpoczęcie od prawidłowego generatora zapewnia, że późniejsze zmiany rozmiaru będą dotyczyć właściwego typu kodu kreskowego.

### Krok 2: Ustaw podstawowy rozmiar modułu (wymiar X) w pikselach

Wymiar X definiuje szerokość pojedynczego modułu kodu kreskowego. Dostosowanie go zmienia ogólną szerokość i wysokość proporcjonalnie.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Why this matters* – Większy wymiar X powoduje większy kod kreskowy, co jest przydatne przy drukarkach o niskiej rozdzielczości. Odwrotnie, mniejsza wartość tworzy kompaktowy kod odpowiedni dla małych etykiet.

### Krok 3: Zmień proporcję kodu kreskowego na 15 i zapisz obraz

**Proporcja kodu kreskowego** kontroluje stosunek wysokości do szerokości. Proporcja 15 daje stosunkowo wysoki kod.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Why this matters* – Różne urządzenia skanujące mają optymalne wymagania co do proporcji. Ustawienie proporcji na 15 demonstruje, jak **jak zmienić rozmiar kodu kreskowego** poprzez modyfikację wysokości przy zachowaniu szerokości określonej przez wymiar X.

#### Oczekiwany wynik

Plik `DatabarAspectRatio15.png` przedstawia kod DataBar Stacked Omni‑Directional, który jest wyższy niż domyślny. Szerokość kodu odzwierciedla 2‑pikselowy wymiar X, a wysokość wynika z proporcji 15.

### Krok 4: Zmień proporcję kodu kreskowego na 30 i zapisz nowy obraz

Zwiększenie proporcji do 30 sprawia, że kod staje się jeszcze wyższy, co ilustruje elastyczność regulacji rozmiaru.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Why this matters* – Zmieniając wartość **proporcji kodu kreskowego**, natychmiast widzisz, jak **jak zmienić rozmiar kodu kreskowego** bez konieczności ponownego tworzenia generatora. Oszczędza to czas przetwarzania w scenariuszach wsadowych.

#### Oczekiwany wynik

Plik `DatabarAspectRatio30.png` jest wyraźnie wyższy niż poprzedni obraz, potwierdzając, że proporcja bezpośrednio wpływa na wysokość kodu.

### Krok 5: Zweryfikuj wygenerowane obrazy

Otwórz pliki PNG w dowolnej przeglądarce obrazów. Powinny się na nich znajdować dwa kody o identycznej szerokości (kontrolowanej przez wymiar X), ale różnej wysokości (kontrolowanej przez proporcję). Jeśli obrazy są rozmyte, zwiększ liczbę pikseli wymiaru X; jeśli są zbyt wysokie, obniż proporcję.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Why this matters* – Programowa weryfikacja zapewnia, że zmiany rozmiaru zostały zastosowane prawidłowo, co jest kluczowe w zautomatyzowanych pipeline’ach budowania.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie | Powód |
|-----------|--------------|-------|
| **Bardzo małe etykiety** | Ustaw `XDimension.Pixels = 1` i `AspectRatio = 10` | Zmniejsza ogólny rozmiar przy zachowaniu czytelności |
| **Druk wysokiej rozdzielczości** | Ustaw `XDimension.Pixels = 4` i `AspectRatio = 20` | Zwiększa gęstość pikseli dla wyraźnego wyniku |
| **Inny format obrazu** | Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` | Przydatne, gdy wsparcie dla PNG jest ograniczone |
| **Dynamiczne dane** | Przekaż zmienną łańcuchową do konstruktora `BarcodeGenerator` | Generuje kody kreskowe dla każdego produktu automatycznie |

Gdy potrzebujesz wygenerować wiele kodów kreskowych o różnych rozmiarach, opakuj kroki w metodę:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Wywołanie `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` tworzy kod kreskowy o niestandardowym rozmiarze w jednej linii kodu.

## Profesjonalne wskazówki dotyczące niezawodnych zmian rozmiaru

* **Always set X‑dimension before the aspect ratio.** Changing the aspect ratio first can lead to unexpected scaling if the X‑dimension defaults to a non‑ideal value.  
* **Use a consistent output folder.** Hard‑coding `"YOUR_DIRECTORY"` works for demos, but in production prefer `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Validate the generated image size.** Small changes in X‑dimension may not be noticeable on screen; checking pixel dimensions guarantees the change took effect.  

## Podsumowanie

Teraz wiesz **jak zmienić rozmiar kodu kreskowego** w C# przy użyciu generatora DataBar Stacked Omni‑Directional. Poprzez regulację **pikseli wymiaru X** oraz **proporcji kodu kreskowego**, możesz tworzyć obrazy PNG pasujące do dowolnego rozmiaru etykiety lub wymagań rozdzielczości. Pełny, działający przykład powyżej demonstruje cały przepływ od utworzenia generatora po weryfikację rozmiaru.

### Co warto zbadać dalej

* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor` and `BackColor` to match brand guidelines.  
* **Different barcode types** – replace `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128` to see how size parameters differ across symbologies.  
* **Batch processing** – combine the `GenerateDatabar` method with a CSV import to create thousands of barcodes automatically.

Dostosuj fragmenty kodu do architektury swojego projektu i pozwól, aby regulacja rozmiaru kodu kreskowego poprawiła niezawodność skanowania oraz wygląd wizualny. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak dostosować rozmiar kodu kreskowego – proporcje Codablock F z Aspose.BarCode dla .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak wygenerować kod Aztec z niestandardową proporcją przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generować i dostosować wysokość kodu kreskowego One-Dimensional Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}