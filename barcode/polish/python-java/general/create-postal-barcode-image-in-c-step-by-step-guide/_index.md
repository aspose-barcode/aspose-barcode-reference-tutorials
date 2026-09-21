---
category: general
date: 2026-08-03
description: Szybko utwórz obraz kodu pocztowego w C#. Dowiedz się, jak generować
  kod pocztowy, ustawiać wymiary kodu i generować kod Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: pl
lastmod: 2026-08-03
og_description: Utwórz obraz kodu kreskowego pocztowego w C# dzięki temu kompletnemu
  samouczkowi; dowiedz się, jak ustawić wymiary kodu kreskowego, wygenerować kod Planet
  oraz tworzyć kody RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Tworzenie obrazu kodu kreskowego pocztowego w C# – pełny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Tworzenie obrazu kodu pocztowego w C# – przewodnik krok po kroku
url: /pl/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego pocztowego w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego pocztowego** w C#, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Omówimy **jak wygenerować kod kreskowy pocztowy**, **jak ustawić wymiary kodu kreskowego** oraz **jak wygenerować kod Planet** dla popularnych standardów pocztowych.

Na końcu otrzymasz dwa gotowe do użycia pliki PNG — jeden z kodem Planet i jeden z kodem RM4SCC — każdy o wysokości 100 px. Nie są potrzebne żadne dodatkowe narzędzia poza biblioteką Aspose.BarCode for .NET.

## Wymagania wstępne

* .NET 6 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
* Visual Studio 2022 lub dowolne IDE C#
* Pakiet NuGet **Aspose.BarCode** (biblioteka udostępniająca `BarcodeGenerator`)

## Krok 1: Zainstaluj bibliotekę kodów kreskowych

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, która zawiera `BarcodeGenerator` oraz wyliczenie `EncodeTypes` niezbędne do kodów kreskowych pocztowych.

## Krok 2: Zdefiniuj folder wyjściowy

Utworzenie niezawodnej ścieżki wyjściowej zapobiega błędom w czasie wykonywania, gdy folder nie istnieje.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Dlaczego to ważne*: `Directory.CreateDirectory` jest idempotentny — tworzy folder tylko wtedy, gdy jeszcze nie istnieje, co zapobiega wyjątkom przy kolejnych uruchomieniach.

## Krok 3: Skonfiguruj wspólne wymiary kodu kreskowego

Ustawienie wymiaru X (szerokość pojedynczej kreski) oraz całkowitej wysokości kreski pozwala kontrolować wizualny rozmiar generowanego obrazu.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Jak ustawić wymiary kodu kreskowego**: właściwość `Parameters.Barcode.XDimension.Pixels` definiuje szerokość wąskiej kreski, natomiast `Parameters.Barcode.BarHeight.Pixels` określa pełną wysokość. Dostosuj te wartości, aby spełniały specyfikacje Twojej usługi pocztowej.

## Krok 4: Wygeneruj kod Planet

Planet jest szeroko stosowanym kodem kreskowym pocztowym w Wielkiej Brytanii. Poniższy kod tworzy kod Planet o wysokości 100 px i zapisuje go jako PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Dlaczego to działa**: `EncodeTypes.Planet` informuje generator, aby użył symboliki Planet. Metoda `Save` zapisuje plik PNG w określonej ścieżce, zachowując wcześniej ustawione wymiary.

## Krok 5: Wygeneruj kod RM4SCC

RM4SCC jest holenderskim standardem kodów kreskowych pocztowych. Poniższy kod odzwierciedla przykład Planet, demonstrując **jak wygenerować kod kreskowy pocztowy** innego typu przy zachowaniu identycznych wymiarów.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Oba pliki PNG znajdują się teraz w folderze `Barcodes`. Po otwarciu zobaczysz czyste kody kreskowe o wysokości 100 px, gotowe do druku lub osadzenia w dokumentach.

## Pełny kod źródłowy

Poniżej znajduje się kompletny, gotowy do uruchomienia program, który **tworzy obrazy kodów kreskowych pocztowych** dla standardów Planet i RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Oczekiwany wynik

Uruchomienie programu wypisuje ścieżki do plików i tworzy dwa pliki PNG:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Każdy obraz ma wysokość 100 px, przy szerokości wąskiej kreski 4 px, co odpowiada ustawionym wymiarom.

## Praktyczne wskazówki i typowe pułapki

* **Uprawnienia folderu** – Jeśli program działa pod ograniczonym kontem, upewnij się, że docelowy folder jest zapisywalny.
* **Różne wymiary** – Aby utworzyć wyższy kod kreskowy, zwiększ `barHeightPixels`. Dla większej rozdzielczości, zmniejsz `xDimensionPixels`, ale zachowaj wartość ≥ 2, aby uniknąć artefaktów renderowania.
* **Inne symbologie pocztowe** – Aspose.BarCode obsługuje także `EncodeTypes.Postnet` i `EncodeTypes.AustralianPost`. Zamień wartość `EncodeTypes` i zachowaj tę samą logikę wymiarów.
* **Format obrazu** – Użyj `BarCodeImageFormat.Jpeg`, aby uzyskać mniejszy rozmiar pliku, gdy jakość bezstratna nie jest wymagana.

## Zakończenie

Teraz wiesz, jak **utworzyć obrazy kodów kreskowych pocztowych** w C#, konfigurując wymiary, wybierając odpowiednią symbologię i zapisując wynik jako PNG. Samouczek omówił **jak wygenerować kod kreskowy pocztowy**, pokazał **generowanie kodu Planet** oraz wyjaśnił **jak ustawić wymiary kodu kreskowego** dla spójnego wyniku.

Następnie możesz zbadać **dostosowywanie kolorów kodu kreskowego**, dodawanie **czytelnego dla człowieka tekstu** lub integrowanie obrazów z fakturami PDF. Ten sam schemat działa dla każdego innego typu kodu kreskowego obsługiwanego przez Aspose.BarCode, co pozwala rozbudować to rozwiązanie do pełnego przepływu automatyzacji pocztowej.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}