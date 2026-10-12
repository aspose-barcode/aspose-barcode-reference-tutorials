---
category: general
date: 2026-09-22
description: Utwórz makro kod kreskowy PDF417 przy użyciu Aspose.BarCode w C#. Dowiedz
  się krok po kroku, jak wygenerować kod kreskowy za pomocą Aspose, skonfigurować
  metadane i zapisać jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: pl
lastmod: 2026-09-22
og_description: Utwórz kod kreskowy macro PDF417 przy użyciu Aspose.BarCode w C#.
  Ten przewodnik pokazuje, jak wygenerować kod kreskowy za pomocą Aspose, ustawić
  metadane makra i wyeksportować obraz.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Tworzenie makro‑kodu kreskowego PDF417 przy użyciu Aspose.BarCode (C#) –
  przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Utwórz makro kodu kreskowego PDF417 przy użyciu Aspose.BarCode (C#)
url: /pl/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy macro PDF417 przy użyciu Aspose.BarCode (C#)

Jeśli potrzebujesz **utworzyć kod kreskowy macro PDF417** w aplikacji .NET, ten samouczek pokaże Ci dokładnie, jak to zrobić przy pomocy Aspose.BarCode. Zobaczysz kompletny, gotowy do uruchomienia przykład, który **generuje kod kreskowy z Aspose**, konfiguruje wszystkie pola specyficzne dla makra i zapisuje wynik jako obraz PNG.

Kody kreskowe są często używane do inwentaryzacji, wysyłki lub śledzenia dokumentów, a wariant Macro PDF417 pozwala osadzić dodatkowe metadane na poziomie pliku wewnątrz samego kodu. Po przeczytaniu tego przewodnika będziesz w stanie wygenerować w pełni funkcjonalny kod macro PDF417 zgodny ze standardem ISO/IEC 15438.

## Co będzie potrzebne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
* Visual Studio 2022 (lub dowolne IDE dla C#)
* Połączenie internetowe kompatybilne z NuGet, aby pobrać pakiet Aspose.BarCode
* Podstawową znajomość składni C#

Te wymagania wstępne zapewniają, że kod skompiluje się bez dodatkowej konfiguracji.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Biblioteka Aspose.BarCode udostępnia klasę `BarcodeGenerator`, której używamy w całym tym samouczku.

```bash
dotnet add package Aspose.BarCode
```

Uruchomienie tego polecenia dodaje najnowszą stabilną wersję do pliku projektu (`*.csproj`). Pakiet zawiera obsługę PDF417, Macro PDF417 oraz wielu innych symbologii.

## Krok 2: Utwórz nowy projekt konsolowy (opcjonalnie)

Jeśli wolisz czyste rozpoczęcie, wygeneruj aplikację konsolową:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Wygenerowany plik `Program.cs` będzie zawierał kod generujący kod kreskowy.

## Krok 3: Zainicjalizuj generator kodu kreskowego

Generator tworzony jest z wartością wyliczenia `EncodeTypes.MacroPdf417` oraz tekstem, który chcesz zakodować. Aspose.BarCode automatycznie obsługuje znaki Unicode, więc możesz bezpośrednio umieścić litery z akcentami lub symbole.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Dlaczego to ważne
`EncodeTypes.MacroPdf417` informuje bibliotekę, że ma używać wersji makro PDF417, co dodaje możliwość osadzenia metadanych na poziomie pliku (ID pliku, liczba segmentów itp.). Tekst `"Åspóse.Barcóde©"` demonstruje, że generator poprawnie koduje znaki UTF‑8.

## Krok 4: Ustaw podstawowe wymiary kodu kreskowego

PDF417 pozwala kontrolować liczbę kolumn oraz wymiar X (szerokość pojedynczego modułu). Dostosowanie tych wartości wpływa na fizyczny rozmiar kodu i niezawodność skanowania.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Mniejsze wartości tworzą gęstszy kod; większe wartości ułatwiają odczyt niskiej rozdzielczości skanerom.
* **Columns** – Kontroluje liczbę kolumn danych; typowe wartości mieszczą się w przedziale od 1 do 30.

## Krok 5: Skonfiguruj metadane Macro PDF417

Macro PDF417 zawiera dodatkowe pola opisujące plik, który kod reprezentuje. Każde pole jest opcjonalne, ale ich ustawienie zwiększa interoperacyjność ze skanerami rozumiejącymi format makro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Wyjaśnienie poszczególnych pól

| Property | Purpose | Typical range |
|----------|---------|---------------|
| **MacroPdf417FileID** | Unikalny identyfikator logicznego pliku, który może być podzielony na kilka kodów. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Indeks bieżącego segmentu (zaczyna się od 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Łączna liczba segmentów tworzących pełny plik. | 1‑99 |
| **MacroPdf417FileName** | Czytelna nazwa pliku. | Do 255 znaków |
| **MacroPdf417Checksum** | Opcjonalna suma kontrolna do wykrywania błędów. | 0‑65535 |
| **MacroPdf417FileSize** | Rozmiar oryginalnego pliku w bajtach. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Znacznik czasu utworzenia lub modyfikacji pliku. | Dowolny `DateTime` |
| **MacroPdf417Addressee** | Identyfikator odbiorcy (np. dział lub maszyna). | Dowolny ciąg znaków |
| **MacroPdf417Sender** | Identyfikator nadawcy (np. nazwa firmy). | Dowolny ciąg znaków |
| **MacroPdf417Terminator** | Określa, czy ten segment jest ostatnim. | `Set` lub `Unset` |

**Wskazówka:** Jeśli dzielisz duży plik na wiele kodów, upewnij się, że `SegmentID` każdego segmentu jest kolejny, a `SegmentsCount` pozostaje stały we wszystkich segmentach. Skany wykorzystują te wartości do odtworzenia oryginalnego pliku.

## Krok 6: Zapisz obraz kodu kreskowego

Aspose.BarCode obsługuje wiele formatów wyjściowych (PNG, JPEG, BMP, SVG itp.). PNG zapewnia jakość bezstratną, co jest idealne do testów i dokumentacji.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Uruchomienie programu tworzy plik o nazwie `ExtPDF417Meta.png` w katalogu wyjściowym projektu (`bin/Debug/net6.0/`). Otwórz obraz w dowolnej przeglądarce, aby zweryfikować prawidłowe renderowanie kodu.

## Krok 7: Zweryfikuj wygenerowany kod kreskowy (opcjonalnie)

Jeśli posiadasz aplikację skanującą PDF417 (mobilną lub desktopową), zeskanuj zapisany PNG. Skanner powinien zwrócić:

* Zakodowany tekst `"Åspóse.Barcóde©"`
* Wszystkie skonfigurowane pola makro (ID pliku, ID segmentu itp.)

Do automatycznej weryfikacji Aspose.BarCode oferuje także klasę `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Ten fragment pokazuje, jak odczytać metadane makro programowo, potwierdzając, że **generowanie kodu kreskowego z Aspose** działa end‑to‑end.

## Przypadki brzegowe i najlepsze praktyki

| Situation | Recommended handling |
|-----------|----------------------|
| **Unicode characters** | Upewnij się, że łańcuch źródłowy jest UTF‑8 (domyślnie w .NET). Aspose.BarCode automatycznie koduje Unicode, ale sprawdź zestaw znaków skanera. |
| **Large file size** | Macro PDF417 dzieli pliki na maksymalnie 99 segmentów. Jeśli plik przekracza 400 KB, zwiększ `SegmentsCount` i wygeneruj wiele kodów, każdy z kolejno rosnącym `SegmentID`. |
| **Timestamp precision** | Używaj `DateTime.UtcNow` dla czasu uniwersalnego; niektóre skanery oczekują UTC. |
| **Checksum validation** | Podaj prawidłową sumę kontrolną, jeśli planujesz weryfikować integralność po stronie odbiorcy. |
| **Different image formats** | Użyj `BarCodeImageFormat.Svg` dla grafiki wektorowej, gdy potrzebujesz nieskończenie skalowalnych kodów. |
| **Performance** | Ponownie używaj jednej instancji `BarcodeGenerator` przy generowaniu wielu kodów; zmieniaj jedynie `Parameters` między iteracjami. |

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić bez modyfikacji (zakładając, że pakiet NuGet jest zainstalowany).



## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}