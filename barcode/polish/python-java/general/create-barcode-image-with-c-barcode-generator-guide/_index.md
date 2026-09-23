---
category: general
date: 2026-08-09
description: Utwórz obraz kodu kreskowego za pomocą generatora kodów kreskowych w
  C# i naucz się generować wiele kodów kreskowych o niestandardowych proporcjach w
  ciągu kilku minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: pl
lastmod: 2026-08-09
og_description: Utwórz obraz kodu kreskowego za pomocą generatora kodów kreskowych
  w C#. Ten samouczek pokazuje, jak generować wiele kodów kreskowych, dostosowywać
  proporcje i efektywnie zapisywać pliki PNG.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Utwórz obraz kodu kreskowego przy użyciu generatora kodów kreskowych w C#
  – szybki przewodnik
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Tworzenie obrazu kodu kreskowego przy użyciu generatora kodów kreskowych w
  C# – przewodnik
url: /pl/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego przy użyciu generatora kodów kreskowych C# – przewodnik

Jeśli potrzebujesz szybko **utworzyć obraz kodu kreskowego**, ten przewodnik pokaże Ci, jak zrobić to za pomocą generatora kodów kreskowych C#. Nauczysz się generować wiele kodów kreskowych, zmieniać współczynnik proporcji i zapisywać każdy obraz jako plik PNG.

Generowanie obrazów kodów kreskowych jest powszechnym zadaniem przy tworzeniu systemów inwentaryzacji, terminali punktu sprzedaży lub etykiet wysyłkowych. Po zakończeniu tego samouczka będziesz mieć dwa gotowe do użycia pliki PNG, które demonstrują różne współczynniki proporcji, oraz zrozumiesz, jak rozszerzyć podejście na dowolną liczbę kodów kreskowych.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące C#)  
* Odwołanie do biblioteki kodów kreskowych, która obsługuje DataBar Stacked Omnidirectional (na przykład, **Aspose.BarCode for .NET**). Fragmenty kodu używają API Aspose, ale koncepcje mają zastosowanie do każdej biblioteki o podobnych właściwościach.

Nie potrzebujesz osobnej bazy danych ani serwera WWW — to jest zwykła aplikacja konsolowa.

## Krok 1: Skonfiguruj projekt konsolowy

Utwórz nowy projekt konsolowy i dodaj bibliotekę kodów kreskowych za pomocą NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Polecenie `dotnet add package` pobiera najnowszą stabilną wersję **Aspose.BarCode**, która udostępnia klasę `BarcodeGenerator` używaną później.

## Krok 2: Napisz pełny program

Otwórz *Program.cs* i zamień jego zawartość na kompletny przykład poniżej. Program tworzy **obraz kodu kreskowego**, zmienia współczynnik proporcji i zapisuje dwa pliki PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Dlaczego każdy element ma znaczenie

* **Create barcode image** – Konstruktor `BarcodeGenerator` inicjalizuje obiekt z żądaną symbologią i danymi.  
* **c# barcode generator** – Właściwość `Parameters` daje pełną kontrolę nad opcjami renderowania; ustawienie `XDimension.Pixels` zapewnia wyraźne paski na ekranie.  
* **generate multiple barcodes** – Zmieniając `DataBar.AspectRatio` pomiędzy zapisami, ta sama instancja generatora tworzy dwa odrębne obrazy bez ponownego tworzenia obiektu, co jest bardziej wydajne.

## Krok 3: Uruchom program i zobacz wyniki

Uruchom aplikację:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście konsoli podobne do:

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Otwórz folder `BarcodeOutputs`. Znajdziesz tam dwa pliki PNG:

* **DatabarAspectRatio15.png** – kompaktowy kod kreskowy odpowiedni dla etykiet o ograniczonej wysokości.  
* **DatabarAspectRatio30.png** – wyższy kod kreskowy, który wiele skanerów odczytuje bardziej niezawodnie z większej odległości.

Oba obrazy są gotowe do osadzenia w plikach PDF, wydrukowania na paragonach lub wysłania do aplikacji mobilnej.

## Krok 4: Rozszerz rozwiązanie, aby generować dowolną liczbę kodów kreskowych

Powyższy wzorzec łatwo skaluje się:

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – Pętla iteruje po tablicy współczynników proporcji, tworząc odrębny **obraz kodu kreskowego** dla każdej wartości.  
* Dostosuj `EncodeTypes` lub zakodowany ciąg, aby generować kody QR, Code 128 lub inne symbologie bez zmiany otaczającej logiki.

## Praktyczne wskazówki i typowe pułapki

| Wskazówka | Wyjaśnienie |
|-----|-------------|
| **Reuse the same generator** | Ponowne inicjalizowanie `BarcodeGenerator` dla każdego obrazu dodaje niepotrzebny narzut. Zmienianie parametrów pomiędzy wywołaniami `Save` jest szybsze i zużywa mniej pamięci. |
| **Validate the output folder** | Zawsze wywołuj `Directory.CreateDirectory` przed zapisem; w przeciwnym razie `Save` zgłosi `DirectoryNotFoundException`. |
| **Choose an appropriate X‑dimension** | Bardzo niskie wartości pikseli (np. 1) mogą sprawić, że kod kreskowy będzie nieczytelny na ekranach o niskiej rozdzielczości. Wartości 2–3 działają dobrze dla większości drukarek. |
| **Mind the encoding** | GS1 DataBar wymaga wiodącego `(01)` dla GTIN. Jeśli pominiesz nawiasy, biblioteka może wygenerować nieprawidłowy kod kreskowy. |
| **Test with a real scanner** | Samo oglądanie nie wystarczy. Przetestuj pliki PNG na rzeczywistym sprzęcie skanującym, którego zamierzasz używać. |

## Oczekiwany wynik (opis wizualny)

*Oba pliki PNG wyświetlają ciemny na jasnym kod DataBar Stacked Omnidirectional. Wersja z współczynnikiem proporcji 15 jest krótsza, podczas gdy wersja z współczynnikiem 30 jest mniej więcej dwa razy wyższa.*  

Jeśli osadzisz obrazy w dokumencie, będą renderowane ostro, ponieważ ustawiliśmy `XDimension.Pixels = 2`.

## Zakończenie

Teraz wiesz, jak **utworzyć pliki obrazu kodu kreskowego** przy użyciu **generatora kodów kreskowych C#**, i możesz **generować wiele kodów kreskowych** poprzez dostosowanie współczynnika proporcji lub dowolnego innego parametru. Pełny, działający przykład demonstruje najlepsze praktyki, takie jak ponowne użycie instancji generatora, obsługa katalogów wyjściowych oraz weryfikacja tworzenia plików.

Następnie możesz zbadać:

* Dodawanie własnych kolorów za pomocą `generator.Parameters.Barcode.Color` (słowo kluczowe drugorzędne: **c# barcode generator**)  
* Eksport do innych formatów, takich jak JPEG lub SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Integracja logiki tworzenia kodów kreskowych z Web API w celu udostępniania obrazów na żądanie (słowo kluczowe drugorzędne

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i zbadać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy PNG – Współczynnik proporcji DataMatrix – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [samouczek generatora kodów kreskowych c# – Dostosuj współczynniki proporcji kodu 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}