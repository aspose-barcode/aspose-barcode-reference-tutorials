---
category: general
date: 2026-07-18
description: Generuj mikro‑kod PDF417 przy użyciu Aspose.BarCode dla .NET – przewodnik
  krok po kroku obejmujący kolumny, wiersze i wyjście PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: pl
lastmod: 2026-07-18
og_description: Generuj mikro kod PDF417 natychmiast przy użyciu Aspose.BarCode dla
  .NET. Dowiedz się, jak kontrolować kolumny, wiersze i zapisywać jako PNG w kilka
  minut.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Wygeneruj mikro‑kod PDF417 – pełny samouczek C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generowanie mikro‑kodu PDF417 w C# – Kompletny przewodnik
url: /pl/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie mikro‑PDF417 w C# – Kompletny przewodnik

Zastanawiałeś się kiedyś, jak **generować mikro‑pdf417 kod kreskowy** bezpośrednio z aplikacji C#? Nie jesteś jedyny. Niezależnie od tego, czy oznaczasz inwentarz, kodujesz krótkie adresy URL, czy budujesz własne rozwiązanie skanowania, opanowanie tego małego, a jednocześnie potężnego kodu 2‑D może zaoszczędzić Ci wiele kłopotów.

W tym samouczku przejdziemy przez rzeczywisty przykład używający **Aspose.BarCode for .NET**, pokazując, jak dostosować kolumny, wiersze i rozmiar modułu, a następnie zapisać wynik do pliku PNG. Po zakończeniu będziesz mieć gotową do uruchomienia aplikację konsolową, która generuje trzy różne obrazy kodów kreskowych — bez żadnych tajemnic.

## Czego będziesz potrzebować

- .NET 6 lub nowszy (kod działa także na .NET Framework 4.7+)
- Visual Studio 2022 (lub dowolne IDE C#, które preferujesz)
- Pakiet NuGet **Aspose.BarCode** (`Aspose.BarCode`)
- Zapisywalny folder na dysku dla wygenerowanych plików PNG

Jeśli już masz te elementy, świetnie — zanurzmy się.

## Krok 1: Utwórz projekt i zainstaluj Aspose.BarCode

Najpierw utwórz nowy projekt konsolowy:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Pro tip:** Uruchom `dotnet restore` po dodaniu pakietu, aby upewnić się, że wszystkie zależności zostały rozwiązane.

Teraz otwórz `Program.cs`. Zaczniemy od zaimportowania niezbędnych przestrzeni nazw:

```csharp
using System;
using Aspose.BarCode.Generation;
```

## Krok 2: Zainicjalizuj generator MicroPdf417

Sercem operacji jest obiekt `BarcodeGenerator`. Przekazujemy mu typ kodowania **MicroPdf417** oraz tekst, który chcemy zakodować — w naszym przypadku słowo „ASPOSE”.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Dlaczego `MicroPdf417`? W porównaniu z pełnowymiarowym PDF417, wersja mikro mieści więcej danych w mniejszej przestrzeni, co jest idealne dla etykiet o ograniczonej powierzchni.

## Krok 3: Dostosuj rozmiar modułu (wymiar X)

Rozmiar modułu określa, ile pikseli zajmuje każdy mały kwadrat kodu kreskowego. Wartość **2 piksele** daje wyraźny, czytelny obraz bez nadmiernego zwiększania rozmiaru pliku.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Note:** Jeśli potrzebujesz większego kodu kreskowego do skanowania z większej odległości, zwiększ tę liczbę do 3 lub 4.

## Krok 4: Generuj kody kreskowe z różnymi konfiguracjami kolumn/wierszy

### 4.1 Dwie kolumny, automatycznie obliczane wiersze

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Sześć wierszy, automatycznie obliczane kolumny

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Cztery kolumny × osiem wierszy (w pełni określone)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Każde wywołanie `Save` zapisuje plik PNG do katalogu roboczego projektu. Śmiało zmień ścieżkę (`"YOUR_DIRECTORY/..."`) na coś w stylu `Path.Combine(Environment.CurrentDirectory, "output")`, jeśli wolisz dedykowany folder.

## Krok 5: Pełny działający przykład

Łącząc wszystko razem, oto kompletny program gotowy do skopiowania i wklejenia:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu tworzy trzy pliki PNG:

| Nazwa pliku | Przybliżone wymiary (px) | Wskazówka wizualna |
|-------------|--------------------------|--------------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Wąski, wyższy kod kreskowy |
| `MicroPdf417Rows6.png` | 120 × 180 | Szerszy, niższy kod kreskowy |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Kwadratowy, zrównoważony układ |

Otwórz dowolny z nich w przeglądarce obrazów — zobaczysz wyraźny **Micro PDF417** gotowy do skanowania.

## Częste pytania i przypadki brzegowe

- **Co zrobić, jeśli folder wyjściowy nie istnieje?**  
  Wywołaj `Directory.CreateDirectory(path)` przed pierwszym `Save`, aby uniknąć `DirectoryNotFoundException`.

- **Czy mogę zmienić format obrazu?**  
  Oczywiście. Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`, w zależności od potrzeb.

- **Czy istnieje limit długości tekstu?**  
  MicroPdf417 może zakodować do 1 KB danych, ale praktyczne limity zależą od wybranej liczby wierszy/kolumn. Jeśli napotkasz błąd, zwiększ liczbę wierszy lub kolumn.

- **Jak wstawić kod kreskowy do pliku PDF?**  
  Użyj Aspose.Pdf, aby wstawić wygenerowany PNG, lub przełącz na `BarCodeImageFormat.Pdf` dla bezpośredniego wyjścia PDF.

## Porady profesjonalne dla generowania kodów kreskowych w C#

1. **Cache the generator** gdy potrzebujesz wielu kodów kreskowych z tymi samymi ustawieniami — zmienia się tylko tekst, co oszczędza cykle CPU.  
2. **Fine‑tune error correction** za pomocą `generator.Parameters.Barcode.Pdf417.ErrorLevel`, jeśli środowisko skanowania jest zaszumione.  
3. **Test with real scanners** już na wczesnym etapie. Niektóre ręczne urządzenia mają trudności z bardzo gęstymi mikro‑kodami; dostosowanie `XDimension` może zrobić dużą różnicę.

## Zakończenie

Teraz wiesz, jak **generować mikro‑pdf417 kod kreskowy** przy użyciu **Aspose.BarCode for .NET**, manipulować **kolumnami MicroPdf417** i **wierszami MicroPdf417**, oraz zapisywać wynik jako pliki PNG — wszystko z jednej schludnej aplikacji konsolowej C#. Eksperymentuj z różnymi rozmiarami modułu, poziomami korekcji błędów lub nawet kolorowym wyjściem, aby dopasować je do potrzeb projektu.

Następnie możesz zgłębić **generowanie kodów kreskowych w C#** dla innych symbologii, takich jak QR, Code128 czy DataMatrix, albo wstawiać obrazy bezpośrednio do PDF‑ów przy pomocy Aspose.Pdf. Nie ma granic, gdy masz już solidne podstawy.

Miłego kodowania i niech Twoje skany zawsze będą wolne od błędów!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z krok‑po‑kroku wyjaśnieniami, pomagając Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak utworzyć kod kreskowy – kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Utwórz obraz kodu DotCode – wiersze i kolumny (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generowanie kodu DataMatrix – przewodnik profesjonalny z Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}