---
category: general
date: 2026-11-20
description: Dowiedz się, jak generować kod kreskowy PDF417 w C# przy użyciu BarcodeGenerator.
  Ten przewodnik krok po kroku obejmuje wymiar X, ustawienia kolumn oraz eksport do
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: pl
lastmod: 2026-11-20
og_description: Szybko generuj kod kreskowy PDF417 w C#. Postępuj zgodnie z tym przewodnikiem,
  aby ustawić wymiary, kolumny i wyeksportować kod jako obraz PNG.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy PDF417 w C# przy użyciu BarcodeGenerator
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# przy użyciu BarcodeGenerator

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, gotowy do uruchomienia przykład, który ustawia X‑Dimension, wybiera liczbę kolumn i zapisuje wynik jako obraz PNG.

Generowanie kodu kreskowego PDF417 jest powszechne, gdy trzeba zakodować dużą ilość danych — takich jak prawo jazdy, karta pokładowa czy rekord inwentarza — w kompaktowy, maszynowo‑czytelny obraz. W tym samouczku używamy klasy **BarcodeGenerator** z biblioteki Aspose.BarCode, ale koncepcje mają zastosowanie do każdej biblioteki obsługującej PDF417.

Po zakończeniu tego artykułu będziesz w stanie:

* Zainicjować `BarcodeGenerator` do kodowania PDF417.  
* Dostosować rozmiar modułu przy użyciu **set XDimension pixels**.  
* Kontrolować układ za pomocą **configure PDF417 columns**.  
* **Zapisz kod kreskowy jako PNG** do użycia na stronach internetowych, w aplikacjach mobilnych lub materiałach drukowanych.  

> **Wymagania wstępne**  
> * .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+).  
> * Odwołanie do pakietu NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Podstawowa znajomość C# i Visual Studio (lub dowolnego ulubionego IDE).  

---

## Jak wygenerować kod kreskowy PDF417 w C#

Rdzeń rozwiązania to krótki proces czterech kroków. Każdy krok jest opakowany w dedykowaną metodę, abyś mógł ponownie wykorzystać logikę w większych projektach.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Dlaczego te cztery kroki są ważne

1. **Zainicjowanie generatora** – `BarcodeGenerator` łączy wybraną symbologię (`EncodeTypes.Pdf417`) z danymi, które chcesz zakodować. Bez tego obiektu nie możesz uzyskać dostępu do dalszej konfiguracji.  
2. **Set X‑Dimension** – PDF417 składa się z małych prostokątnych modułów. Zmiana `XDimension.Pixels` pozwala kontrolować gęstość wizualną kodu, co jest kluczowe dla czytelności na wyświetlaczach lub drukarkach o niskiej rozdzielczości.  
3. **Configure columns** – PDF417 może układać swoje codewords w zmiennej liczbie kolumn. Mniej kolumn daje wyższy kod kreskowy, natomiast więcej kolumn go spłaszcza. Dostosuj to do dostępnej przestrzeni, w której obraz będzie umieszczony.  
4. **Save as PNG** – PNG jest formatem bezstratnym, zachowującym ostre krawędzie niezbędne do dokładnego skanowania. Można również wybrać JPEG lub BMP, ale PNG jest najbezpieczniejszym domyślnym wyborem.  

---

## Konfiguracja wymiarów kodu kreskowego (X‑Dimension)

Krok **set XDimension pixels** bezpośrednio wpływa na to, jak skanery interpretują kod kreskowy. Jeśli moduł jest zbyt mały, kamery o niskiej jakości mogą przegapić pojedyncze paski; jeśli jest zbyt duży, kod kreskowy może stać się niepotrzebnie duży.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Przetestuj wygenerowany obraz w zamierzonym rozmiarze wydruku. Dla druku o wysokiej gęstości (300 dpi lub więcej) wartość `1` lub `2` sprawdza się dobrze. Dla wyświetlania na ekranie przy 96 dpi, `2`–`3` zapewnia wyraźny wygląd.

