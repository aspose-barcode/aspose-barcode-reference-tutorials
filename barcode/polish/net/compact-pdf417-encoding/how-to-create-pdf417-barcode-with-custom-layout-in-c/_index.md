---
category: general
date: 2026-11-14
description: Dowiedz się, jak szybko tworzyć kod kreskowy PDF417 w C#. Ten przewodnik
  pokazuje również, jak generować PDF417 oraz jak dostosować ustawienia PDF417, aby
  uzyskać precyzyjną kontrolę.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: pl
lastmod: 2026-11-14
og_description: Utwórz kod kreskowy PDF417 w C# z instrukcjami krok po kroku. Dowiedz
  się, jak generować PDF417 i jak dostosować parametry PDF417, aby uzyskać dokładne
  wyniki.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Tworzenie kodu kreskowego PDF417 w C# – pełny przewodnik z niestandardowym
  układem
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Jak utworzyć kod kreskowy PDF417 z niestandardowym układem w C#
url: /pl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy PDF417 z niestandardowym układem w C#

Jeśli potrzebujesz **create pdf417 barcode** dla systemu biletowego, etykiety inwentaryzacyjnej lub skanowania w aplikacji mobilnej, ten tutorial pokazuje kompletny proces. Zobaczysz, jak szybko wygenerować PDF417 oraz jak dostosować ustawienia PDF417, takie jak kolumny i wiersze, aby kod kreskowy pasował do Twoich ograniczeń projektowych.

Generowanie kodu kreskowego nie wymaga skomplikowanej biblioteki graficznej — wystarczy Aspose.BarCode for .NET (lub dowolne kompatybilne API). Po zakończeniu tego przewodnika będziesz mieć gotowy plik PNG, który możesz osadzić w PDF‑ach, stronach internetowych lub wydrukować bezpośrednio z aplikacji.

## Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
- Aspose.BarCode for .NET (pakiet NuGet `Aspose.BarCode`)
- Podstawowa znajomość C# i Visual Studio (lub dowolnego IDE)

> **Pro tip:** Jeśli używasz potoku CI/CD, dodaj odwołanie do pakietu NuGet w pliku projektu, aby kompilacje były powtarzalne.

## Krok 1: Zainstaluj bibliotekę kodów kreskowych

Otwórz folder projektu w terminalu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet zawiera klasę `BarcodeGenerator` używaną w całym tutorialu. Nie są wymagane dodatkowe natywne zależności.

## Krok 2: Utwórz podstawowy kod kreskowy PDF417

Pierwszym celem jest **create pdf417 barcode** z ustawieniami domyślnymi. Poniższy program konfiguruje generator, koduje przykładowy ciąg znaków i zapisuje wynik jako obraz PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Dlaczego to działa:**  
`EncodeTypes.Pdf417` informuje bibliotekę, aby użyła symbologii PDF417. Konstruktor automatycznie tworzy obiekt `Barcode` z domyślnymi wartościami kolumn/wierszy, które zapewniają możliwość skanowania w większości przypadków.

Uruchom program (`dotnet run`). Znajdziesz plik `Pdf417Default.png` w folderze projektu. Otworzenie obrazu pokazuje standardowy kod kreskowy PDF417 gotowy do skanowania.

