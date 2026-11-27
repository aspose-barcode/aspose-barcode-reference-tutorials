---
category: general
date: 2026-11-27
description: Dowiedz się, jak generować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Dostosuj wymiary, ustaw liczbę kolumn i zapisz jako PNG w kilku linijkach kodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: pl
lastmod: 2026-11-27
og_description: Generuj kod kreskowy PDF417 w C# natychmiast. Ten samouczek pokazuje,
  jak skonfigurować wymiary, liczbę kolumn i zapisać wynik jako obraz PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generowanie kodu kreskowego PDF417 w C# – szybki przewodnik z Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak wygenerować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **generować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci zwięzłe, kompleksowe rozwiązanie. Zobaczysz, jak stworzyć kod kreskowy, precyzyjnie dostroić jego rozmiar oraz zapisać wynik do pliku PNG — wszystko przy użyciu biblioteki Aspose.BarCode.

Generowanie kodu PDF417 jest powszechne, gdy trzeba zakodować duże ilości danych do skanowania na urządzeniach mobilnych, kartach pokładowych lub etykietach inwentaryzacyjnych. Po zakończeniu tego tutorialu będziesz mieć gotowy do uruchomienia program konsolowy, który tworzy wysokiej jakości obraz PNG.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Aktualną wersję **Aspose.BarCode for .NET** (pakiet NuGet `Aspose.BarCode`)  
* IDE lub edytor (Visual Studio, VS Code, Rider itp.)  

Kod działa na Windows, Linux i macOS, ponieważ Aspose.BarCode jest wieloplatformowy.

## Krok 1: Utwórz nowy projekt konsolowy

Otwórz terminal i uruchom:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Spowoduje to utworzenie minimalnego projektu C# o nazwie **Pdf417Demo** oraz dodanie zależności `Aspose.BarCode`.

## Krok 2: Napisz kod generujący kod kreskowy

Otwórz **Program.cs** i zamień jego zawartość na następującą:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

* **BarcodeGenerator** – podstawowa klasa tworząca obraz kodu kreskowego. Przekazanie `EncodeTypes.Pdf417` wybiera symbologię PDF417.  
* **XDimension.Pixels** – określa najmniejszą szerokość kreski. Mniejsze wartości zmniejszają obraz; większe wartości poprawiają czytelność przy skanerach o niskiej rozdzielczości.  
* **Pdf417.Columns** – kontroluje liczbę kolumn danych. Więcej kolumn daje krótszy, ale wyższy kod; mniej kolumn sprawia, że kod jest szerszy.  
* **ErrorCorrectionLevel** – wyższe poziomy dodają nadmiarowe dane, zwiększając tolerancję na uszkodzenia kosztem rozmiaru.  
* **Save(..., BarCodeImageFormat.Png)** – zapisuje obraz na dysku w formacie PNG, bezstratnym formacie idealnym do dalszego przetwarzania lub osadzania w dokumentach.

## Krok 3: Zbuduj i uruchom program

W terminalu wykonaj:

```bash
dotnet run
```

Powinieneś zobaczyć:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Plik o nazwie **Pdf417Basic.png** pojawi się w folderze projektu. Po otwarciu zobaczysz wyraźny kod PDF417, który koduje tekst *„Sample text for PDF417 barcode”*.

![Wygenerowany kod PDF417 zapisany jako plik PNG](pdf417-barcode-example.png "Wygenerowany kod PDF417 w formacie PNG")

*Image alt text: screenshot of a generated PDF417 barcode saved as a PNG file, demonstrating the result of the generate PDF417 barcode tutorial.*

## Krok 4: Typowe wariacje i przypadki brzegowe

### Zmiana kodowanych danych

Zastąp drugi argument `BarcodeGenerator` dowolnym ciągiem UTF‑8, np.:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Generator automatycznie dzieli dane na wiersze i kolumny.

### Dostosowanie rozmiaru obrazu bez utraty jakości

Jeśli potrzebujesz większego obrazu do druku, zwiększ `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Obsługa bardzo długich danych wejściowych

PDF417 może zakodować do 1 850 znaków. Dla wyjątkowo długich ciągów możesz zwiększyć liczbę kolumn:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Jeśli zawartość przekroczy maksymalną pojemność, Aspose.BarCode zgłosi `ArgumentException`. Owiń kod generujący w blok try‑catch, aby wyświetlić przyjazny komunikat o błędzie.

### Zapis w innych formatach

Aspose.BarCode obsługuje BMP, JPEG, TIFF i SVG. Zmień format w ten sposób:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Krok 5: Zweryfikuj kod kreskowy

Możesz potwierdzić poprawność kodu, skanując go dowolną aplikacją do odczytu PDF417 (np. aplikacjami na smartfony obsługującymi skanowanie kodów). Zdekodowany tekst powinien być identyczny z ciągiem przekazanym do generatora.

Jeśli skanowanie się nie powiedzie:

* Upewnij się, że obraz nie jest skompresowany (użyj PNG lub bezstratnego SVG).  
* Sprawdź, czy `ErrorCorrectionLevel` jest wystarczająco wysoki dla docelowego środowiska.  
* Zweryfikuj, czy wymiary kodu są odpowiednie dla rozdzielczości skanera.

## Podsumowanie

Teraz wiesz, jak **generować kod kreskowy PDF417** w C# przy użyciu Aspose.BarCode, dostosowywać jego wymiary, ustawiać liczbę kolumn i eksportować wynik jako obraz PNG. To podejście sprawdza się w wielu scenariuszach, od mobilnego biletowania po zarządzanie zapasami.

Następnie możesz zbadać:

* **Odczyt** kodu PDF417 przy użyciu `BarCodeReader`.  
* Generowanie innych symbologii, takich jak QR Code lub DataMatrix.  
* Osadzanie pliku PNG w PDF‑ach, raportach lub stronach internetowych.  

Śmiało eksperymentuj z różnymi poziomami korekcji błędów, formatami obrazu i ładunkami danych, aby dopasować rozwiązanie do potrzeb projektu. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde z nich zawiera kompletny, działający kod wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to generate PDF417 barcode in C# with Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [How to generate PDF417 barcode and render it as PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}