---
category: general
date: 2026-09-19
description: Jak generować kod kreskowy przy użyciu Aspose w C# – krok po kroku przewodnik,
  jak szybko i niezawodnie tworzyć kod kreskowy za pomocą Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: pl
lastmod: 2026-09-19
og_description: Jak generować kod kreskowy przy użyciu Aspose w C#. Postępuj zgodnie
  z tym przewodnikiem, aby utworzyć kod kreskowy przy użyciu Aspose, skonfigurować
  MacroPdf417 i zapisać jako PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Jak wygenerować kod kreskowy przy użyciu Aspose – kompletny przewodnik C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Jak wygenerować kod kreskowy przy użyciu Aspose w C#
url: /pl/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy przy użyciu Aspose w C#

Generowanie kodu kreskowego w C# jest proste, gdy używasz biblioteki Aspose.BarCode. Ten samouczek pokazuje, jak **tworzyć kod kreskowy przy użyciu Aspose** krok po kroku, obejmując format MacroPdf417, typowe ustawienia wyglądu oraz sposób zapisu wyniku jako obrazu PNG.

Nauczysz się:

* Zainstalować i odwołać się do Aspose.BarCode dla .NET  
* Skonfigurować właściwości specyficzne dla MacroPdf417, takie jak file ID, segment ID i checksum  
* Dostosować opcje wizualne, takie jak X‑dimension i liczba kolumn  
* Wyeksportować kod kreskowy do pliku obrazu  

Nie wymagana jest wcześniejsza znajomość Aspose — wystarczy podstawowa wiedza o C# i Visual Studio.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

| Wymaganie | Szczegóły |
|-----------|----------|
| .NET runtime | .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider lub dowolny edytor obsługujący C# |
| Aspose.BarCode | Pakiet NuGet `Aspose.BarCode` (wersja próbna lub licencjonowana) |
| Podstawowa znajomość C# | Znajomość instrukcji `using` i inicjalizacji obiektów |

Możesz dodać Aspose.BarCode do swojego projektu za pomocą Menedżera pakietów NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Jak generować kod kreskowy w C# – ogólny przepływ pracy

Proces składa się z czterech logicznych kroków:

1. **Utwórz instancję `BarcodeGenerator`** z żądanym typem kodowania (MacroPdf417) oraz tekstem, który chcesz zakodować.  
2. **Ustaw wspólne opcje wyglądu** takie jak X‑dimension i liczba kolumn.  
3. **Skonfiguruj właściwości specyficzne dla MacroPdf417** takie jak file ID, segment ID i timestamp.  
4. **Zapisz kod kreskowy** w wybranym formacie pliku (PNG w tym przykładzie).

Każdy krok jest opisany szczegółowo poniżej.

## Krok 1: Utwórz generator kodu kreskowego dla MacroPdf417

Klasa `BarcodeGenerator` jest punktem wejścia dla wszystkich zadań związanych z tworzeniem kodów kreskowych. Podczas jej tworzenia przekazujesz dwa argumenty:

* `EncodeTypes.MacroPdf417` – informuje Aspose, że ma użyć symboliki MacroPdf417.  
* Ciąg danych – tekst, który zostanie zakodowany w kodzie kreskowym.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Dlaczego to ważne:** MacroPdf417 to dwuwymiarowy kod kreskowy, który może przenosić duże ilości danych i obsługuje funkcje makro, takie jak segmentacja pliku, co jest przydatne przy przesyłaniu dużych plików w częściach.

## Krok 2: Ustaw wspólne opcje wyglądu kodu kreskowego

Choć MacroPdf417 posiada wiele specjalistycznych ustawień, nadal chcesz kontrolować gęstość wizualną i układ. Najczęściej używane parametry to:

* **X‑dimension** – szerokość najmniejszego modułu (piksela). Mniejsze wartości dają gęstszy obraz.  
* **Columns** – liczba kolumn danych w wierszu; większe liczby zmniejszają wysokość kodu kreskowego.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Wskazówka:** Utrzymuj `XDimension` w przedziale od 2 do 4 pikseli w większości scenariuszy wyświetlania na ekranie. Większe wartości poprawiają czytelność na drukarkach o niskiej rozdzielczości, ale zwiększają rozmiar obrazu.

## Krok 3: Skonfiguruj właściwości specyficzne dla MacroPdf417

