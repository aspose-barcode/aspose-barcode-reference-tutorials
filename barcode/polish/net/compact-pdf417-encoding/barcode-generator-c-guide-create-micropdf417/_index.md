---
category: general
date: 2026-09-29
description: Przewodnik po generatorze kodów kreskowych w C# pokazuje, jak wygenerować
  kod MicroPdf417, zmienić wymiary, ustawić kolumny i dostosować rozmiar kodu kreskowego
  w kilku linijkach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: pl
lastmod: 2026-09-29
og_description: Poradnik generatora kodów kreskowych w C# pokazuje, jak wygenerować
  kod MicroPdf417, zmienić wymiary, ustawić kolumny i dostosować rozmiar kodu kreskowego
  w kilku linijkach.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Generator kodów kreskowych C# – tworzenie i dostosowywanie MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Generator kodów kreskowych C#: przewodnik – tworzenie MicroPdf417'
url: /pl/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przewodnik po generatorze kodów kreskowych C#: tworzenie MicroPdf417

Jeśli potrzebujesz **barcode generator C#** dla swojego projektu .NET, ten samouczek poprowadzi Cię krok po kroku przez tworzenie kodu MicroPdf417 od podstaw. Dowiesz się **jak generować kod kreskowy**, zmieniać wymiary, ustawiać kolumny oraz **dostosowywać rozmiar kodu kreskowego** bez wysiłku.

MicroPdf417 to kompaktowa symbologia 2‑D, która sprawdza się przy etykietowaniu małych części, biletów czy tagów inwentaryzacyjnych. Po zakończeniu tego przewodnika będziesz mieć kompletną, uruchamialną aplikację konsolową, która zapisuje obraz PNG kodu kreskowego, oraz zrozumiesz, jak każdy parametr wpływa na ostateczny rozmiar.

## Prerequisites

Zanim zaczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
* IDE kompatybilne z C# (Visual Studio, VS Code, Rider itp.)
* Pakiet NuGet **GroupDocs.Barcode** – zainstaluj go za pomocą  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Nie są wymagane żadne dodatkowe narzędzia; biblioteka obsługuje kodowanie, renderowanie i zapisywanie plików.

## Barcode generator C#: initializing the generator

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` i określenie symbologii (`EncodeTypes.MicroPdf417`) wraz z danymi, które chcesz zakodować.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Why this matters:**  
`BarcodeGenerator` jest punktem wejścia dla wszystkich operacji związanych z kodami kreskowymi. Konstruktor wiąże wybraną **EncodeTypes** (MicroPdf417) z surowym ciągiem danych. Biblioteka automatycznie obsługuje znaki Unicode, takie jak „Å” i „©”, więc nie potrzebujesz dodatkowej logiki kodowania.

## How to change dimensions of the barcode

Czytelność kodu kreskowego zależy w dużej mierze od szerokości modułu (wymiar X). Ustawienie większej liczby pikseli powoduje, że paski są szersze, a obraz łatwiejszy do zeskanowania, szczególnie na wyświetlaczach o niskiej rozdzielczości.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explanation:**  
`XDimension.Pixels` kontroluje szerokość pojedynczego modułu kodu kreskowego. Domyślnie jest to 1 piksel, co może wyglądać na cienkie na monitorach o wysokiej rozdzielczości DPI. Zwiększenie do 2 pikseli podwaja całkowitą szerokość bez wpływu na zakodowane dane.

**Tip:** Jeśli planujesz drukować kod kreskowy w 300 dpi, wartość 3 lub 4 piksele często daje najlepszy kompromis między rozmiarem a niezawodnością skanowania.

## How to set columns for size control

MicroPdf417 pozwala określić liczbę kolumn (do 4). Mniej kolumn daje wyższy kod kreskowy; więcej kolumn sprawia, że jest szerszy, ale niższy. Dostosowanie tej wartości jest podstawowym sposobem **customize barcode size**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Why this works:**  
Właściwość `Pdf417.Columns` jest współdzielona przez wszystkie symbologie oparte na PDF417, w tym MicroPdf417. Ustawienie maksymalnej wartości (4) rozkłada dane na najszerszy możliwy układ, zmniejszając ogólną wysokość. Jeśli potrzebujesz bardziej kompaktowej wysokości, zmniejsz liczbę kolumn do 2 lub 3.

**Edge case:** Gdy ciąg danych jest długi, biblioteka może automatycznie zwiększyć liczbę wierszy, aby pomieścić zawartość, niezależnie od liczby kolumn. Trzymaj ładunek poniżej 50 znaków, aby uzyskać przewidywalny rozmiar.

## Customize barcode size for different outputs

Poza wymiarem X i kolumnami możesz wpływać na ostateczny rozmiar obrazu, wybierając odpowiedni format obrazu i DPI. PNG jest bezstratny, idealny do wyświetlania w sieci, podczas gdy BMP lub TIFF mogą być lepsze do wysokiej jakości druku.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Jeśli potrzebujesz wyższego DPI, możesz ustawić je ręcznie:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Result:** Zapisany plik PNG zawiera wyraźny kod MicroPdf417, który respektuje skonfigurowane wymiary. Otwórz plik w dowolnej przeglądarce obrazów, aby zweryfikować wizualny rozmiar.

### Expected output

Uruchomienie programu tworzy plik o nazwie **MicroPdf417.png** (lub **MicroPdf417_300dpi.png**, jeśli ustawiłeś DPI). Kod kreskowy będzie wyglądał podobnie do ilustracji poniżej:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Barcode generator C# output showing a MicroPdf417 PNG*

Skanowanie obrazu standardowym czytnikiem 2‑D zwróci oryginalny ciąg `Åspóse.Barcóde©`.

## Full source code for quick copy‑paste

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Skopiuj kod do nowego projektu konsolowego, przywróć pakiety NuGet i uruchom `dotnet run`. Konsola potwierdzi lokalizację obrazu, a wygenerowany kod kreskowy pojawi się w folderze projektu.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| **What if the barcode looks blurry?** | Increase `XDimension.Pixels` or the DPI (`Parameters.Image.DpiX/Y`). Both enlarge the modules and improve visual fidelity. |
| **Can I use a different image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff`. PNG remains the safest choice for lossless quality. |
| **My data contains emojis—will they encode?** | MicroPdf417 supports UTF‑8, so most emojis encode correctly. If you encounter errors, verify that the string is properly normalized (`System.Text.Encoding.UTF8`). |
| **How do I generate other symbologies?** | Change `EncodeTypes.MicroPdf417` to any other value from `EncodeTypes` (


## What Should You Learn Next?

Następne samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}