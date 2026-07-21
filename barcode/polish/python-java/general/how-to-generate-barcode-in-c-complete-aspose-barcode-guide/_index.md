---
category: general
date: 2026-07-21
description: Jak szybko generować kod kreskowy przy użyciu Aspose.BarCode dla C#.
  Dowiedz się, jak tworzyć kod kreskowy za pomocą Aspose, dostosowywać proporcje i
  zapisywać pliki PNG w ciągu kilku minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: pl
lastmod: 2026-07-21
og_description: Jak generować kod kreskowy przy użyciu Aspose.BarCode dla C#. Ten
  przewodnik krok po kroku pokazuje, jak tworzyć kod kreskowy za pomocą Aspose, dostosowywać
  ustawienia i eksportować obrazy.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Jak generować kod kreskowy w C# – Szybki samouczek Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Jak generować kod kreskowy w C# – Kompletny przewodnik Aspose.BarCode
url: /pl/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy w C# – Kompletny przewodnik Aspose.BarCode

Zastanawiałeś się kiedyś **jak generować kod kreskowy** w aplikacji .NET bez walki z niskopoziomowym kodem obrazu? Nie jesteś jedyny. W wielu projektach korporacyjnych musimy **tworzyć kod kreskowy przy użyciu Aspose** dla faktur, etykiet wysyłkowych lub śledzenia zapasów, a biblioteka czyni to zaskakująco proste.

W tym samouczku przeprowadzimy Cię przez praktyczny przykład, który tworzy kod kreskowy DataBar Stacked Omnidirectional, dostosowuje jego współczynnik proporcji i zapisuje dwa pliki PNG. Po zakończeniu będziesz mieć gotowy do uruchomienia program konsolowy oraz jasne zrozumienie kluczowych właściwości, które możesz kontrolować.

## Czego się nauczysz

- Skonfiguruj Aspose.BarCode w projekcie C# (NuGet, podstawy licencjonowania)
- Zainicjalizuj generator **DataBar stacked omnidirectional**
- Dostosuj wymiar X (rozmiar w pikselach) i współczynnik proporcji
- Zapisz kod kreskowy jako obrazy PNG
- Rozszerz przykład o inne typy kodów kreskowych lub formaty wyjściowe

Wcześniejsze doświadczenie z Aspose nie jest wymagane — wystarczy działające .NET 6 (lub nowsze) SDK oraz ulubione IDE.

## Wymagania wstępne

| Requirement | Reason |
|-------------|--------|
| .NET 6 SDK or newer | Nowoczesne funkcje języka i łatwe tworzenie projektów |
| Visual Studio 2022 (or VS Code) | IDE do tworzenia i debugowania |
| Aspose.BarCode for .NET NuGet package | Główna biblioteka wykonująca ciężką pracę |
| A valid Aspose license (or evaluation) | Usuwa znak wodny wersji próbnej i odblokowuje pełne funkcje |

Jeśli nie zainstalowałeś jeszcze pakietu NuGet, uruchom:

```bash
dotnet add package Aspose.BarCode
```

Teraz, gdy wszystko jest gotowe, zanurzmy się w kod.

## Krok 1: Utwórz nowy projekt konsolowy

Najpierw uruchom nową aplikację konsolową. Otwórz terminal i wpisz:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

To tworzy pliki `Program.cs` oraz `.csproj`. Otwórz projekt w edytorze i dodaj odwołanie do Aspose, jak pokazano powyżej.

## Krok 2: Zainicjalizuj BarcodeGenerator

Sercem procesu jest klasa `BarcodeGenerator`. Poprosimy o symbol **DataBar stacked omnidirectional** i podamy jej przykładowy ciąg GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Dlaczego to ważne:** `EncodeTypes.DatabarStackedOmniDirectional` generuje kompaktowy, wysokiej gęstości kod kreskowy idealny dla małych etykiet. Ciąg danych używa identyfikatora aplikacji GS1 `(01)` dla wartości GTIN‑14, którego oczekuje wiele systemów łańcucha dostaw.

## Krok 3: Dostosuj współczynnik proporcji i zapisz obrazy

Aspose.BarCode pozwala dostosować **współczynnik proporcji** symboli DataBar za pomocą `Parameters.Barcode.DataBar.AspectRatio`. Zmiana tej wartości modyfikuje wizualny stosunek szerokości do wysokości, co może być kluczowe przy dopasowywaniu kodu kreskowego do etykiety o stałym rozmiarze.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Wyjaśnienie każdego wiersza**

