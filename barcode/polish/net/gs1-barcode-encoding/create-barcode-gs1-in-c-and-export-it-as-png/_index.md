---
category: general
date: 2026-09-29
description: Utwórz kod kreskowy GS1 w C# i generuj obrazy PNG kodu kreskowego przy
  użyciu BarcodeGenerator. Postępuj zgodnie z instrukcją krok po kroku, aby efektywnie
  eksportować obraz kodu kreskowego.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: pl
lastmod: 2026-09-29
og_description: Utwórz kod kreskowy GS1 w C# i generuj pliki PNG kodu kreskowego za
  pomocą BarcodeGenerator. Skorzystaj z tego kompletnego przewodnika, aby szybko wyeksportować
  obraz kodu kreskowego.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Utwórz kod kreskowy GS1 w C# – wyeksportuj jako PNG w kilka minut
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Utwórz kod kreskowy GS1 w C# i wyeksportuj go jako PNG
url: /pl/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy GS1 w C# i wyeksportuj go jako PNG

Jeśli potrzebujesz **utworzyć kod kreskowy GS1** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz zwięzłe rozwiązanie, które generuje obraz PNG kodu kreskowego i eksportuje go na dysk, wszystko przy użyciu klasy Aspose.BarCode `BarcodeGenerator`.

Generowanie kodu kreskowego GS1 jest powszechnym wymogiem w systemach zarządzania zapasami, wysyłką i punktami sprzedaży. Po zakończeniu tego samouczka będziesz w stanie napisać mały program w C#, który tworzy zgodny z GS1 kod MicroPDF417 i zapisuje go jako wysokiej jakości plik PNG.

## Wymagania wstępne

* **.NET 6** (lub dowolna nowsza wersja .NET) zainstalowana.
* **Visual Studio 2022** lub dowolne IDE obsługujące C#.
* Pakiet NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – dostarcza API `BarcodeGenerator` używane w przykładach.
* Podstawowa znajomość składni C#.

> **Wskazówka:** Użyj darmowej edycji community Aspose.BarCode podczas eksperymentów; pełna wersja usuwa wszelkie znaki wodne wersji ewaluacyjnej.

## Krok 1 – Utwórz kod kreskowy GS1 przy użyciu BarcodeGenerator

Pierwszą rzeczą, którą musisz zrobić, jest utworzenie instancji `BarcodeGenerator` dla formatu *MicroPDF417* i podanie mu ciągu danych GS1. Identyfikatory aplikacji GS1 (AI) są otoczone nawiasami, np. `(01)` dla GTIN‑14 i `(21)` dla numeru seryjnego.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Dlaczego to ważne:**  
`EncodeTypes.MicroPdf417` automatycznie traktuje wejście jako dane GS1, gdy ciąg zawiera prawidłowe AI. Dzięki temu wygenerowany kod kreskowy jest zgodny ze specyfikacją GS1 bez dodatkowej konfiguracji.

## Krok 2 – Ustaw wymiary kodu kreskowego dla optymalnego rozmiaru

Wizualny rozmiar kodu kreskowego jest kontrolowany przez jego **X‑wymiar** (szerokość pojedynczego modułu). Dostosowanie `XDimension.Pixels` pozwala precyzyjnie ustawić ostateczny rozmiar obrazu, zachowując czytelność.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Jak wygenerować PNG kodu kreskowego** – X‑wymiar nie wpływa na kodowane dane; zmienia jedynie fizyczne wymiary wygenerowanego obrazu. Jeśli potrzebujesz większego kodu kreskowego do druku wysokiej rozdzielczości, zwiększ tę wartość (np. `3` lub `4`).

## Krok 3 – Wygeneruj PNG kodu kreskowego i wyeksportuj obraz kodu

