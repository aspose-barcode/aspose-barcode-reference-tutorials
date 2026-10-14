---
category: general
date: 2026-09-29
description: Dowiedz się, jak tworzyć wielokierunkowy kod kreskowy Databar w C# przy
  użyciu Aspose.BarCode. Dostosuj wymiar X, ustaw współczynnik proporcji i zapisz
  obrazy PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: pl
lastmod: 2026-09-29
og_description: Utwórz wszechkierunkowy kod kreskowy Databar w C# przy użyciu Aspose.BarCode.
  Dowiedz się, jak ustawić wymiar X, dostosować proporcje i eksportować pliki PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Tworzenie wielokierunkowego kodu kreskowego Databar w C# – przewodnik krok
  po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak stworzyć wszechkierunkowy kod kreskowy Databar w C#
url: /pl/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć wszechkierunkowy kod kreskowy Databar w C#

Jeśli potrzebujesz **utworzyć wszechkierunkowy kod kreskowy Databar** w aplikacji .NET, ten przewodnik pokaże Ci dokładne kroki. Zobaczysz, jak zainicjować kod kreskowy DataBar stacked omnidirectional, skonfigurować jego wymiar X, zmienić współczynnik proporcji oraz wygenerować obrazy PNG przy użyciu Aspose.BarCode.

Generowanie **DataBar stacked omnidirectional barcode** jest powszechne, gdy musisz zakodować identyfikatory produktów dla skanerów detalicznych. W tym tutorialu nauczysz się **ustawiać współczynnik proporcji kodu kreskowego**, kontrolować rozmiar modułu i eksportować wynik bez opuszczania IDE.

## Prerequisites

Zanim rozpoczniesz, upewnij się, że masz:

- .NET 6.0 lub nowszy zainstalowany
- Visual Studio 2022 (lub dowolne IDE kompatybilne z C#)
- Pakiet **Aspose.BarCode for .NET** dostępny w NuGet (wersja 23.12 lub nowsza)

Pakiet możesz dodać za pomocą Menedżera Pakietów NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Inicjalizacja wszechkierunkowego kodu Databar

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator`, która celuje w symbologię **DataBar stacked omnidirectional**. Konstruktor przyjmuje typ kodowania oraz ciąg danych.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Dlaczego to ważne:** Wartość `EncodeTypes.DatabarStackedOmniDirectional` informuje Aspose.BarCode, aby renderował konkretny format wszechkierunkowego Databar, co jest wymagane do skanowania w obu kierunkach.

## Krok 2: Definiowanie wymiaru X (rozmiar modułu)

Wymiar X kontroluje szerokość pojedynczego modułu kodu kreskowego w pikselach. Wartość `2` piksele dobrze sprawdza się przy renderowaniu na ekranie i w większości drukarek.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to ważne:** Spójny wymiar X zapewnia, że kod kreskowy spełnia minimalne specyfikacje rozmiaru dla skanerów detalicznych, jednocześnie utrzymując rozmiar pliku obrazu w rozsądnych granicach.

## Krok 3: Ustaw pierwszy współczynnik proporcji i zapisz obraz

**Współczynnik proporcji** określa stosunek wysokości do szerokości DataBar. Współczynnik `15` daje zwartą, wysoką wersję kodu idealną dla wąskich etykiet.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Dlaczego to ważne:** Dostosowanie współczynnika proporcji pozwala dopasować kod kreskowy do różnych układów etykiet bez utraty czytelności. Zapisany plik PNG można otworzyć w dowolnym przeglądarce obrazów.

## Krok 4: Zmień współczynnik proporcji i wygeneruj drugi obraz

Czasami potrzebny jest szerszy kod — na przykład, gdy etykieta ma więcej miejsca w poziomie. Zmiana współczynnika na `30` tworzy bardziej płaski wygląd.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to ważne:** Udostępniając właściwość **set barcode aspect ratio**, możesz tworzyć wiele wariantów kodu z jednej bazy kodu, upraszczając automatyczne pipeline’y generowania etykiet.

## Oczekiwany wynik

Uruchomienie programu tworzy dwa pliki PNG w folderze wyjściowym aplikacji:

| Nazwa pliku                | Współczynnik proporcji | Opis wizualny |
|----------------------------|------------------------|---------------|
| `DatabarAspectRatio15.png` | 15                     | Wysoki, wąski kod kreskowy odpowiedni dla wąskich etykiet |
| `DatabarAspectRatio30.png` | 30                     | Szerszy kod, który wypełnia więcej przestrzeni poziomej |

Możesz osadzać te obrazy w raportach, drukować je na opakowaniach produktów lub wysyłać do usługi webowej w celu dalszego przetwarzania.

![Create omnidirectional Databar barcode example](databar-example.png "Create omnidirectional Databar barcode example")

*Zrzut ekranu pokazuje dwa wygenerowane pliki PNG obok siebie.*

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli potrzebuję innego wymiaru X?

Możesz przypisać dowolną wartość całkowitą do `XDimension.Pixels`. Wartości poniżej `1` są ignorowane, a powyżej `10` mogą powodować zbyt duże moduły, które wykraczają poza marginesy drukarki. Po każdej zmianie przetestuj wygląd obrazu.

### Jak zakodować inne dane generowane przez AI (np. UPC, EAN)?

Zastąp ciąg danych w konstruktorze `BarcodeGenerator` odpowiednim identyfikatorem aplikacji (AI). Dla kodu UPC‑A użyj `"012345678905"` bez prefiksu AI.

### Czy mogę eksportować do formatów innych niż PNG?

Tak. Metoda `Save` akceptuje `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` oraz `BarCodeImageFormat.Bmp`. Wybierz format pasujący do Twojego dalszego przepływu pracy.

## Pro tip: ponowne użycie generatora do przetwarzania wsadowego

Jeśli musisz wygenerować dziesiątki kodów kreskowych o różnych współczynnikach proporcji, utrzymuj instancję `BarcodeGenerator` przy życiu i modyfikuj jedynie `DataBar.AspectRatio` przed każdym wywołaniem `Save`. Dzięki temu unikniesz kosztów ponownego tworzenia generatora dla każdego obrazu.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Zakończenie

Teraz wiesz, jak **utworzyć wszechkierunkowy kod kreskowy Databar** w C# przy użyciu Aspose.BarCode. Inicjalizując `BarcodeGenerator`, ustawiając wymiar X, regulując **set barcode aspect ratio** i zapisując pliki PNG, możesz tworzyć obrazy kodów kreskowych spełniające różnorodne wymagania etykiet.  

Następnie odkryj powiązane tematy, takie jak **generate barcode image** dla kodów QR, walidacja **DataBar stacked omnidirectional barcode** lub integracja wygenerowanych PNG w fakturach PDF przy użyciu Aspose.PDF. Eksperymentuj z różnymi współczynnikami proporcji i rozmiarami modułów, aby znaleźć optymalną konfigurację dla swojego sprzętu drukującego.

---


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletny, działający kod wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to generate barcode in C# – create barcode image c# with DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}