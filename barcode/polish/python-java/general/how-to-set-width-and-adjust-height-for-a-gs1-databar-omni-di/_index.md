---
category: general
date: 2026-09-29
description: Jak ustawić szerokość kodu kreskowego GS1 DataBar Omni‑Directional i
  jak zmienić wysokość przy użyciu C#. Postępuj zgodnie z przewodnikiem krok po kroku
  z pełnym kodem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: pl
lastmod: 2026-09-29
og_description: Jak ustawić szerokość kodu kreskowego GS1 DataBar Omni‑Directional
  i jak zmienić wysokość w C#. Dowiedz się, jakie dokładnie wywołania API są potrzebne
  i zobacz kompletny, działający przykład.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Jak ustawić szerokość kodu kreskowego GS1 DataBar – przewodnik C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Jak ustawić szerokość i dostosować wysokość kodu kreskowego GS1 DataBar Omni‑Directional
  w C#
url: /pl/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić szerokość i dostosować wysokość dla kodu kreskowego GS1 DataBar Omni‑Directional w C#

Ustawienie szerokości kodu kreskowego GS1 DataBar Omni‑Directional jest częstym zadaniem, gdy potrzebujesz dokładnych wymiarów dla urządzeń skanujących. W tym samouczku dowiesz się również **jak zmienić wysokość**, aby kod kreskowy idealnie pasował do Twojego układu. Poradnik przeprowadzi Cię przez cały proces, od konfiguracji projektu po w pełni działający przykład kodu.

Omówimy:

* Wymaganą paczkę NuGet oraz wersję .NET.
* Dlaczego wymiar X (szerokość modułu) ma znaczenie dla czytelności kodu kreskowego.
* Dokładne wywołania API do **jak ustawić szerokość** i **jak zmienić wysokość**.
* Obsługę przypadków brzegowych, takich jak minimalna szerokość modułu i renderowanie w wysokiej rozdzielczości.
* Pełny, gotowy do skopiowania przykład, który generuje dwa pliki PNG o różnych wysokościach pasków.

## Wymagania wstępne

