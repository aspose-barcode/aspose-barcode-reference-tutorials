---
category: general
date: 2026-11-27
description: Tworzenie obrazu kodu kreskowego w C# i zapisywanie go w formacie PNG
  przy użyciu Aspose.BarCode – przewodnik krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: pl
lastmod: 2026-11-27
og_description: Utwórz obraz kodu kreskowego w C# i zapisz go w formacie PNG przy
  użyciu Aspose.BarCode. Postępuj zgodnie z tym samouczkiem, aby krok po kroku wygenerować
  kod Macro PDF417.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Tworzenie obrazu kodu kreskowego i zapisywanie w formacie PNG w C# – kompletny
  przewodnik
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Utwórz obraz kodu kreskowego i zapisz w formacie PNG w C#
url: /pl/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego i zapisz w formacie PNG w C#

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** w aplikacji .NET, ten przewodnik pokaże Ci, jak wygenerować kod Macro PDF417 i **zapisać obraz w formacie PNG** przy użyciu Aspose.BarCode. Otrzymasz kompletny, działający przykład oraz wyjaśnienie każdego ustawienia, abyś mógł dostosować kod do własnych wymagań.

Generowanie kodu kreskowego to nie tylko wywołanie jednej metody; musisz skonfigurować rozmiar modułu, parametry makra oraz format wyjściowy. Po zakończeniu tego samouczka zrozumiesz, dlaczego każde właściwość ma znaczenie, jak radzić sobie z typowymi przypadkami brzegowymi i jak zweryfikować, że plik PNG został zapisany poprawnie.

## Czego będziesz potrzebować

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.6+)
- Aspose.BarCode dla .NET (dostępny przez NuGet: `Install-Package Aspose.BarCode`)
- IDE, takie jak Visual Studio 2022 lub Visual Studio Code
- Uprawnienia zapisu do folderu, w którym zostanie zapisany plik PNG

## Krok 1: Zainicjalizuj generator kodów kreskowych

Pierwszy krok to stworzenie instancji `BarcodeGenerator` określającej symbologię `EncodeTypes.MacroPdf417` oraz tekst, który chcesz zakodować.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Dlaczego to jest ważne:**  
`EncodeTypes.MacroPdf417` informuje bibliotekę, że ma używać wariantu makro PDF417, który obsługuje segmentację pliku i dodatkowe metadane. Konstruktor przyjmuje również tekst czytelny dla człowieka, który zostanie zakodowany w kodzie kreskowym.

## Krok 2: Zdefiniuj rozmiar modułu (wymiar X)

Wymiar X kontroluje szerokość pojedynczego modułu kodu kreskowego (najmniejszego elementu czarno‑białego). Wartość `2` piksele dobrze sprawdza się przy wyświetlaniu PNG na ekranie.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktyczna wskazówka:**  
Jeśli planujesz drukować kod kreskowy, zwiększ wartość w pikselach (np. `4` lub `5`), aby uniknąć rozmytego wydruku na drukarkach o niskiej rozdzielczości.

## Krok 3: Skonfiguruj parametry makra PDF417

Macro PDF417 dodaje kilka opcjonalnych pól, które pomagają zidentyfikować plik źródłowy, kolejność segmentów oraz sprawdzić integralność. Poniżej pełny zestaw typowych parametrów; możesz pominąć te, które nie są potrzebne.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Dlaczego te pola są przydatne:**  

| Parametr | Cel |
|-----------|-----|
| `Columns` | Kontroluje szerokość kodu; mniejsza liczba kolumn powoduje wyższy kod. |
| `MacroPdf417FileID` | Unikalny identyfikator łączący wszystkie segmenty. |
| `MacroPdf417SegmentID` | Pozycja tego segmentu w całym pliku. |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów; wymagana do odtworzenia. |
| `MacroPdf417FileName` | Czytelna nazwa, którą mogą wyświetlać aplikacje skanujące. |
| `MacroPdf417Checksum` | Pomaga odbiorcom zweryfikować integralność danych (CCITT‑16). |
| `MacroPdf417FileSize` | Opcjonalna wskazówka rozmiaru oryginalnego pliku. |
| `MacroPdf417TimeStamp` | Znacznik czasu utworzenia oryginalnego pliku. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadane do routingu lub własności. |
| `MacroPdf417Terminator` | Wskazuje, czy jest to ostatni segment (`Set`) czy pośredni (`Unset`). |

**Przypadek brzegowy:** Jeśli generujesz kod kreskowy składający się z jednego segmentu, ustaw `MacroPdf417SegmentsCount` na `1` i `MacroPdf417Terminator` na `Unset`. Biblioteka automatycznie pominie pola związane z segmentami, które nie mają zastosowania.

## Krok 4: Zapisz wygenerowany kod kreskowy jako obraz PNG

Na koniec wywołaj `Save` z ścieżką pliku i wartością wyliczenia `BarCodeImageFormat.Png`. Metoda zapisuje obraz na dysku w bezstratnym formacie PNG.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Dlaczego PNG?**  
PNG zachowuje dokładne wartości pikseli, co jest niezbędne dla skanerów kodów kreskowych, które polegają na ostrym kontraście. Kompresja JPEG może wprowadzać artefakty, które psują wzór kodu.

### Weryfikacja wyniku

Po uruchomieniu programu powinieneś zobaczyć plik o nazwie `ExtPDF417Meta.png` w folderze wykonywania. Otworzenie go dowolnym przeglądarką obrazów wyświetli gęsty, prostokątny kod kreskowy. Poprawność możesz zweryfikować, skanując obraz mobilnym czytnikiem kodów, który obsługuje PDF417 macro; aplikacja zazwyczaj pokaże wbudowane metadane (ID pliku, numer segmentu itp.).

## Typowe pułapki i jak ich uniknąć

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| Kod kreskowy jest rozmyty | Zbyt mały wymiar X dla wybranej DPI | Zwiększ `XDimension.Pixels` lub renderuj przy wyższej DPI (`generator.Parameters.ImageResolution`). |
| Skaner zgłasza „checksum error” | Nieprawidłowa wartość `MacroPdf417Checksum` | Pozwól Aspose obliczyć sumę kontrolną automatycznie, pomijając właściwość, lub upewnij się, że wartość odpowiada algorytmowi CCITT‑16. |
| Plik PNG jest pusty lub nie został utworzony | Nieprawidłowa ścieżka wyjściowa lub brak uprawnień do zapisu | Użyj `Path.Combine` z dobrze znanym folderem zapisu (np. `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Pola makra są ignorowane | `EncodeTypes` ustawiony na zwykły `Pdf417` zamiast `MacroPdf417` | Zweryfikuj, że w konstruktorze użyto `EncodeTypes.MacroPdf417`. |

## Pełny, działający przykład

Poniżej znajduje się kompletny program, który możesz skopiować do aplikacji konsolowej. Kompiluje się z .NET 6.0 i generuje opisany wyżej plik PNG.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Oczekiwany wynik (konsola):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Otworzenie `ExtPDF417Meta.png` pokazuje wyraźny kod Macro PDF417 gotowy do skanowania.

## Kolejne kroki

- **Zmień format obrazu** – zamień `BarCodeImageFormat.Png` na `Jpeg` lub `Bmp`, jeśli potrzebujesz innego typu pliku. Pamiętaj, że JPEG wprowadza artefakty kompresji, które mogą wpływać na niezawodność skanowania.
- **Dostosuj rozdzielczość** – użyj

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}