---

## Ustaw kolumny PDF417

Krok **configure PDF417 columns** pozwala określić kształt kodu kreskowego.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Kiedy zmienić liczbę kolumn

| Kolumny | Kształt wynikowy | Typowe zastosowanie |
|---------|------------------|----------------------|
| 1–3     | Wysoki, wąski    | Etykiety o ograniczonej szerokości |
| 4–9     | Zrównoważony     | Skanowanie ogólnego przeznaczenia |
| 10+     | Szeroki, niski   | Duże oznakowanie lub grafika internetowa |

Jeśli ładunek danych przekracza domyślną pojemność, biblioteka automatycznie dodaje dodatkowe wiersze, ale nadal możesz wpływać na proporcje, dostosowując liczbę kolumn.

---

## Eksport kodu kreskowego do PNG

Zapisanie kodu kreskowego jako obrazu PNG jest proste:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Dlaczego PNG?**  
* Bezstratna kompresja zachowuje ostre krawędzie potrzebne czytnikom kodów kreskowych.  
* PNG obsługuje przezroczystość, co może być przydatne, jeśli później nałożysz kod kreskowy na kolorowe tło.

Jeśli potrzebujesz innego formatu, zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Svg` — API automatycznie obsłuży konwersję.

---

## Typowe problemy i rozwiązywanie

| Problem | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------|-----|
| Kod kreskowy jest rozmyty | X‑Dimension zbyt mały dla rozdzielczości wyjściowej | Zwiększ `XDimension.Pixels` do 3 lub 4. |
| Skaner nie może odczytać kodu | Znaki Unicode nie są obsługiwane przez wybraną czcionkę | Upewnij się, że czcionka biblioteki obsługuje te znaki, lub zamień je na odpowiedniki ASCII. |
| Plik wyjściowy nie został utworzony | Nieprawidłowa ścieżka lub brak uprawnień do zapisu | Użyj ścieżki bezwzględnej i sprawdź dostęp do zapisu w folderze. |
| Zbyt wiele wierszy, kod kreskowy jest wysoki | Liczba kolumn zbyt niska w stosunku do długości danych | Zwiększ `Pdf417.Columns` do wyższej liczby (np. 6). |

---

## Pełny działający przykład – podsumowanie

Poniżej znajduje się **kompletny program**, który możesz skopiować i wkleić do nowego projektu konsolowego. Nie jest wymagany dodatkowy kod poza instrukcjami `using` i pakietem Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Oczekiwany wynik:** Plik o nazwie `Pdf417Basic.png` zawierający wyraźny kod kreskowy PDF417, który koduje ciąg znaków `Åspóse.Barcóde©`. Po otwarciu obraz powinien przedstawiać serię ułożonych w stos prostokątnych pasków z wyższą gęstością po lewej stronie (z powodu układu trzech kolumn).

---

## Zakończenie

Teraz wiesz, jak **wygenerować kod kreskowy PDF417** w C# przy użyciu klasy `BarcodeGenerator`. Samouczek omówił inicjalizację generatora, **set XDimension pixels**, **configure PDF417 columns** oraz **save barcode as PNG** — niezbędne kroki dla każdego gotowego do produkcji przepływu pracy z kodami kreskowymi.

Od teraz możesz:

* Eksperymentować z różnymi `EncodeTypes` (np. QR, Code128).  
* Dodać poziomy korekcji błędów za pomocą `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Renderować kod kreskowy bezpośrednio do `MemoryStream` dla interfejsów API webowych.  

Śmiało dostosuj kod do własnego projektu i podziel się wynikami w komentarzach lub na Stack Overflow, używając tagu `#pdf417`. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generowanie kodu kreskowego PDF417 jako PNG w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak wygenerować kod kreskowy PDF417 w C# z niestandardowymi wymiarami](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}