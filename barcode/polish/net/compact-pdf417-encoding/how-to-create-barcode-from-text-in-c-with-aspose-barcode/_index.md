---
category: general
date: 2026-10-02
description: Utwórz kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak wygenerować kod kreskowy PDF417 i zobacz, jak wygenerować kod kreskowy
  PDF417 w trybie kompaktowym.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: pl
lastmod: 2026-10-02
og_description: Utwórz kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Ten
  przewodnik pokazuje, jak wygenerować kod kreskowy PDF417 oraz jak wygenerować kod
  kreskowy PDF417 w trybie kompaktowym.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Utwórz kod kreskowy z tekstu w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak utworzyć kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć kod kreskowy z tekstu** w aplikacji .NET, ten przewodnik przeprowadzi Cię przez cały proces. Zobaczysz gotowy do uruchomienia przykład, który **generuje kod kreskowy PDF417** i także odpowie na pytanie **jak wygenerować kod kreskowy PDF417** w kompaktowym układzie.

Generowanie kodu kreskowego programowo eliminuje ręczne kroki i zapewnia spójność we wszystkich dokumentach. Po zakończeniu tego samouczka będziesz mieć plik PNG zawierający kod kreskowy PDF417, który możesz osadzić w fakturach, biletach lub kartach identyfikacyjnych.

## Czego będziesz potrzebować

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7.2+)
- Visual Studio 2022 lub dowolny edytor obsługujący C#
- Licencja NuGet na **Aspose.BarCode for .NET** (bezpłatna wersja próbna wystarczy do testów)

> **Pro tip:** Dodaj pakiet NuGet za pomocą CLI, aby utrzymać projekt w czystości:  
> `dotnet add package Aspose.BarCode`

## Krok 1: Utwórz projekt konsolowy

Utwórz nową aplikację konsolową i odwołaj się do biblioteki Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Polecenie `dotnet new console` generuje plik `Program.cs`, który zamienimy na pełny przykład poniżej.

## Krok 2: Jak utworzyć kod kreskowy z tekstu – kod podstawowy

Otwórz `Program.cs` i zamień jego zawartość na poniższy kod. Każda linia jest skomentowana, aby wyjaśnić, dlaczego istnieje.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Dlaczego każde ustawienie ma znaczenie

| Ustawienie | Cel |
|------------|-----|
| `EncodeTypes.Pdf417` | Wybiera symbologię PDF417, która może przechowywać duże ilości danych w dwuwymiarowej macierzy. |
| `XDimension.Pixels = 2` | Kontroluje szerokość każdego modułu; wartość 2 piksele zapewnia równowagę między czytelnością a rozmiarem pliku. |
| `Pdf417.Columns = 3` | Zmniejsza liczbę kolumn, czyniąc kod kreskowy bardziej zwartym bez utraty danych. |
| `Pdf417.Truncate = true` | Aktywuje tryb kompaktowy, usuwając niepotrzebne wypełnienie i skracając kod kreskowy. |
| `BarCodeImageFormat.Png` | PNG zachowuje jakość bezstratną, idealną do dalszego przetwarzania lub drukowania. |

## Krok 3: Generowanie kodu kreskowego PDF417 – uruchomienie przykładu

Zbuduj i uruchom projekt:

```bash
dotnet run
```

Po zakończeniu wykonania zobaczysz:

```
Barcode saved to CompactPdf417.png
```

Otwórz `CompactPdf417.png`, aby zobaczyć wynik. Obraz zawiera kod kreskowy PDF417, który koduje ciąg **Åspóse.Barcóde©**.

![Przykład tworzenia kodu kreskowego z tekstu](barcode-example.png)

*Tekst alternatywny: tworzenie kodu kreskowego z tekstu – kod PDF417 zapisany jako PNG*

## Krok 4: Jak wygenerować kod kreskowy PDF417 z niestandardową korekcją błędów (opcjonalnie)

Jeśli środowisko skanowania jest zaszumione, możesz zwiększyć poziom korekcji błędów:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Zwiększenie poziomu korekcji powoduje, że kod kreskowy jest większy, ale zwiększa odporność na uszkodzenia.

## Krok 5: Typowe pułapki i obsługa przypadków brzegowych

1. **Invalid characters** – PDF417 obsługuje Unicode, ale niektóre starsze skanery mogą odrzucać symbole nie‑ASCII. Przetestuj na docelowym sprzęcie.
2. **File path permissions** – Upewnij się, że katalog, do którego zapisujesz, jest zapisywalny; w przeciwnym razie `Save` zgłosi `UnauthorizedAccessException`.
3. **Image size** – Bardzo wysokie wartości `XDimension` generują duże pliki PNG. Utrzymuj rozmiar pikseli między 1 a 4 dla większości scenariuszy wyświetlania na ekranie.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy z tekstu** w C# przy użyciu Aspose.BarCode, jak **generować kod kreskowy PDF417** w kompaktowym układzie oraz dokładne kroki, **jak wygenerować kod kreskowy PDF417** z niestandardowymi ustawieniami. Pełny, działający kod powyżej można skopiować do dowolnego projektu .NET i dostosować do różnych danych wejściowych lub formatów wyjściowych (np. JPEG, BMP).

## Kolejne kroki

- Zbadaj inne symbologie, takie jak QR Code lub Code128, zmieniając `EncodeTypes`.
- Zintegruj wygenerowany PNG z PDF przy użyciu Aspose.PDF do kompleksowego tworzenia dokumentów.
- Eksperymentuj z `generator.Parameters.Barcode.Pdf417.Rows`, aby kontrolować gęstość pionową.

Śmiało modyfikuj przykład, osadzaj kod kreskowy w własnych aplikacjach i dziel się wynikami ze społecznością. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 w C# – przykład kompaktowy](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Jak utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}