- `outputPath` wskazuje folder, w którym zostaną zapisane pliki PNG. `Directory.CreateDirectory` zapewnia, że folder istnieje nawet na nowej maszynie.
- `AspectRatio = 15` daje stosunkowo wysoki kod kreskowy; `AspectRatio = 30` rozciąga go w poziomie.
- `generator.Save(...)` zapisuje obraz na dysku. Enum `BarCodeImageFormat.Png` zapewnia jakość bezstratną.
- `Console.WriteLine` daje natychmiastową informację zwrotną po uruchomieniu programu.

### Oczekiwany wynik

Gdy uruchomisz `dotnet run`, powinieneś zobaczyć coś podobnego:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Otwórz oba pliki PNG obok siebie; zauważysz, że drugi obraz jest wyraźnie szerszy przy zachowaniu tej samej wysokości. Oba obrazy można zeskanować standardowymi czytnikami kodów kreskowych.

## Krok 4: Uruchom pełny przykład

Oto **pełne, gotowe do uruchomienia źródło** w jednym bloku dla wygody kopiowania:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Skompiluj i uruchom:

```bash
dotnet run
```

Voilà — dwa idealnie wygenerowane pliki PNG z kodem kreskowym pojawią się w folderze `GeneratedBarcodes/`.

## Krok 5: Rozszerzanie przykładu (opcjonalnie)

Teraz, gdy **wiesz, jak generować kod kreskowy** przy użyciu Aspose, możesz się zapytać: *Co jeszcze mogę dostosować?* Oto kilka szybkich pomysłów:

| Property | What it does | Typical use‑case |
|----------|--------------|------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Zmienia rozmiar tekstu czytelnego dla człowieka | Większa czcionka dla skanerów ręcznych |
| `generator.Parameters.Barcode.ImageFormat` | Globalny format wyjściowy (PNG, JPEG, BMP, itp.) | JPEG dla rozmiaru przyjaznego sieci |
| `generator.Parameters.Barcode.Color` | Ustawia kolor pierwszoplanowy | Kategorie kodowane kolorem |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Wyjście wektorowe dla nieskończonego skalowania | PDF gotowy do druku |

Aby eksperymentować, po prostu dodaj odpowiednie linie przed każdym wywołaniem `Save`.

## Częste pułapki i wskazówki profesjonalistów

- **Umieszczenie licencji:** Jeśli używasz płatnej licencji, wywołaj `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` przed utworzeniem generatora. Zapomnienie tego pozostawi znak wodny na obrazie.
- **Nieprawidłowy ciąg danych:** Symbole DataBar oczekują numerycznych danych GS1. Podanie znaków alfabetowych spowoduje wyrzucenie `ArgumentException`.
- **Bezpieczeństwo wątków:** Instancje `BarcodeGenerator` **nie** są bezpieczne wątkowo. Utwórz nową instancję na wątek, jeśli generujesz kody kreskowe równolegle.
- **Rozmiar obrazu vs. możliwości skanera:** Bardzo wysoki `XDimension.Pixels` może wygenerować ogromny obraz, który niektóre skanery mają trudności odczytać. Przetestuj na docelowym sprzęcie.

## Podsumowanie

Właśnie omówiliśmy **jak generować kod kreskowy** w C# przy użyciu Aspose.BarCode, od konfiguracji projektu po zapis dwóch obrazów o różnych współczynnikach proporcji. Kluczowe kroki — inicjalizacja generatora, konfiguracja wymiaru X i współczynnika proporcji oraz wywołanie `Save` — tworzą powtarzalny wzorzec, który możesz zastosować do dowolnego typu kodu kreskowego obsługiwanego przez Aspose.

Teraz możesz **tworzyć kod kreskowy przy użyciu Aspose** dla faktur, etykiet wysyłkowych lub tagów inwentaryzacyjnych i masz solidną bazę do eksploracji bardziej zaawansowanych funkcji, takich jak kolor, własne czcionki czy wyjście SVG. Śmiało modyfikuj kod, eksperymentuj z innymi `EncodeTypes` i integruj generator z istniejącymi usługami.

Masz pytania lub chcesz zobaczyć konkretny styl kodu kreskowego? zostaw komentarz poniżej i szczęśliwego kodowania!

## Co warto nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak dostosować kod kreskowy – współczynnik proporcji Codablock F przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}