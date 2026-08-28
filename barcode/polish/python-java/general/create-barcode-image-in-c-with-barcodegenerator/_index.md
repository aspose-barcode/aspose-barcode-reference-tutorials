---
category: general
date: 2026-08-12
description: Utwórz obraz kodu kreskowego w C# przy użyciu BarCodeGenerator. Dowiedz
  się, jak generować DataBar, kontrolować rozmiar obrazu kodu kreskowego oraz efektywnie
  tworzyć wiele kodów kreskowych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: pl
lastmod: 2026-08-12
og_description: Utwórz obraz kodu kreskowego w C# za pomocą BarCodeGenerator. Ten
  samouczek pokazuje krok po kroku, jak generować kody DataBar, dostosować rozmiar
  obrazu kodu kreskowego oraz tworzyć wiele kodów kreskowych.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Tworzenie obrazu kodu kreskowego w C# – kompletny przewodnik BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Utwórz obraz kodu kreskowego w C# przy użyciu BarCodeGenerator
url: /pl/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie obrazu kodu kreskowego w C# przy użyciu BarCodeGenerator

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić przy użyciu klasy `BarCodeGenerator`. Niezależnie od tego, czy budujesz system POS w handlu detalicznym, czy narzędzie do śledzenia zapasów, nauczysz się generować symbole DataBar, kontrolować rozmiar obrazu kodu kreskowego oraz tworzyć wiele kodów w jednym przebiegu.

Odkryjesz także, jak API **barcode generator c#** pozwala dostosować wymiary, zmienić format wyjściowy i obsłużyć przypadki brzegowe, takie jak nieprawidłowe ciągi danych. Po zakończeniu tutorialu będziesz pewnie **tworzyć wiele kodów kreskowych** bez pisania powtarzalnego kodu.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- .NET 6.0 lub nowszy zainstalowany  
- Środowisko programistyczne (Visual Studio, Rider lub VS Code)  
- Pakiet NuGet Aspose.BarCode for .NET (lub dowolną kompatybilną bibliotekę udostępniającą `BarCodeGenerator`)  

Pakiet możesz dodać za pomocą:

```bash
dotnet add package Aspose.BarCode
```

## Co obejmuje ten tutorial

1. Utworzenie instancji **barcode generator c#** dla kodowania DataBar Omni‑directional.  
2. Dostosowanie **barcode image size** poprzez zmianę X‑dimension i wysokości pasków.  
3. Użycie pętli do **create multiple barcodes** o różnych wysokościach.  
4. Zapis obrazów jako pliki PNG i weryfikacja wyniku.  

Wszystkie fragmenty kodu są kompletne i gotowe do skopiowania do nowego projektu konsolowego.

![Create barcode image example](barcode-example.png){alt="Create barcode image example"}

## Krok 1: Inicjalizacja generatora – podstawy tworzenia obrazu kodu kreskowego

Pierwszym krokiem jest utworzenie obiektu `BarCodeGenerator` z żądaną symbologią. Dla symbolu DataBar Omni‑directional używasz `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Dlaczego to ważne:** Inicjalizacja generatora definiuje zasady kodowania i ładunek danych. Jeśli pominiesz prawidłową wartość `EncodeTypes`, biblioteka wygeneruje nieobsługiwany kod kreskowy lub zgłosi wyjątek.

## Krok 2: Konfiguracja X‑dimension i wysokości pasków – kontrola rozmiaru obrazu kodu kreskowego

Wizualny rozmiar kodu kreskowego zależy od dwóch parametrów:

| Parameter | What it controls | Typical range |
|-----------|------------------|---------------|
| `x_dimension.pixels` | Width of the smallest module (the “dot”) | 1 – 4 px |
| `bar_height.pixels`  | Height of the vertical bars                | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Pro tip:** Mniejsza X‑dimension daje obraz o wyższej rozdzielczości, ale może być trudniejsza do zeskanowania na drukarkach niskiej jakości. Dostosuj wartość w zależności od docelowego sprzętu skanującego.

## Krok 3: Zapis pierwszego kodu kreskowego – tworzenie obrazu kodu kreskowego o wysokości 30 px

Teraz możesz wygenerować obraz i zapisać go na dysku. Metoda `Save` przyjmuje ścieżkę pliku oraz enum formatu obrazu.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Oczekiwany rezultat:** Plik PNG o nazwie `Databar30.png` pojawia się w `C:\Barcodes`. Otwarcie pliku pokazuje symbol DataBar Omni‑directional o wyraźnym, wysokim kontraście.

## Krok 4: Zmiana wysokości i generowanie dodatkowych obrazów – tworzenie wielu kodów kreskowych

Aby **create multiple barcodes** o różnych wymiarach, wystarczy zmodyfikować właściwość `BarHeight` i ponownie wywołać `Save`. Dzięki temu nie musisz ponownie tworzyć generatora, co oszczędza pamięć i czas CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Dlaczego to działa:** Obiekt `BarCodeGenerator` przechowuje cały stan konfiguracji. Zmiana jednej właściwości aktualizuje silnik renderujący przy następnym wywołaniu `Save`, umożliwiając **create multiple barcodes** w sposób efektywny.

## Krok 5: Zaawansowane – jak generować DataBar z własnymi danymi

Powyższy przykład używa statycznego ładunku GS1. W rzeczywistych scenariuszach często trzeba osadzić zmienne identyfikatory produktów. Biblioteka akceptuje dowolny ciąg spełniający specyfikację DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Kluczowy punkt:** Ustawienie `generator.CodeText` aktualizuje kodowane dane bez ponownego tworzenia obiektu. To zalecany wzorzec **how to generate databar** przy obsłudze dużych zbiorów danych.

## Krok 6: Weryfikacja i rozwiązywanie problemów – zapewnienie prawidłowego rozmiaru obrazu kodu kreskowego

Po wygenerowaniu obrazów możesz programowo potwierdzić, że wymiary odpowiadają oczekiwaniom. Klasa `Image` z `System.Drawing` może odczytać plik i zgłosić jego rozmiar.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Jeśli wysokość nie odzwierciedla ustawionej wartości, sprawdź:

- **X‑dimension**: Bardzo mała wartość może spowodować zaokrąglenie wysokości przez renderer.  
- **Image format**: Niektóre formaty (np. JPEG) stosują kompresję, która może zmienić liczbę pikseli przy zapisie. PNG zachowuje dokładne wymiary.

## Krok 7: Najlepsze praktyki dotyczące rozmiaru obrazu kodu kreskowego i wydajności

| Recommendation | Reason |
|----------------|--------|
| Keep `x_dimension.pixels` between 2 – 3 px for most scanners. | Balances readability and file size. |
| Use PNG for lossless output when the image will be printed. | Guarantees exact dimensions and sharp edges. |
| Reuse a single `BarCodeGenerator` instance when generating many barcodes. | Reduces object allocation overhead. |
| Validate the input string against the GS1 standard before assigning to `CodeText`. | Prevents runtime exceptions and invalid scans. |
| Store generated images in a dedicated folder with a clear naming convention (e.g., `Databar_{GTIN}.png`). | Simplifies downstream processing and audit trails. |

## Pełny działający przykład

Poniżej znajduje się kompletny program, który zawiera wszystkie kroki od inicjalizacji po weryfikację. Skopiuj kod do nowego projektu konsolowego i uruchom go.



## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}