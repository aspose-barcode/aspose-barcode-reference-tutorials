---
category: general
date: 2026-10-09
description: Dowiedz się, jak utworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode
  – generuj Macro PDF417 z pełnym wsparciem metadanych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Dowiedz się, jak utworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode
  – generuj Macro PDF417 z pełnym wsparciem metadanych, w tym file ID, segment data,
  timestamp i innych.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Jak utworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Jak utworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417 w C#** szybko i niezawodnie, ten samouczek przeprowadzi Cię przez cały proces przy użyciu Aspose.BarCode. Zobaczysz wszystkie wymagane ustawienia, od podstawowych wymiarów po pełny zestaw pól metadanych Macro PDF417, a zakończysz obrazem PNG gotowym do dalszego przetwarzania.

## Szybkie odpowiedzi
- **Która biblioteka generuje kody kreskowe PDF417?** Aspose.BarCode for .NET.
- **Jaki format generuje przykład?** A loss‑less PNG image.
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa dla przykładu; licencja komercyjna jest wymagana w produkcji.
- **Która wersja .NET jest obsługiwana?** .NET 6.0 lub nowsza.
- **Czy mogę dodać metadane do kodu kreskowego?** Tak – Macro PDF417 obsługuje identyfikator pliku, liczbę segmentów, znaczniki czasu i inne.

## Co to jest kod kreskowy PDF417?
Kod kreskowy PDF417 to układ liniowy warstwowy, który może zakodować do około 1 KB danych na symbol i obsługuje opcjonalne metadane macro dla plików wielosegmentowych. Składa się z wielu rzędów ułożonych linii, co pozwala na dużą pojemność danych przy jednoczesnej czytelności przez standardowe skanery 2‑D. Format zawiera również poziomy korekcji błędów zwiększające niezawodność, a opcjonalna funkcja macro umożliwia podział dużych plików na kilka kodów kreskowych z metadanymi ułatwiającymi ich ponowne złożenie.

## Dlaczego używać Aspose.BarCode dla PDF417?
Aspose.BarCode obsługuje **ponad 50 symbologii kodów kreskowych** i może generować kody Macro PDF417 z maksymalnie **2 000 kolumn**, obsługując pliki większe niż **10 MB** bez ładowania całej zawartości do pamięci. Ta zmierzona zdolność zapewnia płynne działanie scenariuszy o wysokiej przepustowości w przedsiębiorstwach i oferuje rozbudowane opcje dostosowywania.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- .NET 6.0 (lub nowszy) zainstalowany  
- Visual Studio 2022 lub dowolne środowisko IDE zgodne z C#  
- Ważną licencję na **Aspose.BarCode for .NET** (darmowa wersja próbna działa w tym przykładzie)  

Dodaj pakiet NuGet Aspose.BarCode do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

## Jak utworzyć kod kreskowy PDF417 w C#?

`BarcodeGenerator` jest główną klasą do tworzenia obrazów kodów kreskowych.  
`EncodeTypes.MacroPdf417` wybiera symbologię Macro PDF417 do generowania kodu.  
`Save` zapisuje wygenerowany kod kreskowy do pliku obrazu.

Załaduj `BarcodeGenerator` z wyliczeniem `EncodeTypes.MacroPdf417` oraz docelowym tekstem, a następnie wywołaj `Save` – to pełny przepływ tworzenia w trzech linijkach. Generator automatycznie obsługuje Unicode, a instrukcja `using` zapewnia zwolnienie niezarządzanych zasobów po zapisaniu obrazu.

### Krok 1: utwórz instancję generatora kodu kreskowego w C#

Klasa `BarcodeGenerator` tworzy i konfiguruje obrazy kodów kreskowych.  

Zainicjuj `BarcodeGenerator` przy użyciu wartości wyliczenia `EncodeTypes.MacroPdf417` i tekstu, który chcesz zakodować. Tekst może zawierać znaki Unicode, które biblioteka obsługuje automatycznie.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Dlaczego to jest ważne*: `EncodeTypes.MacroPdf417` informuje silnik, aby wygenerował symbol Macro PDF417, który obsługuje dane segmentowane oraz dodatkowe metadane na poziomie pliku. Instrukcja `using` zapewnia zwolnienie niezarządzanych zasobów po zapisaniu obrazu.

### Krok 2: określ podstawowy wygląd kodu kreskowego

`XDimension.Pixels` ustawia rozmiar każdego modułu kodu kreskowego w pikselach.

Kod Macro PDF417 składa się z kwadratowych modułów. Kontrola rozmiaru modułu i liczby kolumn wpływa zarówno na czytelność, jak i rozmiar pliku.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Dlaczego to jest ważne*: `XDimension.Pixels` określa gęstość wizualną; wartość 2 piksele dobrze sprawdza się na ekranie, jednocześnie utrzymując mały rozmiar obrazu. Dostosuj liczbę kolumn do ograniczeń układu – więcej kolumn tworzy szerszy, krótszy kod.

### Krok 3: ustaw specyficzne metadane Macro PDF417

`MacroPdf417FileID` identyfikuje plik, do którego należą wszystkie segmenty kodu kreskowego.

