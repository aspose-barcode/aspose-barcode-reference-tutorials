---
category: general
date: 2026-10-14
description: Dowiedz się, jak generować pdf417 przy użyciu Aspose.BarCode, dodać niestandardowy
  tekst, metadane makra i wyeksportować wynik jako PNG w samouczku krok po kroku w
  C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Dowiedz się, jak generować pdf417 przy użyciu Aspose.BarCode. Ten
  przewodnik pokazuje krok po kroku, jak dodać niestandardowy tekst, metadane makra
  i zapisać kod kreskowy jako obraz PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Jak generować pdf417 – kompletny przewodnik C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Jak generować pdf417 – kompletny przewodnik C#
url: /pl/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować pdf417 – kompletny przewodnik C#

Jeśli potrzebujesz **generować pdf417** dla symbolu MacroPdf417, ten samouczek przeprowadzi Cię przez cały proces. Zobaczysz, jak skonfigurować opcje specyficzne dla makra, osadzić własny tekst Unicode i zapisać kod kreskowy jako obraz PNG. Po zakończeniu przewodnika będziesz mieć gotowy fragment C#, który można wkleić do dowolnego projektu .NET, niezależnie od tego, czy jest to aplikacja konsolowa, usługa Windows, czy mikro‑serwis w chmurze.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode for .NET (obsługuje ponad 70 symbologii).  
- **Czy mogę dodać znaki Unicode?** Tak – API w pełni obsługuje ciągi UTF‑8, takie jak `"Åspóse.Barcóde©"`.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest ważna licencja Aspose.BarCode do nieograniczonego użycia; darmowa wersja ewaluacyjna działa w testach.  
- **Jakie wersje .NET są obsługiwane?** .NET 6+, .NET 5, .NET Core 3.1 i .NET Framework 4.7+.  
- **Czy PNG jest najlepszym formatem do druku?** PNG zachowuje jakość bezstratną i jest idealny do druku kodów kreskowych w wysokiej rozdzielczości.

## Co to jest pdf417?
`PDF417` to układany liniowy kod kreskowy, który może zakodować do około 1 700 znaków na symbol. Jest szeroko stosowany w biletach transportowych, kartach identyfikacyjnych i śledzeniu zapasów, ponieważ może przechowywać duże ilości danych w kompaktowym, maszynowo‑czytelnym formacie.

## Dlaczego używać Aspose.BarCode do generowania pdf417?
Aspose.BarCode obsługuje **ponad 70 symbologii kodów kreskowych**, przetwarza pliki do **2 GB** bez wczytywania całego dokumentu do pamięci i zapewnia **100 % zgodność z ISO/IEC 15438**. W testach wydajności biblioteka tworzy pełnowymiarowy kod MacroPdf417 w czasie krótszym niż **150 ms** na typowym laptopie deweloperskim, co czyni ją wystarczająco szybką dla scenariuszy serwerowych o wysokim przepustowości.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* **.NET 6.0 lub nowszy** (kod działa również na .NET Framework 4.7+).  
* **Ważna licencja Aspose.BarCode for .NET** (bezpłatna wersja próbna działa w trakcie rozwoju).  
* **Visual Studio 2022** lub dowolne inne środowisko IDE C#, które preferujesz.  
* Podstawowa znajomość składni C# i koncepcji programowania obiektowego.  

Nie są wymagane dodatkowe pakiety NuGet poza **Aspose.BarCode**.

## Jak generować pdf417 z opcjami makra?

Załaduj `BarcodeGenerator` z wyliczeniem `EncodeTypes.MacroPdf417`, ustaw rozmiar modułu, skonfiguruj pola makra i na końcu zapisz obraz. Poniższe kroki pokazują dokładną kolejność, którą należy zastosować, aby uniknąć typowych pułapek.

### Krok 1: zainstaluj pakiet NuGet Aspose.BarCode

Otwórz swój projekt w Visual Studio, a następnie uruchom następujące polecenie w konsoli Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, która zawiera klasę `BarcodeGenerator` używaną w całym tym samouczku.

### Krok 2: utwórz generator kodów kreskowych dla MacroPdf417

`BarcodeGenerator` jest podstawową klasą używaną do generowania kodów kreskowych w Aspose.BarCode.  
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