MacroPdf417 dodaje zestaw pól metadanych, które pozwalają podzielić duży plik na kilka segmentów kodu kreskowego. Poniższe właściwości są najczęściej wymagane:

| Właściwość | Cel |
|------------|-----|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku (maks. 8 cyfr). |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 0). |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów w pliku. |
| `MacroPdf417FileName` | Czytelna nazwa oryginalnego pliku. |
| `MacroPdf417Checksum` | Opcjonalna suma kontrolna CCITT‑16 do wykrywania błędów. |
| `MacroPdf417FileSize` | Rozmiar oryginalnego pliku w bajtach. |
| `MacroPdf417TimeStamp` | Znacznik czasu, kiedy plik został wygenerowany. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcjonalne ciągi identyfikujące odbiorcę/nadawcę. |
| `MacroPdf417Terminator` | Określa, czy kod kreskowy jest ostatnim segmentem (`Set`) czy środkowym (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Dlaczego te pola są przydatne:**  
> *Kiedy musisz przesłać duży dokument przez kanał o niskiej przepustowości, możesz podzielić dokument na wiele kodów MacroPdf417. Odbiorca odtwarza oryginalny plik, odczytując metadane każdego segmentu.*

## Krok 4: Zapisz wygenerowany kod kreskowy jako obraz

Aspose obsługuje wiele formatów wyjściowych: PNG, JPEG, BMP, TIFF, SVG i PDF. PNG jest formatem bezstratnym, idealnym do wyświetlania w sieci lub interfejsie użytkownika.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Po uruchomieniu programu znajdziesz plik PNG, który wygląda podobnie do ilustracji poniżej.

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="jak generować kod kreskowy przy użyciu Aspose w C#"}

> **Oczekiwany wynik:** PNG o wymiarach 300 × 150 pikseli, przedstawiający kod MacroPdf417, który koduje tekst „Sample” wraz z podanymi metadanymi makro.

## Pełny, gotowy do uruchomienia przykład

Łącząc wszystkie elementy, oto kompletny program, który możesz skopiować, wkleić i uruchomić:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Uruchom program poleceniem `dotnet run` (lub naciśnij **F5** w Visual Studio). Po wykonaniu sprawdź, czy plik PNG istnieje i otwiera się bez błędów.

## Częste pytania i obsługa przypadków brzegowych

### Co zrobić, jeśli potrzebny jest inny format obrazu?
Aspose obsługuje `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` i `Pdf`. Wystarczy zamienić `BarCodeImageFormat.Png` na żądaną wartość wyliczeniową.

### Jak automatycznie generować wiele segmentów?
Możesz umieścić powyższy kod w pętli, zwiększając `MacroPdf417SegmentID` przy każdym przebiegu i aktualizując ciąg danych. Pamiętaj, aby `MacroPdf417SegmentsCount` pozostało stałe we wszystkich segmentach.

### Co zrobić, gdy dane przekraczają pojemność jednego symbolu MacroPdf417?
MacroPdf417 jest przeznaczony do dużych ładunków, ale każdy kod ma teoretyczny maksymalny rozmiar (≈ 1,1 KB na segment). Podziel plik źródłowy na części mieszczące się w tym limicie, a następnie zakoduj każdą część jako osobny segment.

### Czy sumę kontrolną trzeba obliczać ręcznie?
Aspose może wygenerować sumę kontrolną CCITT‑16 automatycznie, jeśli ustawisz `MacroPdf417Checksum` na `0`. W przykładzie podaliśmy wartość stałą w celach ilustracyjnych; w kodzie produkcyjnym zazwyczaj pozwala się bibliotece obliczyć ją samodzielnie.

### Jak zmienić kolory kodu kreskowego (pierwszy plan/tło)?
Użyj właściwości `BarColor` i `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Podsumowanie

Teraz wiesz, **jak generować kod kreskowy** w C# przy użyciu Aspose.BarCode oraz, konkretnie, **jak tworzyć kod kreskowy przy użyciu Aspose** dla symboliki MacroPdf417. Samouczek obejmował instalację, konfigurację wyglądu oraz pól specyficznych dla makro.

## Co warto nauczyć się dalej?

Poniższe samouczki dotyczą tematyki powiązanej i rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generować obraz kodu PDF417 w C# przy użyciu Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}