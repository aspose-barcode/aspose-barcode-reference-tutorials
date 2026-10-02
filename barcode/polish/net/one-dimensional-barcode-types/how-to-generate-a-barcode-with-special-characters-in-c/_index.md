---
category: general
date: 2026-10-02
description: kod kreskowy ze specjalnymi znakami w C# – dowiedz się, jak wygenerować
  kod kreskowy ze specjalnymi znakami przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: pl
lastmod: 2026-10-02
og_description: kod kreskowy ze znakami specjalnymi w C# – ten tutorial pokazuje,
  jak wygenerować kod kreskowy w C#, który zawiera znaki diakrytyczne i symbole znaków
  towarowych, wraz z kodem i wyjaśnieniami.
og_image_alt: barcode with special characters example output
og_title: Generuj kod kreskowy ze specjalnymi znakami w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak wygenerować kod kreskowy ze specjalnymi znakami w C#
url: /pl/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy ze znakami specjalnymi w C#

Jeśli potrzebujesz wygenerować kod kreskowy ze znakami specjalnymi w C#, ten przewodnik pokaże Ci kompletną, gotową do uruchomienia rozwiązanie. Niezależnie od tego, czy kodujesz litery z akcentami, takie jak **Å**, czy symbole, takie jak **©**, poniższe kroki pozwolą Ci stworzyć kod MacroPdf417, który zachowa każdy znak dokładnie tak, jak go wpisałeś.

Nauczysz się, jak generować kod kreskowy c# przy użyciu biblioteki Aspose.BarCode, konfigurować metadane specyficzne dla MacroPdf417 oraz zapisać wynik jako obraz PNG. Nie są wymagane żadne zewnętrzne narzędzia — wystarczy środowisko programistyczne .NET i pakiet NuGet Aspose.BarCode.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące C#)  
* Aspose.BarCode dla .NET dodany do projektu (`dotnet add package Aspose.BarCode`)  

Te wymagania zapewniają, że kod kompiluje się bez dodatkowych zależności.

## Generowanie kodu kreskowego ze znakami specjalnymi w C#

Rdzeniem rozwiązania jest utworzenie instancji `BarcodeGenerator`, która używa formatu `EncodeTypes.MacroPdf417`. Generator akceptuje dowolny ciąg Unicode, więc możesz bezpośrednio osadzać znaki specjalne.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Dlaczego to działa

* **Wsparcie Unicode** – `BarcodeGenerator` akceptuje `string` zawierający dowolny glif Unicode, więc znaki takie jak **Å**, **ó** i **©** są kodowane bez dodatkowych kroków.  
* **MacroPdf417** – Ten format pozwala dołączyć metadane na poziomie pliku (identyfikator pliku, identyfikator segmentu, suma kontrolna itp.), które oczekują wiele systemów skanowania w przedsiębiorstwach.  
* **Kontrola na poziomie pikseli** – Ustawienie `XDimension.Pixels` kontroluje szerokość modułu, co wpływa na czytelność na drukarkach o niskiej rozdzielczości.  

## Ustaw podstawowy wygląd kodu kreskowego

Dostosowanie `XDimension` i liczby kolumn wpływa zarówno na rozmiar wizualny, jak i na ilość danych mieszczących się w jednym wierszu. Wartość `2` piksele zapewnia kompaktowy, a jednocześnie skanowalny kod, podczas gdy `Columns = 5` utrzymuje symbol na tyle wąski, aby pasował do większości etykiet.

### Porada

Jeśli kierujesz się do drukarki etykiet o wysokiej gęstości, zwiększ `XDimension.Pixels` do `3` lub `4`, aby uniknąć zniekształceń na poziomie pikseli.

## Konfiguracja metadanych MacroPdf417

MacroPdf417 rozszerza standardową specyfikację PDF417 o pola opisujące, jak powinien zostać odtworzony plik wielosegmentowy. Właściwości ustawione w przykładzie odpowiadają typowemu przypadkowi użycia:

