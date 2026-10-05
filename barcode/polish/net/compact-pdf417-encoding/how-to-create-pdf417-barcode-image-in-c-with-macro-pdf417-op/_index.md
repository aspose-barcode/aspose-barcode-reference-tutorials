---
category: general
date: 2026-09-13
description: Dowiedz się, jak stworzyć obraz kodu kreskowego PDF417 w C# przy użyciu
  BarcodeGenerator i opcji Macro PDF417. Krok po kroku kod, wskazówki i pełny przykład.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: pl
lastmod: 2026-09-13
og_description: Utwórz obraz kodu kreskowego PDF417 w C# za pomocą BarcodeGenerator.
  Postępuj zgodnie z tym szczegółowym samouczkiem, aby skonfigurować opcje Macro PDF417
  i zapisać kod kreskowy w formacie PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Tworzenie obrazu kodu kreskowego PDF417 w C# – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Jak utworzyć obraz kodu kreskowego PDF417 w C# z opcjami Macro PDF417
url: /pl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego PDF417 w C# z opcjami Macro PDF417

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego PDF417** w C#, ten przewodnik pokazuje dokładnie, jak to zrobić przy użyciu **klasy BarcodeGenerator**. Niezależnie od tego, czy tworzysz system śledzenia dokumentów, czy kodujesz duże pliki, poniższe instrukcje krok po kroku obejmują wszystko, od konfiguracji opcji Macro PDF417 po zapisanie ostatecznego pliku PNG.

Generowanie kodu kreskowego jest proste, gdy zrozumiesz kluczowe parametry. W tym samouczku dowiesz się, jak:

* Zainicjować `BarcodeGenerator` dla **Macro PDF417**.
* Dostosować rozmiar modułu kodu kreskowego (`XDimension`).
* Skonfigurować ustawienia specyficzne dla segmentu, takie jak identyfikator pliku, identyfikator segmentu i suma kontrolna.
* Zapisać wynik jako **format obrazu kodu kreskowego** (PNG), który może być wyświetlany w dowolnym interfejsie użytkownika.

Jedynym wymogiem wstępnym jest środowisko programistyczne .NET (Visual Studio 2022 lub nowsze) oraz pakiet NuGet Aspose.BarCode for .NET, który udostępnia API `BarcodeGenerator` używane w przykładach.

## Jak utworzyć obraz kodu kreskowego PDF417 w C# – przegląd

Utworzenie obrazu kodu kreskowego PDF417 składa się z czterech logicznych kroków:

1. **Utwórz generator** – zainicjuj `BarcodeGenerator` z `EncodeTypes.MacroPdf417` oraz danymi, które chcesz zakodować.  
2. **Zdefiniuj rozmiar modułu** – ustaw `XDimension.Pixels`, aby kontrolować fizyczną szerokość każdego elementu kodu kreskowego.  
3. **Skonfiguruj opcje Macro PDF417** – określ liczbę kolumn, identyfikatory pliku, numery segmentów oraz opcjonalną sumę kontrolną.  
4. **Zapisz kod kreskowy** – zapisz wygenerowany obraz na dysku, używając obsługiwanego **formatu obrazu kodu kreskowego**, takiego jak PNG.

Każdy krok jest wyjaśniony szczegółowo poniżej, wraz z kompletnym, uruchamialnym kodem C#.

## Krok 1: Zainicjuj BarcodeGenerator dla Macro PDF417

Pierwsza linia tworzy obiekt `BarcodeGenerator`, który wie, że musi wygenerować kod kreskowy **Macro PDF417**. Konstruktor przyjmuje dwa argumenty: typ kodowania oraz surowy ciąg danych.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Dlaczego to ważne:**  
`EncodeTypes.MacroPdf417` informuje bibliotekę, że kod kreskowy ma być traktowany jako kontener wielosegmentowy, co jest niezbędne, gdy trzeba podzielić duży plik na kilka symboli. Instancja `BarcodeGenerator` jest obiektem zwalnianym, więc blok `using` zapewnia zwolnienie wszystkich niezarządzanych zasobów po zapisaniu obrazu.

## Krok 2: Ustaw rozmiar modułu kodu kreskowego (XDimension)