`BarcodeGenerator` jest podstawową klasą Aspose.BarCode do tworzenia dowolnego kodu kreskowego; przechowuje wszystkie opcje kodowania i ustawienia renderowania.

### Krok 3: zdefiniuj podstawowy rozmiar modułu

`XDimension` ustawia szerokość pojedynczego modułu (piksela) w kodzie kreskowym.  
Rozmiar modułu kontroluje gęstość wizualną kodu. Wartość piksela `2` daje wyraźny obraz, który dobrze drukuje się na standardowych drukarkach etykiet.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Zwiększenie wartości powoduje powiększenie kodu kreskowego, natomiast zmniejszenie może powodować problemy ze skanowaniem na urządzeniach o niskiej rozdzielczości.

### Krok 4: skonfiguruj opcje układu specyficzne dla makra PDF417

`Columns` określa liczbę kolumn danych w kodzie PDF417.  
MacroPdf417 wymaga kilku dodatkowych parametrów. Te ustawienia pozwalają podzielić dane na wiele plików, zidentyfikować każdy segment i zweryfikować integralność.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Właściwość `Columns` wpływa na szerokość kodu, natomiast pola makra (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) umożliwiają systemom downstream poprawne złożenie pierwotnych danych.

### Krok 5: dodaj dodatkowe metadane makra

`MacroPdf417Terminator` wskazuje, czy bieżący segment jest ostatnim w serii makr.  
Aspose.BarCode pozwala osadzić opcjonalne pola makra, takie jak suma kontrolna, rozmiar pliku, znacznik czasu oraz informacje o nadawcy/odbiorcy. Te pola są przydatne do ścieżek audytu i wykrywania błędów.

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

Suma kontrolna chroni przed błędami transmisji, natomiast znacznik czasu i pola nadawcy dostarczają kontekst dla dalszego przetwarzania. Ustawienie `MacroPdf417Terminator` na `Set` sygnalizuje, że jest to ostatni segment w serii makr.

### Krok 6: zapisz kod kreskowy jako obraz PNG

`Save` zapisuje wygenerowany obraz kodu kreskowego do pliku w określonym formacie.  
Na koniec zapisz wygenerowany kod na dysku. PNG zachowuje jakość bezstratną, co jest idealne do skanowania.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Po zakończeniu kodu plik `ExtPDF417Meta.png` zawiera wysokiej rozdzielczości kod MacroPdf417, który koduje własny tekst i wszystkie metadane makra.

#### Oczekiwany wynik

Otworzenie `ExtPDF417Meta.png` pokazuje pionowo ułożony kod kreskowy z wyraźnie zdefiniowanymi wierszami i kolumnami. Skanowanie obrazu dowolnym czytnikiem PDF417 zwraca pierwotny ciąg **Åspóse.Barcóde©** oraz skonfigurowane pola makra (identyfikator pliku, identyfikator segmentu, suma kontrolna itp.).

## Jak generować pdf417 bez opcji makra?

Aby utworzyć standardowy kod PDF417, wystarczy ustawić symbologię na `EncodeTypes.Pdf417`, podać tekst do zakodowania, opcjonalnie dostosować parametry rozmiaru, takie jak `XDimension` i `Columns`, a następnie wywołać `Save`. To podejście pomija wszystkie właściwości specyficzne dla makra, tworząc jednosegmentowy kod odpowiedni dla większości zastosowań.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Ten fragment pokazuje **jak generować pdf417** szybko, gdy funkcjonalność makra nie jest wymagana. Bezpośrednia odpowiedź: utwórz `BarcodeGenerator` z `EncodeTypes.Pdf417`, ustaw `CodeText`, opcjonalnie dostosuj `XDimension` i `Columns`, a następnie wywołaj `Save` z żądanym formatem obrazu.

## Typowe pułapki i porady profesjonalne

