---
category: general
date: 2026-08-12
description: Generuj kod kreskowy Aspose przy użyciu Aspose.BarCode i dowiedz się,
  jak wygenerować PDF417 z własnym tekstem w kilku prostych krokach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: pl
lastmod: 2026-08-12
og_description: Generuj kod kreskowy Aspose przy użyciu Aspose.BarCode. Ten samouczek
  pokazuje, jak wygenerować PDF417 z niestandardowym tekstem, metadanymi makra i zapisać
  wynik jako PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Generowanie kodu kreskowego Aspose – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Generowanie kodu kreskowego Aspose – kompletny przewodnik C#
url: /pl/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego Aspose – kompletny przewodnik C#

Jeśli potrzebujesz **generate barcode aspose** dla symbolu MacroPdf417, ten samouczek przeprowadzi Cię przez cały proces. Zobaczysz, jak skonfigurować opcje specyficzne dla makra, osadzić własny tekst i zapisać kod kreskowy jako obraz PNG.

Generowanie kodu kreskowego przy użyciu Aspose.BarCode eliminuje ręczne obliczenia i zapewnia zgodność ze specyfikacją PDF417. W poniższych krokach dowiesz się także **how to generate pdf417** z niestandardowymi metadanymi, takimi jak identyfikator pliku, liczba segmentów i znaczniki czasu. Po zakończeniu przewodnika będziesz mieć gotowy przykład kodu, który możesz wkleić do dowolnego projektu .NET.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy (kod działa także z .NET Framework 4.7+)
* Ważną licencję Aspose.BarCode dla .NET (bezpłatna wersja ewaluacyjna wystarczy do testów)
* Visual Studio 2022 lub dowolne IDE C#, którego używasz
* Podstawową znajomość składni C# oraz koncepcji obiektowych

Nie są wymagane dodatkowe pakiety NuGet poza **Aspose.BarCode**.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz projekt w Visual Studio, a następnie uruchom następujące polecenie w konsoli Menedżera Pakietów:

