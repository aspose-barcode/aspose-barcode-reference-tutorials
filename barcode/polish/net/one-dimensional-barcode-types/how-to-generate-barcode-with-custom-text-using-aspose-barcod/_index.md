---
category: general
date: 2026-10-28
description: Jak generować kod kreskowy z własnym tekstem przy użyciu Aspose.BarCode
  – krok po kroku przewodnik dla programistów .NET do tworzenia obrazów kodów kreskowych
  Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: pl
lastmod: 2026-10-28
og_description: Jak wygenerować kod kreskowy z własnym tekstem w .NET przy użyciu
  Aspose.BarCode. Zapoznaj się z tym kompletnym przewodnikiem, aby utworzyć i zapisać
  kod Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Jak wygenerować kod kreskowy z własnym tekstem – samouczek Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Jak wygenerować kod kreskowy z własnym tekstem przy użyciu Aspose.BarCode dla
  .NET
url: /pl/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy z własnym tekstem przy użyciu Aspose.BarCode dla .NET

Generowanie kodu kreskowego z własnym tekstem jest częstym wymogiem, gdy trzeba osadzić identyfikatory, znaczniki czasu lub inne metadane bezpośrednio w wizualnym kodzie. Ten samouczek pokazuje, jak wygenerować kod Macro PDF417, który zawiera własny tekst oraz pełny zestaw metadanych, przy użyciu biblioteki **Aspose.BarCode** dla .NET.

Nauczysz się, jak skonfigurować generator, zastosować własny tekst, ustawić pola specyficzne dla Macro PDF417 oraz zapisać wynik jako obraz PNG. Nie są wymagane żadne zewnętrzne narzędzia – wystarczy pakiet NuGet Aspose.BarCode i środowisko programistyczne .NET.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)  
* Pakiet NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Te wymagania zapewniają, że kod zostanie skompilowany i uruchomiony bez dodatkowej konfiguracji.

## Krok 1: Zainstaluj pakiet Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję Aspose.BarCode do Twojego projektu, dając dostęp do klasy `BarcodeGenerator` oraz wszystkich powiązanych parametrów.

## Krok 2: Utwórz nową aplikację konsolową

Stwórz minimalną aplikację konsolową, która będzie zawierać logikę generowania kodu kreskowego:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

* **EncodeTypes.MacroPdf417** – wybiera symbologię Macro PDF417, która obsługuje segmentowane dane i metadane.  
* **XDimension.Pixels** – kontroluje rozmiar każdego modułu; wartość 2 piksele zapewnia wyraźny, skanowalny obraz.  
* **Pdf417.Columns** – zmniejsza całkowitą szerokość, czyniąc kod bardziej zwarty dla etykiet drukowanych.  
* **MacroPdf417* properties** – osadzają informacje na poziomie pliku (ID, liczba segmentów, znaczniki czasu itp.) bezpośrednio w kodzie kreskowym. Ta funkcja jest unikalna dla Macro PDF417 i często wykorzystywana w logistyce lub systemach zarządzania dokumentami.  
* **Save(..., BarCodeImageFormat.Png)** – zapisuje bezstratny plik PNG, zachowując ostre krawędzie kodu kreskowego dla niezawodnego skanowania.

## Krok 3: Uruchom program i zweryfikuj wynik

Zbuduj i uruchom aplikację konsolową:

```bash
dotnet run
```

Program tworzy plik `ExtPDF417Meta.png` w katalogu roboczym projektu. Otwierając go, zobaczysz kod Macro PDF417, który koduje tekst **„Åspóse.Barcóde©”** wraz z podanymi metadanymi.

**Oczekiwany wynik** – obraz PNG podobny do poniższego:

![przykładowy wynik generowania kodu kreskowego PNG pokazujący kod Macro PDF417](ExtPDF417Meta.png)

*Tekst alternatywny obrazu („przykładowy wynik generowania kodu kreskowego PNG”) wzmacnia główne słowo kluczowe pod kątem dostępności i SEO.*

## Typowe warianty i przypadki brzegowe

### Użycie innego typu kodu kreskowego

Jeśli potrzebujesz **wygenerować kod kreskowy z własnym tekstem** dla kodu QR zamiast Macro PDF417, zamień `EncodeTypes.MacroPdf417` na `EncodeTypes.QR`. Reszta struktury parametrów pozostaje bez zmian, ale kody QR nie obsługują pól metadanych Macro.

### Obsługa znaków Unicode

Przykład już zawiera znaki Unicode (`Å`, `ó`, `©`). Aspose.BarCode obsługuje wejście UTF‑8 od razu, jednak należy upewnić się, że plik źródłowy jest zapisany w kodowaniu UTF‑8, aby uniknąć ostrzeżeń podczas kompilacji.

### Zapis do innych formatów obrazu

Aspose.BarCode obsługuje BMP, JPEG, TIFF oraz SVG oprócz PNG. Zmieniamy wartość wyliczenia `BarCodeImageFormat` odpowiednio:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Duże zestawy danych

Macro PDF417 może podzielić dane na wiele segmentów. Gdy tekst przekracza pojemność jednego segmentu, zwiększ `MacroPdf417SegmentID` i utrzymuj spójność `MacroPdf417SegmentsCount` we wszystkich wygenerowanych częściach. Takie podejście jest niezbędne w scenariuszach **create barcode aspose**, gdzie ładunek jest większy niż może pomieścić pojedynczy kod kreskowy.

### Obsługa błędów

Otocz logikę generowania blokiem try‑catch, aby wychwycić problemy w czasie wykonywania, takie jak nieprawidłowe ścieżki plików czy nieobsługiwane znaki:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Profesjonalne wskazówki dla niezawodnego generowania kodów kreskowych

* **Zweryfikuj kod kreskowy** po jego utworzeniu przy użyciu `BarCodeReader`. Ten dodatkowy krok potwierdza, że zakodowane dane odpowiadają Twoim oczekiwaniom.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Utrzymuj wymiar X** w przedziale 2 – 4 piksele dla większości skanerów. Mniejsze wartości mogą skutkować nieczytelnymi obrazami na urządzeniach o niskiej rozdzielczości.

* **Unikaj bardzo długich nazw plików** w `MacroPdf417FileName`. Specyfikacja ogranicza to pole do 32 znaków.

* **Używaj spójnych znaczników czasu** (UTC) przy generowaniu wielu segmentów, aby uprościć dalsze przetwarzanie.

## Podsumowanie

Wiesz już, **jak wygenerować kod kreskowy** z własnym tekstem przy użyciu Aspose.BarCode dla .NET, jak skonfigurować metadane Macro PDF417 oraz jak zapisać wynik jako obraz PNG. Kompletny, gotowy do uruchomienia przykład demonstruje każdy wymagany krok – od instalacji pakietu NuGet po obsługę znaków Unicode i zapis wyniku.

Od tego momentu możesz:

* **Generować kod kreskowy z własnym tekstem** dla innych symbologii (QR, DataMatrix itp.)  
* **Tworzyć przepływy pracy Aspose** przetwarzające tysiące obrazów jednocześnie  
* Zintegrować kod generujący kody kreskowe z usługami ASP.NET Core, usługami Windows lub Azure Functions  

Eksperymentuj z różnymi parametrami, odkrywaj dodatkowe pola metadanych i włącz kod kreskowy do swoich pipeline’ów automatyzacji dokumentów. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}