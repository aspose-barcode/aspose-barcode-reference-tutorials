---
category: general
date: 2026-08-09
description: Przykład kodu kreskowego Aspose pokazujący, jak używać generatora kodów
  kreskowych w C# do tworzenia Macro PDF417 z pełnym wsparciem metadanych.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: pl
lastmod: 2026-08-09
og_description: Przykład kodu kreskowego Aspose demonstruje użycie generatora kodów
  kreskowych w C# do tworzenia kodu Macro PDF417, który zawiera identyfikator pliku,
  dane segmentu, znacznik czasu i inne metadane.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Przykład kodu kreskowego Aspose – tworzenie Macro PDF417 w C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Przykład kodu kreskowego Aspose: generowanie Macro PDF417 w C#'
url: /pl/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład Aspose barcode: generowanie Macro PDF417 w C#

Jeśli potrzebujesz **aspose barcode example**, które tworzy kod kreskowy Macro PDF417, ten przewodnik pokaże Ci, jak zrobić to za pomocą **barcode generator C#**. Zobaczysz wszystkie wymagane ustawienia, od podstawowych wymiarów po pełny zestaw pól metadanych Macro PDF417, i otrzymasz obraz PNG gotowy do dalszego przetwarzania.

Samouczek obejmuje kompletny przepływ pracy, wyjaśnia, dlaczego każdy parametr ma znaczenie, i dostarcza gotowy do uruchomienia przykład kodu. Nie są wymagane żadne zewnętrzne odwołania; możesz skopiować kod, dostosować wartości i uruchomić go od razu.

## Wymagania wstępne

- .NET 6.0 (lub nowszy) zainstalowany  
- Visual Studio 2022 lub dowolne IDE kompatybilne z C#  
- Ważna licencja na **Aspose.BarCode for .NET** (bezpłatna wersja próbna działa w tym przykładzie)  

Dodaj pakiet NuGet Aspose.BarCode do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz instancję generatora kodów kreskowych C# 

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z wartością wyliczenia `EncodeTypes.MacroPdf417` oraz tekstem, który chcesz zakodować. Tekst może zawierać znaki Unicode, które biblioteka obsługuje automatycznie.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Dlaczego to jest ważne*: `EncodeTypes.MacroPdf417` informuje silnik, aby wygenerował symbol Macro PDF417, który obsługuje segmentowane dane oraz dodatkowe metadane na poziomie pliku. Instrukcja `using` zapewnia zwolnienie niezarządzanych zasobów po zapisaniu obrazu.

## Krok 2: Zdefiniuj podstawowy wygląd kodu kreskowego

Kod kreskowy Macro PDF417 składa się z kwadratowych modułów. Kontrola rozmiaru modułu i liczby kolumn wpływa zarówno na czytelność, jak i rozmiar pliku.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Dlaczego to jest ważne*: `XDimension.Pixels` określa gęstość wizualną; wartość 2 piksele dobrze sprawdza się na wyświetlaczach, jednocześnie utrzymując obraz małym. Dostosuj liczbę kolumn do ograniczeń układu — więcej kolumn tworzy szerszy, krótszy kod kreskowy.

## Krok 3: Ustaw specyficzne metadane Macro PDF417

Macro PDF417 rozszerza standardowy format PDF417 o pola, które umożliwiają odtworzenie dużych plików z wielu segmentów kodu kreskowego. Każde pole jest opcjonalne, ale ich ustawienie demonstruje pełne możliwości API.

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
- `MacroPdf417Checksum` zapewnia szybkie sprawdzenie integralności bez dekodowania całego ładunku.  
- `MacroPdf417FileSize` i `MacroPdf417TimeStamp` pozwalają systemom downstream zweryfikować, że odtworzony plik jest zgodny z oryginałem.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` są przydatne w scenariuszach logistycznych lub wymiany dokumentów.  
- Ustawienie `MacroPdf417Terminator` na `Set` oznacza, że ten kod kreskowy jest ostatnim segmentem, co upraszcza algorytm rekonstrukcji.

## Krok 4: Zapisz wygenerowany obraz kodu kreskowego

Na koniec zapisz kod kreskowy do pliku PNG. Możesz wybrać dowolny obsługiwany format (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Dlaczego to jest ważne*: PNG zachowuje bezstratne dane pikseli, zapewniając, że skanery odczytają dokładny wzór modułów, który skonfigurowałeś. Zmiana formatu może wpłynąć na jakość wizualną i rozmiar pliku.

### Oczekiwany wynik

Uruchomienie pełnego programu tworzy plik o nazwie **ExtPDF417Meta.png**. Otwarcie obrazu pokazuje prostokątny kod kreskowy Macro PDF417 z zakodowanym tekstem „Åspóse.Barcóde©”, a gęstość wizualna odpowiada ustawionej 2‑pikselowej wymiarowi X. Skanowanie obrazu przy użyciu czytnika kompatybilnego z PDF417 zwraca wszystkie pola metadanych zdefiniowane w Kroku 3.

## Pełny działający przykład

Skopiuj poniższy kod do nowego projektu konsolowego (`dotnet new console`) i zamień `YOUR_DIRECTORY` na ścieżkę bezwzględną lub względną, która istnieje na Twoim komputerze.

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

Uruchom program (`dotnet run`). Po wykonaniu sprawdź, czy plik PNG pojawił się w określonym miejscu. Użyj dowolnej aplikacji do odczytu kodów kreskowych obsługującej Macro PDF417, aby potwierdzić, że metadane zostały poprawnie osadzone.

## Typowe warianty i przypadki brzegowe

- **Różne formaty obrazu**: Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Tiff`, jeśli Twój system downstream preferuje inny format.  
- **Zmiana rozmiaru modułu**: Większe wartości `XDimension.Pixels` poprawiają niezawodność skanowania na skanerach o niskiej rozdzielczości, ale zwiększają rozmiar obrazu.  
- **Wiele segmentów**: Aby wygenerować plik wielosegmentowy, utwórz serię kodów kreskowych, zwiększaj `MacroPdf417SegmentID` dla każdego i utrzymuj stały `MacroPdf417FileID`. Tylko ostatni segment powinien mieć ustawiony `MacroPdf417Terminator`.  
- **Obsługa Unicode**: Generator automatycznie koduje znaki Unicode; upewnij się, że Twój ciąg źródłowy używa kodowania UTF-8, jeśli odczytujesz go z zewnętrznego pliku.  
- **Obsługa błędów**: Owiń blok `using` w try‑catch, aby przechwycić `BarCodeException` w przypadku nieprawidłowych parametrów (np. liczba kolumn poza zakresem).

## Porady profesjonalne

- **Wydajność**: Ponownie używaj jednej instancji `BarcodeGenerator` przy tworzeniu wielu kodów kreskowych z tymi samymi ustawieniami; zmieniaj tylko właściwość `CodeText` pomiędzy zapisami.  
- **Szacowanie rozmiaru pliku**: Pole `MacroPdf417FileSize` powinno odpowiadać liczbie bajtów oryginalnego ładunku; niezgodności mogą powodować błędy walidacji w downstream.  
- **Testowanie**: Waliduj wygenerowane kody kreskowe zarówno przy użyciu wbudowanego dekodera Aspose (`BarCodeReader`), jak i skanera zewnętrznego, aby zapewnić interoperacyjność.

## Zakończenie

Ten **aspose barcode example

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak utworzyć strefę ciszy kodu kreskowego dla Code 16K przy użyciu Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak utworzyć strefę ciszy kodu kreskowego dla ITF-14 przy użyciu Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}