```powershell
Install-Package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, w której znajduje się klasa `BarcodeGenerator` używana w całym samouczku.

## Krok 2: Utwórz generator kodu kreskowego dla MacroPdf417

Pierwsza linia tworzy instancję `BarcodeGenerator`, która celuje w symbologię **MacroPdf417** i osadza własny tekst, który chcesz zakodować.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Dlaczego to ważne*: Enum `EncodeTypes.MacroPdf417` informuje Aspose, że kod kreskowy ma być traktowany jako makro‑włączony symbol PDF417, co umożliwia podział dużych danych na wiele segmentów. Ciąg `"Åspóse.Barcóde©"` pokazuje, że generator prawidłowo obsługuje znaki Unicode.

## Krok 3: Zdefiniuj podstawowy rozmiar modułu

Rozmiar modułu kontroluje wizualną gęstość kodu kreskowego. Wartość pikselowa `2` daje wyraźny obraz, który dobrze drukuje się na standardowych drukarkach etykiet.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Zwiększenie wartości powiększa kod kreskowy, a zmniejszenie może powodować problemy ze skanowaniem na urządzeniach o niskiej rozdzielczości.

## Krok 4: Skonfiguruj opcje układu specyficzne dla PDF417 macro

MacroPdf417 wymaga kilku dodatkowych parametrów. Te ustawienia pozwalają podzielić dane na wiele plików, zidentyfikować każdy segment i zweryfikować integralność.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Dlaczego to ważne*: Właściwość `Columns` wpływa na szerokość kodu kreskowego, natomiast pola makro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) umożliwiają systemom downstream prawidłowe odtworzenie pierwotnych danych.

## Krok 5: Dodaj dodatkowe metadane makro

Aspose.BarCode pozwala osadzić opcjonalne pola makro, takie jak suma kontrolna, rozmiar pliku, znacznik czasu oraz informacje nadawcy/odbiorcy. Pola te są przydatne w ścieżkach audytu i wykrywaniu błędów.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Dlaczego to ważne*: Suma kontrolna chroni przed błędami transmisji, a znacznik czasu i pola nadawcy dostarczają kontekstu dla dalszego przetwarzania. Ustawienie `MacroPdf417Terminator` na `Set` sygnalizuje, że jest to ostatni segment w serii makro.

## Krok 6: Zapisz kod kreskowy jako obraz PNG

Na koniec zapisz wygenerowany kod kreskowy na dysku. PNG zachowuje jakość bezstratną, co jest idealne do skanowania.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Po zakończeniu działania kodu plik `ExtPDF417Meta.png` zawiera wysokiej rozdzielczości kod MacroPdf417, który koduje własny tekst oraz wszystkie metadane makro.

### Oczekiwany wynik

Otwarcie `ExtPDF417Meta.png` pokazuje pionowo ułożony kod kreskowy z wyraźnie zdefiniowanymi wierszami i kolumnami. Skanowanie obrazu dowolnym czytnikiem PDF417 zwraca oryginalny ciąg **Åspóse.Barcóde©** oraz skonfigurowane pola makro (identyfikator pliku, identyfikator segmentu, suma kontrolna itp.).

## Jak wygenerować pdf417 bez opcji makro (alternatywny scenariusz)

Jeśli potrzebujesz jedynie standardowego kodu PDF417, pomiń właściwości makro i zachowaj podstawową konfigurację:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Ten fragment pokazuje **how to generate pdf417** szybko, gdy funkcjonalność makro nie jest wymagana.

## Częste pułapki i wskazówki profesjonalistów

| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| Kod kreskowy jest za mały, by go zeskanować | X‑dimension ustawiony na 1 piksel lub zbyt duża liczba kolumn | Użyj przynajmniej `2` pikseli dla `XDimension` i utrzymuj liczbę kolumn między `3` a `9` dla typowych rozmiarów etykiet |
| Znaki Unicode wyświetlają się jako � | Nieprawidłowe kodowanie w pliku projektu | Upewnij się, że plik projektu jest zapisany jako UTF‑8 i zawiera prawidłowy BOM |
| Pola makro są ignorowane przez skaner | `MacroPdf417Terminator` nie ustawiono dla ostatniego segmentu | Ustaw `MacroPdf417Terminator = Pdf417MacroTerminator.Set` w ostatnim segmencie |
| Plik obrazu jest uszkodzony | Strumień wyjściowy nie został prawidłowo zamknięty | Użyj instrukcji `using` (jak pokazano), aby zagwarantować zwolnienie zasobów generatora |

## Pełny, uruchamialny przykład

Skopiuj poniższy kod do nowej aplikacji konsolowej i uruchom go. Program tworzy kod kreskowy, zapisuje go i wypisuje ścieżkę wyjściową w konsoli.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Uruchomienie programu wypisuje wiersz podobny do:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Otwórz plik, aby zweryfikować wizualny rezultat.

## Zakończenie

Teraz wiesz, jak **generate barcode aspose** dla symbologii MacroPdf417, osadzić własny tekst Unicode, skonfigurować metadane makro i wyeksportować wynik jako obraz PNG. Ten sam schemat pozwala Ci **how to generate pdf417** bez opcji makro, a kod możesz dostosować do innych formatów kodów kreskowych obsługiwanych przez Aspose.BarCode.

Następnie poznaj tematy pokrewne, takie jak **create barcode custom text** dla kodów QR, dodawanie filtrów kolorów przy użyciu parametrów `Color` lub osadzanie kodów kreskowych bezpośrednio w dokumentach PDF przy pomocy Aspose.PDF. Eksperymentuj z różnymi wartościami `XDimension` i liczbą kolumn, aby dopasować kod kreskowy do konkretnej drukarki lub skanera.

Miłego kodowania i ciesz się niezawodnością, jaką Aspose.BarCode wnosi do Twoich rozwiązań .NET!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak wygenerować kod DataMatrix z Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generowanie kodu kreskowego Java – Ustaw tekst kodu przy użyciu Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}