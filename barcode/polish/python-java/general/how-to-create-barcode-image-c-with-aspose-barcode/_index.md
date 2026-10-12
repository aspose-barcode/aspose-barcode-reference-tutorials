---
category: general
date: 2026-10-12
description: Utwórz obraz kodu kreskowego w C# przy użyciu Aspose.BarCode w kilka
  minut. Ten krok po kroku przykład generatora kodów kreskowych w C# pokazuje, jak
  ustawić proporcje i zapisać pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: pl
lastmod: 2026-10-12
og_description: Twórz obrazy kodów kreskowych w C# natychmiast. Skorzystaj z tego
  przykładu generatora kodów kreskowych w C#, aby tworzyć wysokiej jakości obrazy
  PNG z kodami kreskowymi o niestandardowych proporcjach.
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: Tworzenie obrazu kodu kreskowego w C# – szybki przewodnik z Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Jak utworzyć obraz kodu kreskowego w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego c# przy użyciu Aspose.BarCode

Jeśli potrzebujesz szybko **utworzyć obraz kodu kreskowego c#**, ten przewodnik poprowadzi Cię przez kompletny, działający przykład. Niezależnie od tego, czy tworzysz system etykiet wysyłkowych, czy skaner inwentarza, poniższe kroki dokładnie pokazują, jak skonfigurować kod DataBar Stacked Omnidirectional, dostosować jego parametry wizualne i zapisać wynik jako plik PNG.

Zobaczysz także **przykład generatora kodów kreskowych c#**, który demonstruje zmianę współczynnika proporcji w locie, dzięki czemu możesz tworzyć wiele wariantów bez przepisywania kodu. Nie jest wymagana żadna zewnętrzna dokumentacja — po prostu skopiuj, wklej i uruchom.

## Czego będziesz potrzebować

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
* Pakiet **Aspose.BarCode for .NET** dostępny w NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Folder, w którym będą zapisywane wygenerowane pliki PNG (zastąp `YOUR_DIRECTORY` w kodzie)

Te wymagania zapewniają, że **przykład generatora kodów kreskowych c#** działa na dowolnym nowoczesnym komputerze z systemem Windows, Linux lub macOS.

## Jak utworzyć obraz kodu kreskowego c# przy użyciu Aspose.BarCode

Proces składa się z czterech krótkich kroków: utworzenie generatora, ustawienie rozmiaru modułu, skonfigurowanie współczynnika proporcji i w końcu zapisanie obrazu. Każdy krok jest wyjaśniony, abyś rozumiał *dlaczego* jest istotny, a nie tylko *co* wpisać.

### Krok 1 – Inicjalizacja generatora kodu kreskowego

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**Dlaczego to jest ważne:** Konstruktor `BarcodeGenerator` przyjmuje dwa argumenty: symbolikę kodu kreskowego (`EncodeTypes.DatabarStackedOmniDirectional`) oraz surowy ciąg danych. Prefiks `(01)` informuje skaner, że kolejne 14 cyfr reprezentuje identyfikator GTIN‑14, co jest powszechnym wymogiem w handlu detalicznym i logistyce.

### Krok 2 – Ustaw rozmiar modułu (wymiar X)

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to jest ważne:** Wymiar X kontroluje szerokość najmniejszego słupka (tzw. „modułu”). Wartość `2` piksele daje wyraźny, wysokiej rozdzielczości kod kreskowy, który pozostaje czytelny po skalowaniu. Jeśli potrzebujesz większego kodu na plakat, zwiększ tę wartość proporcjonalnie.

### Krok 3 – Zapisz pierwszy obraz z współczynnikiem proporcji 15

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Dlaczego to jest ważne:** Symbole DataBar obsługują *współczynnik proporcji*, który wpływa na stosunek wysokości do szerokości. Współczynnik proporcji `15` jest domyślny w wielu aplikacjach detalicznych i tworzy zwartą, nieco kwadratową etykietę, która łatwo mieści się na małych etykietach.

### Krok 4 – Zmień współczynnik proporcji na 30 i zapisz drugi obraz

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**Dlaczego to jest ważne:** Zwiększenie współczynnika proporcji do `30` rozciąga kod kreskowy w pionie, poprawiając czytelność na skanerach o niskiej rozdzielczości lub na etykietach, które są wyższe niż szerokie. Ponieważ ta sama instancja `BarcodeGenerator` jest ponownie używana, unikasz alokacji nowego obiektu dla każdej wariacji — efektywny wzorzec przy przetwarzaniu wsadowym.