Teraz możesz wyrenderować kod kreskowy i zapisać go do pliku PNG. Metoda `Save` przyjmuje ścieżkę docelową oraz żądany format obrazu.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Co się dzieje w tle:**  
`BarcodeGenerator.Save` rasteryzuje kod kreskowy do bitmapy, stosuje ustawiony wcześniej X‑wymiar i koduje bitmapę jako plik PNG. Powstały plik może być używany bezpośrednio na stronach internetowych, drukowany na etykietach lub osadzany w plikach PDF.

## Pełny przykład kodu źródłowego

Poniżej znajduje się kompletny, samodzielny program konsolowy, który możesz skopiować, wkleić i uruchomić. Demonstruje **jak generować pliki PNG kodu kreskowego**, **wyeksportować obraz kodu**, oraz zawiera podstawowe obsługi błędów.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Oczekiwany wynik

Po uruchomieniu programu powinieneś zobaczyć:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Otwarcie pliku PNG wyświetla wyraźny kod **GS1 MicroPDF417**, który koduje GTIN‑14 `12345678901234` oraz numer seryjny `ABC123`. Zeskanowanie go dowolnym skanerem kompatybilnym z GS1 zwróci oryginalny ciąg danych.

## Częste pułapki i najlepsze praktyki

| Problem | Dlaczego się pojawia | Jak tego uniknąć |
|-------|----------------|-----------------|
| **Nieprawidłowe formatowanie AI** | Brak nawiasów lub niewłaściwa kolejność powoduje, że kod nie jest GS1. | Zawsze otaczaj każdy AI nawiasami, np. `(01)`. |
| **Zbyt mały X‑wymiar** | Kod staje się nieczytelny na urządzeniach o niskiej rozdzielczości. | Utrzymuj `XDimension.Pixels` ≥ 2 dla większości drukarek; zwiększ dla wyjścia o wysokim DPI. |
| **Folder wyjściowy nie istnieje** | `Save` rzuca `DirectoryNotFoundException`. | Użyj `Directory.CreateDirectory` przed wywołaniem `Save`. |
| **Użycie niewłaściwego EncodeType** | Niektóre typy (np. `Code128`) nie obsługują danych GS1 domyślnie. | Wybierz `EncodeTypes.MicroPdf417` lub dowolny typ kompatybilny z GS1. |
| **Brak referencji NuGet** | Błędy kompilacji takie jak `The type or namespace name 'Aspose' could not be found`. | Zainstaluj pakiet `Aspose.BarCode` przez NuGet. |

## Rozszerzanie przykładu

* **Różne formaty obrazu** – Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Gif` lub `Bmp`, jeśli potrzebujesz innego formatu.
* **Wyjście o wyższej rozdzielczości** – Ustaw `generator.Parameters.ImageResolution.DpiX` i `DpiY` przed zapisem.
* **Osadzanie w PDF** – Użyj `Aspose.Pdf`, aby umieścić PNG w fakturze PDF lub etykiecie.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy GS1** w C# przy użyciu Aspose.BarCode `BarcodeGenerator`, **generować PNG kodu kreskowego** i **wyeksportować obraz kodu** do systemu plików. Poradnik omówił każdy krok — od inicjalizacji generatora danymi GS1, przez dostosowanie X‑wymiaru, po zapisanie końcowego pliku PNG — jednocześnie rozwiązując typowe błędy i proponując pomysły na rozszerzenia.

Śmiało eksperymentuj z innymi identyfikatorami aplikacji GS1, różnymi symbologiami kodów kreskowych lub obrazami o wyższej rozdzielczości. Gdy opanujesz te podstawy, generowanie zgodnych kodów kreskowych dla zapasów, wysyłki czy handlu detalicznego stanie się rutynową częścią Twojego zestawu narzędzi .NET.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obrazy kodów GS1 w C# – Jak szybko generować kod kreskowy w C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Utwórz PNG kodu kreskowego w C# – przewodnik krok po kroku](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Utwórz obraz kodu kreskowego w C# – kompletny przewodnik programistyczny](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}