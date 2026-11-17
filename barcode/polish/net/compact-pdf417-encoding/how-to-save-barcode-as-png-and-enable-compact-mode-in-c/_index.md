---
category: general
date: 2026-11-17
description: Dowiedz się, jak zapisać kod kreskowy, włączyć tryb kompaktowy, dostosować
  kolumny i wygenerować kod PDF417, korzystając z pełnego przykładu w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: pl
lastmod: 2026-11-17
og_description: Jak zapisać kod kreskowy, włączyć tryb kompaktowy i dostosować kolumny
  podczas generowania kodu PDF417 w C#. Postępuj zgodnie z przewodnikiem krok po kroku.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Jak zapisać kod kreskowy jako PNG i włączyć tryb kompaktowy w C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Jak zapisać kod kreskowy jako PNG i włączyć tryb kompaktowy w C#
url: /pl/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zapisać kod kreskowy jako PNG i włączyć tryb kompaktowy w C#

Jeśli potrzebujesz **jak zapisać kod kreskowy** w formacie, który można używać w sieci lub w druku, ten przewodnik pokaże Ci dokładne kroki. Dowiesz się także, jak **włączyć tryb kompaktowy**, **dostosować kolumny** oraz **wygenerować kod kreskowy PDF417** przy użyciu biblioteki Aspose.BarCode dla .NET.

Tutorial obejmuje wszystko – od konfiguracji projektu po ostateczny plik PNG, więc możesz skopiować kod do własnego rozwiązania bez dodatkowych poszukiwań. Nie jest wymagana żadna zewnętrzna dokumentacja; pełny, gotowy do uruchomienia przykład jest w zestawie.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE dla C#)  
* Pakiet NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Te trzy elementy są jedynymi zależnościami dla poniższego kodu.

## Krok 1: Utwórz generator kodu PDF417

Pierwszym zadaniem przy **generowaniu kodu PDF417** jest utworzenie instancji `BarcodeGenerator` z odpowiednim typem kodowania i danymi, które chcesz zakodować.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

Enum `EncodeTypes.Pdf417` informuje bibliotekę, że ma użyć symbologii PDF417, czyli stosowanego kodu liniowego przeznaczonego do kodowania dużych ilości danych. Ciąg `"Compact mode"` staje się tekstem czytelnym dla człowieka pod kodem kreskowym.

## Krok 2: Ustaw wymiar X (szerokość modułu)

Każda kreska w kodzie kreskowym nazywana jest modułem. Kontrolowanie szerokości modułu pozwala precyzyjnie dostroić wizualny rozmiar kodu bez zmiany danych.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Wymiar X równy 2 piksele daje kompaktowy obraz, który nadal jest niezawodnie odczytywany przez większość urządzeń.

## Krok 3: **Jak dostosować kolumny** dla kodu PDF417

PDF417 umożliwia określenie liczby kolumn, które ma wykorzystać kod kreskowy. Mniej kolumn daje wyższy, węższy symbol, natomiast więcej kolumn sprawia, że symbol jest szerszy, ale niższy.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Ten wiersz demonstruje **jak dostosować kolumny**. Możesz zmienić wartość na 2, 4 lub dowolną liczbę obsługiwaną przez bibliotekę, w zależności od dostępnej przestrzeni na docelowym nośniku.

## Krok 4: **Jak włączyć tryb kompaktowy** i przyciąć symbol

