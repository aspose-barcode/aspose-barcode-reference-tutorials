---
category: general
date: 2026-11-20
description: Dowiedz się, jak stworzyć makro kod kreskowy PDF417 w C# przy użyciu
  Aspose.BarCode. Ten przewodnik obejmuje metadane, parametry i zapisywanie obrazu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: pl
lastmod: 2026-11-20
og_description: Utwórz makro kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Skorzystaj z tego pełnego samouczka, aby ustawić metadane, skonfigurować parametry
  i wyeksportować plik PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Tworzenie makro kodu kreskowego PDF417 w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak utworzyć makro kod kreskowy PDF417 przy użyciu Aspose.BarCode w C#
url: /pl/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak stworzyć makro kod kreskowy PDF417 przy użyciu Aspose.BarCode w C#

Jeśli potrzebujesz **utworzyć makro kod kreskowy PDF417** w aplikacji .NET, ten samouczek pokazuje dokładne kroki. Zobaczysz, jak skonfigurować metadane specyficzne dla makra, dostosować ustawienia wizualne i zapisać wynik jako plik PNG.

Generowanie makro kodu kreskowego PDF417 jest przydatne, gdy chcesz podzielić duży zestaw danych na kilka symboli, zachowując jednocześnie identyfikator obejmujący cały plik. W poniższym przykładzie używamy biblioteki Aspose.BarCode, która udostępnia płynne API dla wszystkich funkcji PDF417.

Po zakończeniu tego przewodnika będziesz mieć gotowy do uruchomienia program konsolowy, który generuje obraz kodu kreskowego zawierający pełne informacje makro.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany.
* Visual Studio 2022 (lub dowolne IDE obsługujące C#).
* Pakiet NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Możesz dodać pakiet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Inicjalizacja generatora kodów kreskowych dla macro PDF417

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z wartością wyliczenia `EncodeTypes.MacroPdf417`. Informuje to bibliotekę, aby traktowała kod kreskowy jako symbol macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Dlaczego to ważne*: Wybranie `MacroPdf417` włącza wszystkie właściwości związane z makrem w obiekcie parametrów `Pdf417`.

## Krok 2: Ustaw podstawowy wygląd wizualny

Czytelny kod kreskowy zaczyna się od odpowiedniego rozmiaru modułu i liczby kolumn. Właściwość `XDimension.Pixels` kontroluje szerokość pojedynczego modułu, natomiast `Pdf417.Columns` określa, ile kolumn danych zawiera każdy wiersz.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Dostosowanie tych wartości wpływa zarówno na niezawodność skanera, jak i rozmiar obrazu.

## Krok 3: Zdefiniuj szczegóły identyfikacji pliku makro

Macro PDF417 wymaga identyfikatora pliku, identyfikatora segmentu oraz całkowitej liczby segmentów. Te trzy pola umożliwiają skanerowi ponowne złożenie oryginalnego zestawu danych.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Te **parametry macro PDF417** są rdzeniem funkcjonalności makra. Bez nich skaner nie może połączyć symboli razem.

## Krok 4: Dodaj opcjonalne metadane makro

Poza obowiązkowymi identyfikatorami, format makro obsługuje dodatkowe pola, takie jak suma kontrolna, rozmiar pliku, znacznik czasu, odbiorca, nadawca oraz flaga zakończenia. Dostarczenie tych danych poprawia wykrywanie błędów i zapewnia kontekst dla systemów downstream.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Wskazówka*: Jeśli Twój przepływ pracy nie wymaga konkretnego pola, możesz pozostawić jego domyślną wartość. Biblioteka pominie odpowiadający element danych w kodzie kreskowym.

## Krok 5: Zapisz obraz kodu kreskowego

Po skonfigurowaniu wszystkich parametrów wywołaj `Save`, aby wyeksportować kod kreskowy. Przykład zapisuje plik PNG w katalogu określonym przez użytkownika.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Po zakończeniu programu, `ExtPDF417Meta.png` zawiera makro kod PDF417, który koduje tekst `"Åspóse.Barcóde©"` wraz ze wszystkimi metadanymi makro.

## Pełny kod źródłowy

Poniżej znajduje się kompletny, samodzielny program. Skopiuj go do nowego projektu konsolowego i uruchom po zainstalowaniu pakietu NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu wypisuje wiersz potwierdzający podobny do:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Otwarcie pliku PNG pokazuje gęsty, wysokokontrastowy kod kreskowy. Zeskanowanie go przy użyciu skanera kompatybilnego z PDF417 zwraca oryginalny tekst oraz wszystkie pola makro.

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli potrzebuję więcej niż 20 segmentów?

Właściwość `MacroPdf417SegmentsCount` może być ustawiona do `255`. Upewnij się, że system odbierający może obsłużyć większą liczbę segmentów i rozważ podzielenie danych na zarządzalną liczbę symboli.

### Jak suma kontrolna wpływa na skanowanie?

Suma kontrolna CCITT‑16 (`MacroPdf417Checksum`) zapewnia dodatkową warstwę wykrywania błędów. Jeśli skaner wykryje niezgodność, odrzuci kod kreskowy. Możesz pominąć sumę kontrolną, jeśli Twój przepływ pracy jej nie wymaga.

### Czy mogę wygenerować makro kod PDF417 bez Aspose?

Tak, inne biblioteki (np. ZXing.Net, Dynamsoft) obsługują PDF417, ale pola specyficzne dla makra często są pomijane. Aspose.BarCode oferuje najpełniejszą implementację metadanych makro.

### Jakie formaty obrazu są obsługiwane przy zapisywaniu?

Metoda `Save` akceptuje dowolny format zdefiniowany w `BarCodeImageFormat`, taki jak `Png`, `Jpeg`, `Gif`, `Bmp` i `Tiff`. Wybierz format, który pasuje do Twojego łańcucha przetwarzania downstream.

## Zakończenie

Teraz wiesz, jak **utworzyć makro kod kreskowy PDF417** w C# przy użyciu Aspose.BarCode. Samouczek obejmował inicjalizację generatora, ustawienia wizualne, identyfikatory plików makro, opcjonalne metadane oraz eksport obrazu. Dzięki tej podstawie możesz osadzać makro PDF w systemach inwentaryzacji, śledzenia dokumentów lub w dowolnym scenariuszu wymagającym segmentowanej transmisji danych.

Kolejne kroki to eksperymentowanie z różnymi wartościami `XDimension` w celu uzyskania wyższej rozdzielczości, dodawanie regulacji poziomu korekcji błędów lub integracja kodu kreskowego z interfejsem web API, który zwraca strumień PNG bezpośrednio. Powiązane tematy znajdziesz w samouczkach o **przykładzie generatora kodów kreskowych**, **parametrach macro PDF417** oraz obsłudze **metadanych macro PDF417**.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i eksplorować alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć obraz kodu PDF417 w C# z opcjami Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Odczyt kodu kreskowego z obrazu C# – kompletny przewodnik z Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak stworzyć kod PDF417 z Aspose – kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}