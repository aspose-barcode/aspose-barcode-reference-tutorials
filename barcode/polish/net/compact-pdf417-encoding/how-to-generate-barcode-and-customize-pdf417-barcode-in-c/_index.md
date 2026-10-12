---
category: general
date: 2026-09-19
description: Jak generować kod kreskowy w C# krok po kroku. Dowiedz się, jak dostosować
  ustawienia kodu PDF417 i stworzyć obraz kodu kreskowego, którego programiści C#
  mogą używać od razu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: pl
lastmod: 2026-09-19
og_description: Jak generować kod kreskowy w C# ze szczegółowymi instrukcjami. Dostosuj
  parametry kodu PDF417 i utwórz obraz kodu kreskowego, którego projekty C# mogą używać
  już dziś.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Jak generować kod kreskowy i dostosować kod PDF417 w C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Jak generować kod kreskowy i dostosować kod PDF417 w C#
url: /pl/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy i dostosować kod PDF417 w C#

Jeśli potrzebujesz **how to generate barcode** w aplikacji .NET, ten tutorial pokazuje kompletną, gotową do uruchomienia rozwiązanie. Nauczysz się, jak dostosować wymiary kodu PDF417, wybrać liczbę kolumn i w końcu **create barcode image C#** projekty mogą osadzić bezpośrednio.

Generowanie kodu kreskowego nie wymaga skomplikowanego procesu budowania. Po zakończeniu tego przewodnika będziesz mieć plik PNG zawierający kod MicroPDF417, który odpowiada dokładnemu rozmiarowi i rozdzielczości, jakiej potrzebujesz.

## Prerequisites

You should have the following installed before you start:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.6+)
* Visual Studio 2022 (lub dowolny edytor C#, którego preferujesz)
* Pakiet NuGet Aspose.BarCode dla .NET – zainstaluj za pomocą  
  `dotnet add package Aspose.BarCode`

No additional external tools are required.

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Create a new console project and add the Aspose.BarCode reference.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Open `Program.cs` and add the required `using` directives:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

These namespaces expose the classes that let you **how to generate barcode** and control PDF417‑specific options.

## Krok 2: Zainicjalizuj generator MicroPDF417 z żądanym tekstem

The first line creates a `BarcodeGenerator` instance configured for the MicroPDF417 symbology. The constructor takes the encoding type and the data string you want to encode.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Dlaczego to ważne:** MicroPDF417 jest kompaktową odmianą pełnego standardu PDF417, idealną dla małych etykiet lub ekranów mobilnych. Inicjalizacja generatora z odpowiednim `EncodeTypes` zapewnia, że biblioteka używa właściwego algorytmu kodowania.

## Krok 3: Dostosuj wymiar X (szerokość modułu) dla wyższej rozdzielczości

The X‑dimension controls the width of a single barcode module (the smallest black or white bar). Setting it to a low pixel value yields a higher‑resolution image.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to ważne:** Większy wymiar X ułatwia odczyt kodu przez skanery o niskiej rozdzielczości, podczas gdy mniejsza wartość pozwala zmieścić więcej danych w ograniczonej przestrzeni. Dostosuj tę wartość w zależności od środowiska skanowania.

## Krok 4: Określ liczbę kolumn, aby kontrolować rozmiar kodu

MicroPDF417 pozwala na 1‑4 kolumny. Więcej kolumn daje krótszy, szerszy kod; mniej kolumn tworzy wyższy, węższy kod.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Dlaczego to ważne:** Wybranie odpowiedniej liczby kolumn pozwala dopasować kod do konkretnego elementu UI lub wydrukowanej etykiety bez ręcznego skalowania.

## Krok 5: Zapisz kod kreskowy jako obraz PNG

Finally, write the generated barcode to disk. PNG preserves lossless quality, which is important for crisp scanning.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

If the target directory does not exist, the `Save` method throws an `ArgumentException`. You can guard against this with a simple check:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Pełny kod źródłowy

Putting the pieces together, here is the complete, runnable program:

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Running this program produces a file named **MicroPdf417.png** that looks like the screenshot below (image omitted for brevity). The barcode encodes the text *Sample* and respects the X‑dimension and column settings you defined.

## Dostosowywanie innych opcji PDF417

While this guide focuses on **customize pdf417 barcode** parameters that affect size, Aspose.BarCode offers many additional settings you might need:

| Property | Cel | Typowe wartości |
|----------|-----|-----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Kontroluje liczbę wierszy (wysokość) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Ustawia poziom korekcji błędów (wyższy = bardziej tolerancyjny) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Generuje przycięty kod kreskowy (bez wzoru stop) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Wybiera kompaktowanie numeryczne, tekstowe lub bajtowe | `CompactionModes.Numeric`, etc. |

**Pro tip:** Kiedy potrzebujesz kodu, który pasuje do stałej szerokości, zacznij od zwiększenia `Columns` i zmniejszenia `XDimension`. Jeśli skaner zgłasza brakujące symbole, podnieś `ErrorLevel`, aby zwiększyć redundancję.

## Obsługa przypadków brzegowych

* **Tekst za długi dla MicroPDF417:** Wariant Micro obsługuje do 1 KB danych. Jeśli Twój ciąg przekracza ten limit, przełącz się na pełną symbologię `Pdf417`, zmieniając `EncodeTypes.MicroPdf417` na `EncodeTypes.Pdf417`.
* **Nieobsługiwany format obrazu:** `BarCodeImageFormat` obsługuje także `Jpeg`, `Bmp` i `Gif`. Wybierz format pasujący do Twojego łańcucha przetwarzania.
* **Ścieżki wieloplatformowe:** Używaj `Path.Combine` zamiast twardo zakodowanych backslashy przy docelowych systemach Linux lub macOS.

## Weryfikacja kodu kreskowego

You can verify the generated image with any standard barcode scanner app (mobile or desktop). The scanner should return the original text **Sample**. If it fails:

1. Sprawdź, czy wymiar X nie jest ustawiony poniżej 1 piksela (niektóre skanery nie potrafią rozróżnić modułów poniżej piksela).
2. Upewnij się, że plik wyjściowy nie jest uszkodzony — uruchom program ponownie i porównaj rozmiary plików.
3. Zwiększ `ErrorLevel`, aby poprawić tolerancję.

## Zakończenie

You now know **how to generate barcode** in C# using Aspose.BarCode, how to **customize pdf417 barcode** dimensions and column count, and how to **create barcode image C#** projects can embed directly. The complete example demonstrates a practical workflow from project setup to final PNG output.

Next, explore other symbologies such as QR, Code128, or DataMatrix by swapping the `EncodeTypes` enum value. Adjusting additional parameters like `Resolution` or `Margin` lets you fine‑tune every barcode for your specific application.

Happy coding, and let your barcodes empower your next automation project!

## Co powinieneś nauczyć się dalej?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}