`XDimension` kontroluje szerokość w pikselach pojedynczego modułu kodu kreskowego (najmniejszego czarnego lub białego paska). Wartość **2 piksele** daje kompaktowy, a jednocześnie czytelny obraz.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktyczna wskazówka:**  
Jeśli docelowa drukarka ma niską rozdzielczość DPI, zwiększ liczbę pikseli (np. `3` lub `4`), aby uniknąć rozmazywania. Natomiast przy wyświetlaniu na ekranie możesz utrzymać niską wartość, aby zmniejszyć rozmiar pliku.

## Krok 3: Skonfiguruj specyficzne opcje Macro PDF417

Macro PDF417 dodaje metadane, które pozwalają skanerowi odtworzyć oryginalny plik z wielu segmentów kodu kreskowego. Najczęściej używane opcje to:

| Property | Meaning |
|----------|---------|
| `Columns` | Liczba kolumn w każdym symbolu (wpływa na szerokość). |
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku. |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 1). |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów tworzących plik. |
| `MacroPdf417FileName` | Oryginalna nazwa pliku (opcjonalnie, do wyświetlenia). |
| `MacroPdf417Checksum` | Opcjonalna 16‑bitowa suma kontrolna weryfikująca integralność. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Dlaczego te ustawienia są ważne:**  
- **Columns** wpływają na czytelność i ogólne wymiary obrazu.  
- **FileID** musi być taki sam we wszystkich segmentach, aby dekoder wiedział, że należą do siebie.  
- **SegmentID** i **SegmentsCount** pozwalają skanerowi prawidłowo uporządkować fragmenty.  
- **FileName** i **Checksum** są opcjonalne, ale poprawiają doświadczenie użytkownika oraz integralność danych.

**Przypadek brzegowy:** Jeśli wygenerujesz więcej niż 999 segmentów, pole `SegmentID` przepełnia się; w takim wypadku podziel dane na wiele plików.

## Krok 4: Zapisz wygenerowany kod kreskowy jako obraz PNG

Ostatni krok zapisuje kod kreskowy na dysku. `BarCodeImageFormat.Png` tworzy obraz bezstratny, który działa w środowiskach webowych, desktopowych i mobilnych.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Alternatywne formaty:**  
Możesz zamienić `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`, jeśli Twój system docelowy wymaga konkretnego formatu. Pamiętaj, że JPEG wprowadza artefakty kompresji, które mogą obniżyć niezawodność skanowania.

**Oczekiwany wynik:**  
Plik `MacroPdf417.png` będzie zawierał wysokokontrastowy, wielosegmentowy kod PDF417. Po otwarciu powinien wyglądać podobnie do ilustracji poniżej.

![Przykład obrazu kodu kreskowego PDF417](image.png){: .align-center alt="Przykład obrazu kodu kreskowego PDF417 wygenerowanego kodem C#"}

## Pełny kod źródłowy – gotowy do skopiowania i uruchomienia

Poniżej znajduje się kompletny, samodzielny program. Zawiera niezbędne dyrektywy `using`, metodę `Main` oraz komentarze wyjaśniające każdą nieoczywistą linię.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Uruchamianie programu:**  

1. Utwórz nowy projekt konsolowy .NET 6 (lub nowszy).  
2. Dodaj pakiet NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Zamień wygenerowany plik `Program.cs` na powyższy kod.  
4. Dostosuj `outputPath` do folderu, do którego masz prawo zapisu.  
5. Zbuduj i uruchom – konsola potwierdzi lokalizację obrazu.

## Częste pytania i rozwiązywanie problemów

| Question | Answer |
|----------|--------|
| *Co zrobić, jeśli kod kreskowy jest zbyt szeroki dla mojej etykiety?* | Zmniejsz `Columns` lub zwiększ `XDimension.Pixels`, aby zrównoważyć szerokość i czytelność. |
| *Czy muszę ustawiać sumę kontrolną?* | Suma kontrolna jest opcjonalna |

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy PDF417 w C# – Kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Utwórz metadane kodu kreskowego PDF417 w C# – Kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generuj kod kreskowy z tekstem – Pełny przewodnik PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}