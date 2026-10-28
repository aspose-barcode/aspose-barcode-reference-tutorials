---
category: general
date: 2026-10-28
description: Szybko utwórz obraz kodu kreskowego w C#. Dowiedz się, jak używać generatora
  kodów kreskowych w C#, jak ustawić rozmiar piksela oraz jak zmienić współczynnik
  proporcji dla DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: pl
lastmod: 2026-10-28
og_description: Utwórz obraz kodu kreskowego w C# za pomocą generatora kodów kreskowych.
  Skorzystaj z tego przewodnika, aby ustawić rozmiar piksela, zmienić proporcje i
  generować kody DataBar.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Tworzenie obrazu kodu kreskowego w C# – przewodnik krok po kroku
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Jak utworzyć obraz kodu kreskowego w C# przy użyciu generatora kodów kreskowych
url: /pl/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego w C# przy użyciu Barcode Generator

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, gotowy do uruchomienia przykład, który używa biblioteki Barcode Generator C# do generowania kodu DataBar stacked omnidirectional, ustawiania rozmiaru piksela i zmiany współczynnika proporcji.

Programowe generowanie kodów kreskowych eliminuje potrzebę korzystania z zewnętrznych narzędzi i pozwala osadzić obraz bezpośrednio w plikach PDF, raportach lub kontrolkach UI. W poniższych krokach omówimy także **jak ustawić rozmiar piksela** oraz **jak zmienić współczynnik proporcji**, dwa typowe wymagania, gdy potrzebny jest wyraźny, prawidłowo skalowany kod kreskowy.

## Prerequisites

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* IDE kompatybilne z C# (Visual Studio, Rider lub VS Code)  
* Pakiet NuGet `BarcodeGenerator` (np. `GroupDocs.Barcode` lub `Aspose.Barcode`) zainstalowany w projekcie  

Możesz dodać pakiet przy użyciu następującego polecenia:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tip:** Zweryfikuj, czy wersja pakietu odpowiada Twojemu docelowemu frameworkowi, aby uniknąć niezgodności w czasie wykonywania.

## Create barcode image with Barcode Generator C#

Pierwszym krokiem jest utworzenie generatora z żądanym typem kodu kreskowego i danymi. Poniższy przykład tworzy kod **DataBar stacked omnidirectional**, który jest idealny w scenariuszach skanowania w handlu detalicznym.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Why each line matters

* **Instantiate `BarcodeGenerator`** – Konstruktor przyjmuje symbologię kodu kreskowego (`EncodeTypes.DatabarStackedOmniDirectional`) oraz surowy ciąg danych. Wybranie właściwej symbologii zapewnia, że skaner będzie w stanie odczytać kod.  
* **Set `XDimension.Pixels`** – Ta właściwość kontroluje szerokość najmniejszego elementu kreski. Wartość `2` generuje szczegółowy obraz, który pozostaje czytelny na większości ekranów. Zwiększ ją, jeśli potrzebujesz większego kodu dla drukarek o niskiej rozdzielczości.  
* **Configure `AspectRatio`** – Rodzina DataBar obsługuje kilka współczynników proporcji wpływających na stosunek wysokości do szerokości. Wartości `15` i `30` są powszechne; `15` daje krótszy kod, natomiast `30` – wyższy.  
* **`Save` method** – Zapisuje wygenerowany kod do pliku PNG. Możesz zamienić `BarCodeImageFormat.Png` na `Jpeg` lub `Bmp`, jeśli Twój system wymaga innego formatu.

## How to set pixel size for different rendering contexts

Rozmiar piksela określa wizualną gęstość kodu kreskowego. Jeśli kod ma być wyświetlany na monitorze o wysokiej rozdzielczości DPI, możesz zwiększyć rozmiar piksela do `3` lub `4`. Natomiast dla drukarek termicznych o niskiej rozdzielczości, mniejszy rozmiar piksela (np. `1`) zmniejsza zużycie tuszu.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Edge case:** Ustawienie rozmiaru piksela zbyt niskiego (< 1) powoduje `ArgumentOutOfRangeException`. Zawsze waliduj wartość przed jej przypisaniem.

## How to change aspect ratio without recreating the generator

Zmiana współczynnika proporcji to prosta aktualizacja właściwości; **nie** musisz ponownie tworzyć instancję `BarcodeGenerator`. Oszczędza to pamięć i zwiększa wydajność, gdy potrzebujesz wielu obrazów o różnych kształtach.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Jeśli potrzebujesz więcej niż dwóch proporcji, możesz przeiterować tablicę:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Expected output

Uruchomienie programu tworzy dwa pliki PNG (lub więcej, jeśli użyjesz pętli). Otwórz je w dowolnej przeglądarce obrazów; powinieneś zobaczyć czysty kod DataBar:

* **DatabarAspectRatio15.png** – krótki, szeroki kod odpowiedni dla wąskich przestrzeni etykiet.  
* **DatabarAspectRatio30.png** – wyższy kod, który zwiększa niezawodność skanowania przy skanerach pod kątem.

Oba obrazy mają ten sam rozmiar piksela (2 px na moduł), różnią się jedynie wysokością, co demonstruje **jak zmienić współczynnik proporcji** przy zachowaniu pozostałych parametrów.

## Common pitfalls and how to avoid them

| Symptom | Cause | Fix |
|---------|-------|-----|
| Barcode appears blurry | `XDimension.Pixels` set too low for the output resolution | Increase pixel size to at least `2` for screen display, `3` for print |
| Scanner cannot read the code | Wrong `EncodeTypes` for the data format | Verify that the GTIN‑14 data matches the chosen symbology |
| `ArgumentOutOfRangeException` on aspect ratio | Ratio value not supported by the library (valid range: 15‑30) | Use only values documented by the library, or catch the exception and fallback to a default |
| File not found after `Save` | Relative path points to a non‑existent directory | Use an absolute path or ensure `Directory.CreateDirectory` is called first |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Next steps – extending the barcode workflow

Teraz, gdy potrafisz **utworzyć obraz kodu kreskowego**, możesz chcieć:

* **Osadzić PNG w PDF** przy użyciu biblioteki takiej jak `PdfSharp` lub `iTextSharp`.  
* **Generować inne symbologie** (QR, Code128, PDF417) zmieniając enum `EncodeTypes`.  
* **Zastosować transformacje kolorów** poprzez dostęp do `barcode.Parameters.Barcode.Image.Color`.  
* **Udostępnić obraz przez endpoint ASP.NET Core** dla generowania w locie w aplikacjach webowych.

Każdy z tych tematów opiera się na tych samych podstawowych koncepcjach omówionych w tym tutorialu, takich jak użycie **barcode generator c#**, kontrola rozmiaru piksela oraz manipulacja współczynnikiem proporcji.

## Conclusion

Wiesz już, jak **utworzyć obraz kodu kreskowego** w C# przy użyciu Barcode Generator, jak ustawić rozmiar piksela, jak zmienić współczynnik proporcji oraz jak efektywnie generować kody DataBar. Pełny, gotowy do uruchomienia przykład możesz skopiować do dowolnego projektu .NET, dostosować do innych symbologii i rozbudować, aby pasował do rzeczywistych przepływów pracy.

Śmiało eksperymentuj z różnymi wartościami `XDimension`, współczynnikami proporcji i formatami wyjściowymi. Jeśli napotkasz problemy, wróć do tabeli „Common pitfalls” lub zajrzyj do oficjalnej dokumentacji biblioteki po bardziej zaawansowane opcje konfiguracji. Szczęśliwego kodowania!

## What Should You Learn Next?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}