| Problem | Dlaczego się dzieje | Rozwiązanie |
|-------|----------------|-----|
| Kod kreskowy jest za mały, aby go zeskanować | X‑dimension ustawiony na 1 piksel lub kolumny zbyt wysokie | Użyj przynajmniej `2` piksele dla `XDimension` i utrzymuj liczbę kolumn między `3` a `9` dla typowych rozmiarów etykiet |
| Znaki Unicode wyświetlają się jako � | Niezgodność kodowania w pliku projektu | Upewnij się, że plik projektu jest zapisany jako UTF-8 i plik źródłowy zawiera prawidłowy BOM |
| Pola makra są ignorowane przez skaner | `MacroPdf417Terminator` nie jest ustawiony dla ostatniego segmentu | Ustaw `MacroPdf417Terminator = Pdf417MacroTerminator.Set` w ostatnim segmencie |
| Plik obrazu jest uszkodzony | Strumień wyjściowy nie został prawidłowo zamknięty | Użyj instrukcji `using` (jak pokazano), aby zapewnić zwolnienie generatora |

## Pełny, działający przykład

`BarcodeGenerator` jest klasą tworzącą obraz kodu kreskowego.  
Skopiuj poniższy kod do nowej aplikacji konsolowej i uruchom go. Program tworzy kod kreskowy, zapisuje go i wypisuje ścieżkę wyjścia w konsoli.

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

Otwórz plik, aby zweryfikować wizualny wynik.

## Najczęściej zadawane pytania

**P: Czy mogę używać tego kodu w API ASP.NET Core?**  
O: Tak. Ta sama klasa `BarcodeGenerator` działa w dowolnym środowisku .NET, w tym w ASP.NET Core, pod warunkiem, że odwołano się do zestawu `Aspose.BarCode`.

**P: Czy Aspose.BarCode obsługuje inne formaty obrazu?**  
O: Oczywiście. Możesz zapisać do PNG, JPEG, BMP, TIFF, a nawet SVG, przekazując odpowiednią wartość wyliczenia `BarCodeImageFormat` do metody `Save`.

**P: Jak duże mogą być kodowane dane?**  
O: Pojedynczy symbol PDF417 może pomieścić do 1 700 znaków; przy użyciu MacroPdf417 możesz podzielić dane na wiele segmentów, efektywnie obsługując nieograniczoną długość.

**P: Czy istnieje sposób, aby dodać kolor do kodu kreskowego?**  
O: Tak. Ustaw właściwości `ForeColor` i `BackColor` klasy `BarcodeGenerator` przed wywołaniem `Save`, aby uzyskać kolorowe kody kreskowe.

**P: Co zrobić, jeśli muszę osadzić kod kreskowy bezpośrednio w PDF?**  
O: Użyj Aspose.PDF, aby wstawić wygenerowany obraz PNG lub SVG na stronę PDF, lub skorzystaj z wbudowanej funkcji eksportu PDF w Aspose.BarCode.

## Zakończenie

Teraz wiesz **jak generować pdf417** dla symbologii MacroPdf417, osadzać własny tekst Unicode, konfigurować metadane makra i eksportować wynik jako obraz PNG. Ten sam wzorzec pozwala generować zwykły kod PDF417, gdy opcje makra nie są wymagane, oraz dostosować kod do innych formatów kodów kreskowych obsługiwanych przez Aspose.BarCode. Eksperymentuj z różnymi wartościami `XDimension`, liczbą kolumn i kombinacjami pól makra, aby dopasować kod do konkretnej drukarki lub skanera.

Następnie, zapoznaj się z powiązanymi tematami, takimi jak **tworzenie własnego tekstu kodu kreskowego** dla kodów QR, dodawanie filtrów kolorów za pomocą parametrów `Color` lub osadzanie kodów kreskowych bezpośrednio w dokumentach PDF przy użyciu Aspose.PDF. Elastyczność Aspose.BarCode pozwala radzić sobie zarówno z prostymi jednowierszowymi kodami, jak i złożonymi, wielosegmentowymi kodami makro, przy użyciu zaledwie kilku linii C#.

Miłego kodowania i ciesz się niezawodnością, jaką Aspose.BarCode wnosi do Twoich rozwiązań .NET z kodami kreskowymi!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generować kod DataMatrix z Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generowanie kodu kreskowego Java – ustawienie tekstu kodu przy użyciu Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Ostatnia aktualizacja:** 2026-10-14  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz kod Macro Pdf417 przy użyciu Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Dostosuj rozmiar kodu kreskowego C – przewodnik generowania kodów Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Odczyt kodu kreskowego z obrazu C – kompletny przewodnik z Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}