Macro PDF417 rozszerza standardowy format PDF417 o pola umożliwiające odtworzenie dużych plików z wielu segmentów kodu kreskowego. Każde pole jest opcjonalne, ale ich ustawienie demonstruje pełne możliwości API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Dlaczego to jest ważne*:  
- `MacroPdf417FileID` łączy wszystkie segmenty należące do tego samego logicznego pliku.  
- `MacroPdf417SegmentID` i `MacroPdf417SegmentsCount` umożliwiają dekoderowi prawidłowe uporządkowanie fragmentów.  
- `MacroPdf417Checksum` zapewnia szybkie sprawdzenie integralności bez dekodowania całej zawartości.  
- `MacroPdf417FileSize` i `MacroPdf417TimeStamp` pozwalają systemom downstream zweryfikować, czy odtworzony plik odpowiada oryginałowi.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` są przydatne w scenariuszach logistycznych lub wymiany dokumentów.  
- Ustawienie `MacroPdf417Terminator` na `Set` oznacza, że ten kod jest ostatnim segmentem, co upraszcza algorytm rekonstrukcji.

### Krok 4: zapisz wygenerowany obraz kodu kreskowego

`Save` zapisuje obraz kodu kreskowego w określonej ścieżce pliku.

Na koniec zapisz kod jako plik PNG. Możesz wybrać dowolny obsługiwany format (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Dlaczego to jest ważne*: PNG zachowuje bezstratne dane pikseli, zapewniając, że skanery odczytają dokładny wzór modułów, który skonfigurowałeś. Zmiana formatu może wpłynąć na jakość wizualną i rozmiar pliku.

#### Oczekiwany wynik

Uruchomienie pełnego programu tworzy plik o nazwie **ExtPDF417Meta.png**. Otwierając obraz, zobaczysz prostokątny kod Macro PDF417 z zakodowanym tekstem „Åspóse.Barcóde©”, a gęstość wizualna odpowiada ustawionej dwupikselowej wymiarowi X. Skanowanie obrazu przy użyciu czytnika kompatybilnego z PDF417 zwróci wszystkie pola metadanych zdefiniowane w Kroku 3.

## Pełny działający przykład

Skopiuj poniższy kod do nowego projektu konsolowego (`dotnet new console`) i zamień `YOUR_DIRECTORY` na absolutną lub względną ścieżkę istniejącą na Twoim komputerze.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Uruchom program (`dotnet run`). Po zakończeniu sprawdź, czy plik PNG pojawił się w wybranej lokalizacji. Użyj dowolnej aplikacji do odczytu kodów kreskowych obsługującej Macro PDF417, aby potwierdzić prawidłowe osadzenie metadanych.

## Typowe warianty i przypadki brzegowe

- **Różne formaty obrazu**: Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Tiff`, jeśli Twój system downstream preferuje inny format.  
- **Zmiana rozmiaru modułu**: Większe wartości `XDimension.Pixels` poprawiają niezawodność skanowania na skanerach o niskiej rozdzielczości, ale zwiększają rozmiar obrazu.  
- **Wiele segmentów**: Aby utworzyć plik wielosegmentowy, wygeneruj serię kodów, zwiększając `MacroPdf417SegmentID` dla każdego i utrzymując stały `MacroPdf417FileID`. Tylko ostatni segment powinien mieć ustawiony `MacroPdf417Terminator`.  
- **Obsługa Unicode**: Generator automatycznie koduje znaki Unicode; upewnij się, że Twój ciąg źródłowy używa kodowania UTF‑8, jeśli odczytujesz go z zewnętrznego pliku.  
- **Obsługa błędów**: Otocz blok `using` konstrukcją try‑catch, aby przechwycić `BarCodeException` w przypadku nieprawidłowych parametrów (np. liczba kolumn poza zakresem).

## Porady profesjonalne

- **Wydajność**: Ponownie używaj jednej instancji `BarcodeGenerator` przy tworzeniu wielu kodów z tymi samymi ustawieniami; zmieniaj tylko właściwość `CodeText` pomiędzy zapisami.  
- **Szacowanie rozmiaru pliku**: Pole `MacroPdf417FileSize` powinno odpowiadać liczbie bajtów oryginalnej zawartości; niezgodności mogą powodować błędy walidacji w downstream.  
- **Testowanie**: Waliduj wygenerowane kody zarówno przy użyciu wbudowanego dekodera Aspose (`BarCodeReader`), jak i zewnętrznego skanera, aby zapewnić interoperacyjność.

## Zakończenie

Ten przykład **Aspose.BarCode** pokazuje, jak **utworzyć kod kreskowy PDF417 w C#** z pełnym wsparciem metadanych Macro, dając solidną bazę do budowy niezawodnych przepływów wymiany danych opartych na kodach kreskowych.

## Co warto nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, rozwijające techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, pomagając opanować dodatkowe funkcje API i eksplorować alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak utworzyć strefę ciszy dla Code 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak utworzyć strefę ciszy dla ITF-14 przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---


**Ostatnia aktualizacja:** 2026-10-09  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak wygenerować obraz kodu PDF417 w C z Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Samouczek generatora kodów – Jak wygenerować kod PDF417 w](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}