---
category: general
date: 2026-10-08
description: Dowiedz się, jak zmienić rozmiar obrazów kodów kreskowych przy użyciu
  przykładu generatora kodów kreskowych w C#, dostosowując wysokość kreski z 30 px
  do 60 px w zaledwie kilku linijkach kodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: pl
lastmod: 2026-10-08
og_description: Jak szybko zmienić rozmiar kodu kreskowego przy użyciu przykładu generatora
  kodów kreskowych w C#. Dostosuj wysokość pasków, zapisz pliki PNG i unikaj typowych
  pułapek.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Jak zmienić rozmiar kodu kreskowego w C# – przykład generatora krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Jak zmienić rozmiar kodu kreskowego, korzystając z przykładu generatora kodów
  kreskowych w C#
url: /pl/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić rozmiar kodu kreskowego przy użyciu przykładu generatora kodów kreskowych w C#

Jeśli potrzebujesz **jak zmienić rozmiar kodu kreskowego** obrazów w projekcie .NET, ten przewodnik pokazuje pełne rozwiązanie. Zobaczysz zwięzły **przykład generatora kodów kreskowych C#**, który zmienia wysokość pasków z 30 px na 60 px i zapisuje każdą wersję jako plik PNG.

Zmiana rozmiaru kodu kreskowego jest często wymagana, gdy te same dane muszą pojawić się na paragonach, etykietach lub stronach produktów w różnych skalach wizualnych. Zamiast edytować obraz rastrowy w zewnętrznym edytorze, możesz programowo dostosować wymiary kodu kreskowego, zachowując integralność danych.

W tym samouczku:

* Skonfigurujesz generator kodu DataBar Omni‑Directional.
* Zmienisz parametry X‑dimension i bar height.
* Zapiszesz dwa obrazy o różnych wysokościach.
* Zrozumiesz, dlaczego zmiana wysokości pasków działa i na jakie przypadki brzegowe zwrócić uwagę.

> **Wymaganie wstępne** – Masz środowisko programistyczne .NET (Visual Studio 2022 lub nowsze) oraz bibliotekę kodów kreskowych, która udostępnia `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`. Kod działa z najnowszą wersją biblioteki na październik 2026.

## Wymagania wstępne dla przykładu generatora kodów kreskowych C#