| Requirement | Reason |
|------------|--------|
| .NET 6.0 SDK or later | Przykład używa nowoczesnych funkcji C# i działa na Windows, Linux lub macOS. |
| Visual Studio 2022 (or any C# IDE) | Zapewnia IntelliSense dla API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Zawiera `BarcodeGenerator`, `EncodeTypes` oraz obsługę formatów obrazu. Zainstaluj przy pomocy `dotnet add package Aspose.Barcode`. |
| Write permission to a folder where PNG files will be saved | Generator zapisuje wygenerowane obrazy na dysku. |

## Jak ustawić szerokość kodu kreskowego

Krok **jak ustawić szerokość** realizowany jest poprzez konfigurację właściwości `XDimension` parametrów kodu kreskowego. `XDimension` reprezentuje szerokość modułu (najmniejszego paska lub spacji) w pikselach, punktach lub milimetrach. Poprawne ustawienie zapewnia spełnienie wymagań skanera.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Dlaczego wymiar X ma znaczenie

* **Tolerancja skanera** – Większość skanerów wymaga minimalnej szerokości modułu; zbyt mała wartość może powodować błędy odczytu.
* **Rozdzielczość druku** – Przy druku 300 dpi, moduł 2 px przekłada się na ~0,17 mm, co mieści się w zalecanym zakresie dla GS1 DataBar.
* **Rozmiar obrazu** – Większe wartości XDimension zwiększają całkowitą szerokość kodu kreskowego, co może wpływać na ograniczenia układu.

### Wskazówki dotyczące niezawodnych ustawień szerokości

* **Nigdy nie ustawiaj XDimension poniżej 1 px** – biblioteka przytnie wartość, ale wynikowy kod może być nieczytelny.
* **Dopasuj do docelowego DPI** – jeśli renderujesz do formatu wysokiej rozdzielczości (np. TIFF przy 600 dpi), zwiększ XDimension proporcjonalnie.
* **Testuj na prawdziwym skanerze** – po zmianie szerokości zweryfikuj kod kreskowy na urządzeniu, które będzie go odczytywać.

## Jak zmienić wysokość kodu kreskowego

Gdy szerokość jest już określona, możesz kontrolować rozmiar pionowy za pomocą właściwości `BarHeight`. Poniższy kod demonstruje **jak zmienić wysokość** z 30 px na 60 px i zapisać dwa oddzielne obrazy.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Zrozumienie wysokości pasków

* **Równowaga wizualna** – Wyższe paski poprawiają czytelność na tle o niskim kontraście, ale zwiększają pionowy rozmiar obrazu.
* **Limity regulacyjne** – Niektóre standardy (np. etykietowanie detaliczne) określają maksymalną wysokość paska; dostosuj się do nich.
* **Proporcje** – Zmiana wysokości nie wpływa na szerokość modułu; możesz precyzyjnie dostroić oba parametry niezależnie.

### Obsługa przypadków brzegowych przy zmianie wysokości

| Situation | Recommended approach |
|-----------|----------------------|
| Height < 10 px | Zwiększ do co najmniej 10 px; bardzo krótkie paski mogą być ignorowane przez skanery. |
| Very tall bars (≥ 100 px) | Sprawdź, czy nośnik wyjściowy (papier, etykieta) pomieści dodatkową przestrzeń. |
| Need proportional scaling | Oblicz `BarHeight = XDimension * desiredRatio`, aby zachować spójność wizualną. |

## Pełny, działający przykład

Poniżej znajduje się kompletny program, który łączy kroki **jak ustawić szerokość** i **jak zmienić wysokość**. Skopiuj kod do nowego projektu konsolowego, przywróć pakiet NuGet Aspose.Barcode i uruchom go. Dwa pliki PNG pojawią się w folderze `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu generuje dwa pliki PNG:

* `DatabarBarHeight30Pixels.png` – kod kreskowy o wysokości 30 px, moduły o szerokości 2 px.
* `DatabarBarHeight60Pixels.png` – ten sam kod kreskowy z podwojoną wysokością pionową.

Otwórz dowolny z obrazów w dowolnym przeglądarce; zobaczysz czysty symbol GS1 DataBar Omni‑Directional gotowy do skanowania.

## Często zadawane pytania

| Question | Answer |
|----------|--------|
| *Can I use millimetres instead of pixels?* | Tak. Ustaw `generator.Parameters.Barcode.XDimension.Millimeters` oraz `BarHeight.Millimeters`. Biblioteka konwertuje na piksele urządzenia na podstawie DPI obrazu. |
| *What if I need a different barcode type?* | Zamień `EncodeTypes.DatabarOmniDirectional` na dowolną inną wartość `EncodeTypes` (np. `EncodeTypes.QR`). Właściwości szerokości i wysokości działają tak samo. |
| *Is there a way to generate SVG instead of PNG?* | Użyj `BarCodeImageFormat.Svg` w wywołaniu `Save`. Ustawienia szerokości/wysokości pozostają obowiązujące. |
| *Do I need to call `generator.Dispose()`?* | `BarcodeGenerator` implementuje `IDisposable`. W aplikacji konsolowej możesz go objąć blokiem `using`, ale w krótkich przykładach jest to opcjonalne. |

## Zakończenie

Teraz wiesz **jak ustawić szerokość** kodu kreskowego GS1 DataBar Omni‑Directional oraz **jak zmienić wysokość** przy użyciu API Aspose.Barcode w C#. Pełny przykład pokazuje, jak utworzyć generator, skonfigurować `XDimension` i `BarHeight` oraz zapisać pliki PNG o różnych rozmiarach pionowych.  

Od tego momentu możesz:

* Eksperymentować z innymi `EncodeTypes` (np. QR, Code128).
* Renderować do formatów wysokiej rozdzielczości, takich jak TIFF, przeznaczonych do druku.
* Zintegrować generator z API webowym, które zwraca kody kreskowe w locie.

Miłego kodowania i niech Twoje kody kreskowe zawsze skanują się bez problemów!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak zmienić wysokość kodu kreskowego w C# – Kompletny przewodnik](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Przykład generatora kodów kreskowych w C# – ustaw szerokość i wysokość](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}