![Przykład tworzenia kodu kreskowego PDF417](https://example.com/images/pdf417-default.png){:alt="Przykład tworzenia kodu kreskowego PDF417 pokazujący domyślny układ"}

## Krok 3: Jak wygenerować PDF417 o niestandardowych wymiarach

Czasami etykieta o stałym rozmiarze lub komponent UI wymaga określonego rozmiaru kodu kreskowego. Wtedy **how to generate pdf417** z niestandardowymi kolumnami i wierszami staje się niezbędne.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Dlaczego możesz tego potrzebować:**  
- **Ograniczona szerokość:** Zmniejszenie liczby kolumn i zwiększenie liczby wierszy tworzy szerszy, ale krótszy kod kreskowy, idealny dla wąskich etykiet.  
- **Ograniczona wysokość:** Zwiększenie liczby kolumn i zmniejszenie liczby wierszy daje wyższy, węższy kod kreskowy, przydatny gdy masz pionową przestrzeń.

Zarówno `Columns`, jak i `Rows` akceptują tylko wartości mieszczące się w udokumentowanych zakresach (2‑30 dla kolumn, 1‑90 dla wierszy). Podanie wartości spoza zakresu powoduje wyrzucenie `ArgumentOutOfRangeException`, więc zawsze waliduj dane wejściowe użytkownika, jeśli udostępniasz te ustawienia w interfejsie.

## Krok 4: Jak dalej dostosować PDF417

Poza kolumnami i wierszami, symbologia PDF417 oferuje wiele opcjonalnych parametrów:

| Właściwość | Cel | Typowe wartości |
|------------|-----|-----------------|
| `ErrorLevel` | Kontroluje zdolność korekcji błędów | 0‑8 (wyższy = bardziej odporny) |
| `MacroPdf417` | Włącza macro PDF417 dla danych wielosegmentowych | `true`/`false` |
| `CompactPdf417` | Tworzy bardziej kompaktowy kod kreskowy kosztem zmniejszonej korekcji błędów | `true`/`false` |
| `SecurityLevel` | Dodaje cyfrę kontrolną bezpieczeństwa | 0‑2 |

Oto szybki przykład, który dodatkowo ustawia poziom błędu na maksymalny (8) dla hałaśliwego otoczenia:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Dlaczego to ma znaczenie:**  
Wyższa korekcja błędów pozwala skanerom odzyskać dane, nawet jeśli część kodu kreskowego jest uszkodzona. Jednak zwiększa to również rozmiar kodu, więc należy wyważyć to ustawienie względem ograniczeń układu.

## Krok 5: Zweryfikuj działanie kodu kreskowego

Po wygenerowaniu pliku PNG przetestuj go dowolną aplikacją do skanowania kodów kreskowych (większość smartfonów ma darmowe czytniki PDF417). Jeśli skaner zwróci oryginalny tekst (`Custom layout text`), kod kreskowy jest prawidłowy.

Jeśli napotkasz problemy ze skanowaniem:
1. **Sprawdź wymiary:** Upewnij się, że kolumny/wiersze mieszczą się w dozwolonym zakresie.  
2. **Dostosuj poziom błędu:** Zwiększ `ErrorLevel` dla uszkodzonych nośników.  
3. **Sprawdź jakość obrazu:** Zapisz z wyższą rozdzielczością DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) jeśli planujesz druk.

## Pełny kod źródłowy pomocnika wielokrotnego użytku

Poniżej znajduje się kompaktowa, wielokrotnego użytku klasa, którą możesz dodać do dowolnego projektu .NET. Zawiera **how to generate pdf417** i **how to customize pdf417** w jednej metodzie.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Możesz wywołać tego pomocnika w następujący sposób:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Metoda ukrywa powtarzalny kod szkieletowy, pozwalając skupić się na logice biznesowej.

## Częste pułapki i jak ich unikać

- **Wartości poza zakresem:** Zawsze waliduj `columns` i `rows` przed ich przypisaniem.  
- **Nieprawidłowy format obrazu:** Niektóre starsze skanery akceptują tylko BMP lub JPEG. Użyj `BarCodeImageFormat.Bmp` w razie potrzeby.  
- **Niska rozdzielczość DPI przy druku:** Domyślne DPI to 96. Dla wysokiej jakości wydruków, jawnie ustaw wyższą wartość DPI (np. 300) przy wywoływaniu `Save`.  
- **Brak wsparcia czcionki:** PDF417 koduje dane binarne, więc zazwyczaj nie musisz określać czcionki. Jednak jeśli nakładasz tekst na obraz, upewnij się, że czcionka jest zainstalowana na docelowym komputerze.

## Zakończenie

Teraz wiesz, jak **create pdf417 barcode** od początku do końca, jak **generate pdf417** z niestandardowymi ustawieniami kolumn/wierszy oraz jak **customize pdf417** pod kątem korekcji błędów i kompaktowości. Stosując wzorzec wielokrotnego użytku możesz generować kody kreskowe na żądanie, dopasowywać je do dowolnych ograniczeń układu i zapewnić niezawodne skanowanie w środowiskach produkcyjnych.

**Kolejne kroki**

- Zbadaj inne symbologie, takie jak QR lub Code128, używając tej samej klasy `BarcodeGenerator`.  
- Połącz wyjście PNG z biblioteką generowania PDF (np. iText7), aby osadzać kody kreskowe w fakturach.  
- Eksperymentuj z `MacroPdf417` w celu transmisji danych wielosegmentowych, funkcji przydatnej w logistyce i aplikacjach transportowych.

Szczęśliwego kodowania i niech Twoje kody kreskowe zawsze skanują się za pierwszym razem!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak wygenerować kod kreskowy i dostosować kod kreskowy PDF417 w C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Jak utworzyć kod kreskowy PDF417 i wyeksportować PNG w C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}