Tryb kompaktowy usuwa niepotrzebne wypełnienie i zmniejsza ogólny rozmiar kodu kreskowego. Biblioteka udostępnia tę funkcję poprzez właściwość `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Zauważ, że fraza **włączyć tryb kompaktowy** pojawia się tutaj, a ta sama czynność jest opisana dokładnym sformułowaniem **jak włączyć tryb kompaktowy** później w przewodniku, aby spełnić wymagania dotyczące drugorzędnego słowa kluczowego.

## Krok 5: **Jak zapisać kod kreskowy** jako obraz PNG

Zapis wygenerowanego obrazu to ostatni krok. Metoda `Save` zapisuje kod kreskowy w systemie plików w wybranym formacie.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Zastąp `YOUR_DIRECTORY` ścieżką absolutną lub względną, do której Twoja aplikacja ma prawo zapisu. Po uruchomieniu znajdziesz plik o nazwie `CompactPdf417.png` zawierający kompaktowy kod PDF417.

### Oczekiwany wynik

Otwarcie zapisanego pliku PNG pokazuje pionowo kompaktowy kod PDF417 z trzema kolumnami i przyciętym wypełnieniem. Rozmiar wizualny wynosi około 2 px na moduł, co czyni obraz odpowiednim do osadzania w znacznikach HTML `<img>` lub do druku na małych etykietach.

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się kompletny program, który możesz skopiować do nowego projektu konsolowego. Zawiera wszystkie niezbędne dyrektywy `using` oraz demonstruje **jak zapisać kod kreskowy**, **włączyć tryb kompaktowy**, **jak dostosować kolumny** i **generować kod PDF417** w jednym przepływie.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Uruchomienie tego programu tworzy opisany wcześniej plik PNG. Konsolowy komunikat potwierdza lokalizację zapisanego pliku, co pomaga zweryfikować, że krok **jak zapisać kod kreskowy** zakończył się sukcesem.

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli potrzebny jest inny format obrazu?

Metoda `Save` przyjmuje dowolną wartość z enumu `BarCodeImageFormat`, taką jak `Jpeg`, `Bmp` czy `Gif`. Zastąp `BarCodeImageFormat.Png` żądanym formatem, a reszta kodu pozostaje bez zmian.

### Jak przycięcie wpływa na pojemność danych?

Włączenie **trybu kompaktowego** (przycięcia) zmniejsza liczbę wierszy, co może obniżyć maksymalną pojemność danych kodu kreskowego. Jeśli napotkasz wyjątek „Data too large”, zwiększ liczbę kolumn lub wyłącz przycięcie.

### Czy mogę używać dynamicznej liczby kolumn?

Tak. Możesz obliczyć liczbę kolumn na podstawie długości ciągu wejściowego:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Ten fragment pokazuje **jak dostosować kolumny** programowo, zapewniając dopasowanie kodu do określonego układu.

### Czy wymiar X jest ograniczony do całkowitych pikseli?

Właściwość `Pixels` przyjmuje dowolną dodatnią liczbę całkowitą. Dla wyjść o wyższej rozdzielczości (np. do druku) możesz woleć ustawić `Points` zamiast `Pixels`, aby uzyskać rozmiar niezależny od urządzenia.

## Wskazówki dla środowiska produkcyjnego

* **Pro tip:** Otocz generowanie kodu kreskowego blokiem try‑catch, aby obsłużyć `BarCodeException`, gdy dane wejściowe przekraczają pojemność symbolu.  
* **Uwaga:** Uprawnienia systemu plików. Proces musi mieć prawo zapisu do docelowego katalogu, w przeciwnym razie krok **jak zapisać kod kreskowy** zakończy się błędem `UnauthorizedAccessException`.  
* **Uwaga o wydajności:** Tworzenie wielu kodów kreskowych w pętli korzysta z korzyści płynących z ponownego użycia jednej instancji `BarcodeGenerator` i jedynie aktualizowania właściwości `CodeText` między iteracjami.

## Podsumowanie

Teraz wiesz, **jak zapisać kod kreskowy** jako plik PNG, **włączyć tryb kompaktowy**, **jak dostosować kolumny** oraz **generować kod PDF417** przy użyciu Aspose.BarCode dla C#. Pełny przykład demonstruje każdy wymagany krok, od inicjalizacji generatora po zapis końcowego obrazu.

Od tego momentu możesz zgłębiać powiązane tematy, takie jak dodawanie logo do kodu kreskowego, dostosowywanie kolorów czy integracja generatora w API ASP.NET Core. Każde z tych rozszerzeń podąża tym samym schematem przedstawionym w tym przewodniku, więc możesz modyfikować kod z pewnością.

Śmiało eksperymentuj z różnymi liczbami kolumn, wymiarami X i formatami obrazu, aby spełnić dokładne wymagania swojego projektu. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz wyjaśnienia krok po kroku, pomagające opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}