| Element | Powód |
|------|--------|
| .NET 6.0 SDK lub nowszy | Zapewnia środowisko uruchomieniowe i funkcje językowe użyte w przykładzie. |
| Biblioteka kodów kreskowych (np. Aspose.BarCode, Dynamsoft lub dowolna biblioteka udostępniająca `BarcodeGenerator`) | Dostarcza enum `EncodeTypes.DatabarOmniDirectional` oraz metody eksportu obrazu. |
| Folder, do którego możesz zapisywać (np. `C:\Temp\Barcodes\`) | Przykład zapisuje pliki PNG w tej lokalizacji. |
| Podstawowa znajomość C# | Samouczek zakłada znajomość klas, właściwości i interpolacji ciągów. |

Zainstaluj bibliotekę za pomocą NuGet, jeśli jeszcze tego nie zrobiłeś:

```bash
dotnet add package Aspose.BarCode
```

Zastąp nazwę pakietu tą, której faktycznie używasz; poniższy interfejs API jest wspólny dla większości SDK kodów kreskowych.

## Jak zmienić rozmiar kodu kreskowego – krok 1: utwórz generator

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z żądaną symbologią i danymi. W tym przykładzie generujemy kod **DataBar Omni‑Directional**, który koduje wartość GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Dlaczego to ważne:** Enum `EncodeTypes.DatabarOmniDirectional` informuje bibliotekę, którego standardu kodu kreskowego użyć. Ciąg danych wykorzystuje identyfikator aplikacji GS1 `(01)` dla 14‑cyfrowego GTIN, zapewniając zgodność kodu z międzynarodowymi standardami handlowymi.

## Jak zmienić rozmiar kodu kreskowego – krok 2: określ szerokość modułu i początkową wysokość pasków

Wizualny rozmiar kodu kreskowego zależy od dwóch parametrów:

* **X‑dimension** – szerokość najmniejszego paska (modułu). Mierzona w pikselach lub milimetrach.
* **Bar height** – pionowa długość pasków.

Ustawienie tych wartości przed zapisem zapewnia, że wygenerowany obraz będzie miał pożądane wymiary.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Wyjaśnienie:** X‑dimension o wartości 2 px daje kompaktowy kod, który nadal skanuje się niezawodnie. Wysokość 30 px jest typowym domyślnym ustawieniem dla małych etykiet. Możesz dostosować X‑dimension niezależnie od wysokości, jeśli potrzebujesz gęstszy lub bardziej rozstawiony wzór.

## Jak zmienić rozmiar kodu kreskowego – krok 3: zapisz pierwszy obraz (wysokość 30 px)

Teraz wyeksportuj kod do pliku PNG. Metoda `Save` przyjmuje ścieżkę pliku oraz enum formatu obrazu.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Wynik:** `DatabarBarHeight30Pixels.png` zawiera kod o wysokości 30 px. Możesz otworzyć plik w dowolnej przeglądarce obrazów, aby zweryfikować wymiary.

## Jak zmienić rozmiar kodu kreskowego – krok 4: zmień wysokość pasków na 60 px

Aby stworzyć większą wersję, po prostu zmodyfikuj właściwość `BarHeight`. Generator ponownie używa tych samych danych i X‑dimension, więc wzór kodu pozostaje identyczny — zmienia się tylko rozmiar wizualny.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Dlaczego to działa:** Silnik renderujący kod oblicza geometrię każdego paska na żądanie. Aktualizacja właściwości wysokości przed kolejnym wywołaniem `Save` powoduje nową rasteryzację z nowymi wymiarami.

## Jak zmienić rozmiar kodu kreskowego – krok 5: zapisz drugi obraz (wysokość 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Masz teraz dwa pliki PNG, jeden mały (30 px) i jeden większy (60 px), gotowe do użycia na etykietach o różnych rozmiarach.

## Pełny kod źródłowy przykładu generatora kodów kreskowych C#

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Skopiuj go do nowego projektu konsolowego, aby od razu przetestować.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Oczekiwany wynik w konsoli:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Po uruchomieniu otwórz dwa pliki PNG, aby zobaczyć różnicę wizualną. Oba kody kreskowe kodują tę samą wartość GTIN‑14 i będą skanowane identycznie, niezależnie od wysokości.

## Dlaczego dostosowanie wysokości pasków jest bezpieczne dla skanowania

Skanery kodów kreskowych odczytują wzór jasnych i ciemnych modułów, a nie absolutną liczbę pikseli. O ile **X‑dimension** pozostaje w tolerancji skanera (zwykle 0,5 mm do 2 mm w jednostkach fizycznych), zmiana wysokości nie wpływa na czytelność. Biblioteka automatycznie skalowuje moduły, zachowując wymagane strefy ciszy i wzory wyrównania.

## Częste pułapki i jak ich unikać

| Pułapka | Jak naprawić |
|---------|------------|
| **Folder wyjściowy nie istnieje** | Wywołaj `Directory.CreateDirectory(outputPath)` przed zapisem. |
| **Nieprawidłowa X‑dimension powodująca rozmyte skany** | Utrzymuj `XDimension.Pixels` między 1 px a 4 px dla większości drukarek; przetestuj fizycznym skanerem. |
| **Używanie formatu rastrowego dla bardzo dużych kodów** | Przejdź na `BarCodeImageFormat.Svg` dla nieskończonej skalowalności bez pikselizacji. |
| **Zapomnienie o zresetowaniu `BarHeight` przed drugim zapisem** | Upewnij się, że przypisujesz nową wysokość **przed** ponownym wywołaniem `Save`. |

## Porada: generuj wiele rozmiarów w pętli

Jeśli potrzebujesz zakresu wysokości (np. 30 px, 45 px, 60 px), prosta pętla `foreach` zmniejsza duplikację kodu:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

## Przypadki brzegowe: różne formaty obrazu i ustawienia DPI

* **Wyjście SVG** – Użyj `BarCodeImageFormat.Svg`, aby uzyskać plik wektorowy, który można skalować bez utraty jakości.  
* **PNG o wysokim DPI** – Ustaw `generator.Parameters.Image.DpiX` i `DpiY` na 300 lub 600 dla obrazów gotowych do druku; wysokość pasków nadal będzie mierzona w pikselach, więc zwiększ ją proporcjonalnie.  
* **Niestandardowe symbologie** – Niektóre typy kodów (np. QR Code) mają osobną właściwość `Size` zamiast `BarHeight`. Skonsultuj dokumentację biblioteki w tych przypadkach.

## Testowanie zmienionego rozmiaru kodu kreskowego

1. Otwórz każdy plik PNG w przeglądarce obrazów i zweryfikuj wymiary w pikselach (np. 150 × 30 px vs. 150 × 60 px).  
2. Wydrukuj obrazy w skali 100 %.  
3. Zeskanuj je ręcznym skanerem kodów kreskowych lub aplikacją mobilną. Zdekodowane dane powinny być

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, pomagające opanować dodatkowe funkcje API i eksplorować alternatywne podejścia w własnych projektach.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}