| Właściwość | Cel |
|------------|-----|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 1) |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów w pliku |
| `MacroPdf417FileName` | Logiczna nazwa pliku (używana przez niektóre skanery) |
| `MacroPdf417Checksum` | Suma kontrolna CCITT‑16 zapewniająca integralność danych |
| `MacroPdf417FileSize` | Oczekiwany rozmiar w bajtach – pomaga skanerom zweryfikować kompletność |
| `MacroPdf417TimeStamp` | Znacznik czasu utworzenia dla ścieżek audytu |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Opcjonalne informacje routingu |
| `MacroPdf417Terminator` | Wskazuje, czy jest to ostatni segment (`Set`) czy pośredni (`Unset`) |

### Obsługa przypadków brzegowych

* **Duże identyfikatory plików** – Właściwość `FileID` akceptuje 32‑bitową liczbę całkowitą. Jeśli Twój system używa GUID‑ów, przekształć GUID do wartości 32‑bitowej przed przypisaniem.  
* **Precyzja znacznika czasu** – Właściwość przechowuje `DateTime`. Jeśli potrzebujesz precyzji poniżej sekundy, umieść ją w nazwie pliku, ponieważ standard nie obsługuje milisekund.  

## Zapisz obraz kodu kreskowego

Metoda `Save` zapisuje renderowany kod kreskowy w systemie plików. Możesz wybrać inne formaty (`Jpeg`, `Bmp`, `Svg`) zamieniając `BarCodeImageFormat.Png`. PNG jest bezstratny, co czyni go idealnym do dalszego przetwarzania lub osadzania w plikach PDF.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

Po uruchomieniu programu znajdziesz plik `ExtPDF417Meta.png` w katalogu wyjściowym. Otworzenie obrazu pokazuje gęsty, wielowierszowy kod kreskowy, który zawiera tekst **Åspóse.Barcóde©** wraz z makro‑metadanymi, które skonfigurowałeś.

### Oczekiwany wynik

* Plik PNG o przybliżonych wymiarach 300 × 150 pikseli (rozmiar zależy od liczby kolumn).  
* Po zeskanowaniu przy użyciu czytnika kompatybilnego z PDF417, odkodowany tekst wyświetla dokładnie **Åspóse.Barcóde©**, a skaner może odtworzyć oryginalny plik przy użyciu pól makro.

## Jak generować kod kreskowy c# – typowe pułapki

Mimo że kod jest prosty, programiści często napotykają następujące problemy:

1. **Brak pakietu NuGet** – Zapomnienie o zainstalowaniu `Aspose.BarCode` skutkuje błędami kompilacji. Zweryfikuj odwołanie do pakietu w pliku `.csproj`.  
2. **Nieprawidłowe znaki dla wybranej symbologii** – Niektóre typy kodów kreskowych (np. Code 128) odrzucają niektóre zakresy Unicode. MacroPdf417 akceptuje pełny zestaw Unicode, co czyni go najbezpieczniejszym wyborem dla znaków specjalnych.  
3. **Nieprawidłowa ścieżka pliku** – Użycie ścieżki względnej bez odpowiednich uprawnień może spowodować błąd czasu wykonania `UnauthorizedAccessException`. Podaj ścieżkę bezwzględną lub upewnij się, że aplikacja ma prawo zapisu do docelowego folderu.  

Rozwiązanie tych kwestii zapewnia, że generowanie kodu kreskowego c# pozostaje płynnym doświadczeniem.

## Pełny działający przykład

Skopiuj poniższy kompletny program do nowego projektu konsolowego i uruchom go. Nie wymaga dodatkowej konfiguracji poza pakietem NuGet.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with special characters in the payload
            using (BarcodeGenerator generator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 metadata


## Co warto się nauczyć dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z krok po kroku wyjaśnieniami, które pomogą Ci opanować dodatkowe funkcje API i zbadać alternatywne podejścia implementacyjne w własnych projektach.

- [Kod kreskowy ze znakami specjalnymi – Kompletny przewodnik po generowaniu PDF417 przy użyciu](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [Jak wygenerować obraz kodu kreskowego przy użyciu Aspose.BarCode w C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [Jak wygenerować obraz kodu PDF417 w C# z użyciem Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}