## Pełny, działający przykład

Poniżej znajduje się kompletny program, który możesz skopiować do aplikacji konsolowej. Zawiera niezbędne dyrektywy `using`, obsługę błędów oraz komentarze wyjaśniające każdą linię.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu tworzy dwa pliki PNG:

| Nazwa pliku | Współczynnik proporcji | Typowe zastosowanie |
|-----------|--------------|-------------|
| `DatabarAspectRatio15.png` | 15 | Standardowa etykieta detaliczna |
| `DatabarAspectRatio30.png` | 30 | Wysoka etykieta lub skaner o niskiej rozdzielczości |

Oba obrazy zawierają wyraźny kod DataBar Stacked Omnidirectional, który koduje wartość GTIN‑14 `12345678901231`. Możesz otworzyć pliki PNG w dowolnej przeglądarce obrazów, aby zweryfikować jakość wizualną.

![Przykładowy obraz kodu kreskowego utworzony w C# przy użyciu Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="Przykładowy obraz kodu kreskowego utworzony w C# przy użyciu Aspose.BarCode"}

*Tekst alternatywny powyżej zawiera główne słowo kluczowe, pomagając zarówno wyszukiwarkom, jak i czytnikom ekranu.*

## Dodatkowe uwagi i wskazówki najlepszych praktyk

* **Obsługiwane formaty** – `BarCodeImageFormat` obsługuje PNG, JPEG, BMP, GIF i TIFF. PNG jest bezstratny, co czyni go najbezpieczniejszym wyborem do dalszego skanowania.
* **Dostosowanie kolorów** – Możesz zmienić kolory pierwszego planu/tła za pomocą `generator.Parameters.Barcode.ForegroundColor` i `BackgroundColor`. Jest to przydatne przy drukowaniu na kolorowych nośnikach.
* **Generowanie wsadowe** – Dla dużych inwentarzy, otocz logikę zapisu w pętli `foreach`, która odczytuje dane produktów z pliku CSV. Ponowne użycie tej samej instancji `BarcodeGenerator` zmniejsza obciążenie pamięci.
* **Obsługa błędów** – Blok `try/catch` w pełnym przykładzie przechwytuje problemy, takie jak nieprawidłowe ciągi danych lub błędy uprawnień zapisu, które są częste, gdy docelowy katalog nie istnieje.
* **Wydajność** – Ustawienie `XDimension.Pixels` przed pierwszym wywołaniem `Save` zapewnia, że renderujący oblicza rozmiar bitmapy tylko raz przy każdej zmianie współczynnika proporcji.

## Podsumowanie

Teraz wiesz, jak **utworzyć obraz kodu kreskowego c#** przy użyciu Aspose.BarCode, dostosować wymiar X, zmienić współczynniki proporcji i zapisać pliki PNG w jednym, wielokrotnie używanym bloku kodu. Ten **przykład generatora kodów kreskowych c#** obejmuje najczęstsze wariacje, z którymi spotkasz się przy generowaniu symboli DataBar Stacked Omnidirectional dla zastosowań detalicznych lub logistycznych.

## Co dalej?

* Zbadaj inne symbologie, takie jak `EncodeTypes.Code128` lub `EncodeTypes.QR`, aby poszerzyć swoje rozwiązanie.
* Eksperymentuj z `generator.Parameters.Barcode.ImageMargin`, aby dodać marginesy wokół kodu kreskowego.
* Zintegruj wygenerowane pliki PNG z fakturami PDF przy użyciu Aspose.PDF lub osadź je bezpośrednio w raportach HTML.

Śmiało dostosuj kod do swojego konkretnego przepływu pracy — niezależnie od tego, czy potrzebujesz jednego obrazu na produkt, czy masowej eksportu tysięcy kodów kreskowych, przedstawiony tutaj wzorzec skaluje się efektywnie.

---

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć obraz kodu kreskowego z Aspose.Barcode w C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Jak utworzyć obraz kodu pocztowego w C# przy użyciu Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}