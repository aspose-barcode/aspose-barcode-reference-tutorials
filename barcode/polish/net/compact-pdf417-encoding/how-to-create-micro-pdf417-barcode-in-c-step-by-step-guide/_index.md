---
category: general
date: 2026-08-22
description: Dowiedz się, jak stworzyć mikro kod kreskowy PDF417 w C# i wygenerować
  obraz PNG kodu kreskowego. Zawiera ustawianie wymiarów kodu kreskowego oraz zapisywanie
  pliku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: pl
lastmod: 2026-08-22
og_description: Utwórz mikrokod PDF417 w C# i wyeksportuj go jako PNG. Skorzystaj
  z tego przewodnika, aby ustawić wymiary kodu kreskowego i szybko wygenerować obraz
  kodu.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Utwórz mikro kod kreskowy PDF417 w C# – pełny samouczek programistyczny
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Jak stworzyć mikro kod kreskowy PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć mikro‑kod PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć mikro‑kod PDF417** dla systemu biletowego, etykiety inwentarzowej lub skanowania mobilnego, ten tutorial pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny program w C#, który generuje plik PNG z kodem kreskowym, nauczysz się ustawiać wymiary kodu oraz zrozumiesz każdą opcję konfiguracji.

Po zakończeniu tego przewodnika będziesz w stanie wygenerować wysokiej rozdzielczości obraz kodu kreskowego, dostosować wymiar X, wybrać liczbę kolumn i zapisać wynik jako plik PNG — wszystko przy użyciu kilku linii kodu.

## Czego będziesz potrzebować

- .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
- Visual Studio 2022 lub dowolne IDE kompatybilne z C#
- Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolna biblioteka obsługująca `EncodeTypes.MicroPdf417`)
- Podstawowa znajomość składni C#

> **Pro tip:** Darmowa edycja community Aspose.BarCode wystarczy do rozwoju i testów. W wersji produkcyjnej należy uzyskać licencję, aby usunąć znak wodny oceny.

## Krok 1: Zainstaluj bibliotekę kodów kreskowych

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Spowoduje to dodanie zestawu `Aspose.BarCode`, który udostępnia klasę `BarcodeGenerator` używaną do **create barcode image C#** aplikacji.

## Krok 2: Zainicjuj generator – utwórz mikro‑kod PDF417

Pierwsza wykonywalna linia tworzy instancję `BarcodeGenerator` skonfigurowaną dla symboliki Micro PDF417 i podaje dane, które mają zostać zakodowane.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Dlaczego to ważne*: Enum `EncodeTypes.MicroPdf417` informuje bibliotekę, że ma używać kompaktowej wersji PDF417, co jest idealne dla małych etykiet i ekranów mobilnych.

## Krok 3: Jak ustawić wymiary kodu kreskowego w C#

Dostrajanie szerokości modułu (wymiar X) kontroluje gęstość wizualną kodu. Mniejsza wartość daje ostrzejszy obraz, większa ułatwia skanowanie z większej odległości.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Dlaczego warto ustawiać wymiary**: Bez zmiany wymiaru X domyślna wartość może spowodować, że kod będzie wyglądał na rozmyty przy renderowaniu w wysokim DPI. Ustawienie go na 2 piksele to dobre wyważenie dla większości skanowań ekranowych.

## Krok 4: Wybierz liczbę kolumn – kontrola szerokości kodu

Micro PDF417 dopuszcza od 1 do 4 kolumn. Więcej kolumn kompresuje dane w poziomie, zmniejszając ogólną szerokość obrazu.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Przypadek brzegowy*: Jeśli zażądasz 5 kolumn, biblioteka zgłosi `ArgumentOutOfRangeException`. Zawsze pozostawaj w dokumentowanym zakresie.

## Krok 5: Jak wygenerować PNG kodu kreskowego – zapis obrazu

Teraz możesz wyeksportować wygenerowany kod do pliku PNG. PNG zachowuje jakość bezstratną, co jest niezbędne do niezawodnego skanowania.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Po uruchomieniu programu zobaczysz komunikat w konsoli potwierdzający lokalizację pliku. Powstały plik `MicroPdf417.png` wygląda tak:

![Screenshot showing a generated micro PDF417 barcode created with C#](micro-pdf417-example.png "Generated micro PDF417 barcode")

*Tekst alternatywny obrazu*: **micro PDF417 barcode generated in C#** – prezentuje końcowy wynik po zastosowaniu wymiarów i ustawień kolumn.

## Krok 6: Uruchom i zweryfikuj wynik

1. Zbuduj projekt: `dotnet build`.
2. Uruchom: `dotnet run`.
3. Otwórz `MicroPdf417.png` na pulpicie i zeskanuj go aplikacją mobilną do skanowania kodów kreskowych.

Powinieneś zobaczyć odkodowany tekst **„Sample text”**. Jeśli skaner zgłosi błąd, sprawdź ponownie wymiar X i liczbę kolumn – skrajne wartości mogą sprawić, że kod będzie zbyt gęsty dla niektórych urządzeń.

## Typowe warianty i rozwiązywanie problemów

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Potrzeba większego kodu dla drukarek o niskiej rozdzielczości** | Zwiększ `XDimension.Pixels` do 3 lub 4. |
| **Chcesz wyższy kod bez zmiany szerokości** | Ustaw `generator.Parameters.Barcode.Pdf417.Rows` (zakres wierszy 3‑90). |
| **Generowanie wielu kodów w pętli** | Ponownie użyj tej samej instancji `BarcodeGenerator` i zmieniaj tylko `CodeText` przed każdym `Save`. |
| **Zapis jako JPEG zamiast PNG** | Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. |
| **Uruchamianie na .NET Framework 4.7** | Ten sam kod działa; wystarczy odwołać się do odpowiedniego `Aspose.BarCode.dll`. |

## Pełny listing źródłowy (do uruchomienia)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Oczekiwany wynik** – plik PNG o wymiarach 200 × 100 pikseli zawierający wyraźny mikro‑kod PDF417, który dekoduje się jako „Sample text”.

## Podsumowanie

Teraz wiesz, jak **create micro PDF417 barcode** w C#, **set barcode dimensions** oraz **generate a barcode PNG**. Pełny przykład demonstruje każdy niezbędny krok – od instalacji biblioteki po zapis końcowego pliku – dzięki czemu możesz wbudować generowanie kodów kreskowych bezpośrednio w własnych aplikacjach.

Następnie eksploruj pokrewne tematy, takie jak **creating QR codes with Aspose.BarCode**, **customizing colors** czy **embedding barcodes in PDF documents**. Wszystkie te zagadnienia opierają się na tych samych podstawach `BarcodeGenerator`, które omówiliśmy.

Śmiało eksperymentuj z różnymi ciągami danych, liczbą kolumn i wartościami wymiaru X, aby dopasować je do swojego środowiska skanowania. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, pomagające opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}