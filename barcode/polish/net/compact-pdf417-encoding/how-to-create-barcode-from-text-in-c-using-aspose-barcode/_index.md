---
category: general
date: 2026-10-28
description: Utwórz kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak wygenerować obraz kodu PDF417, ustawić liczbę kolumn, dostosować wymiar
  X oraz włączyć tryb kompaktowy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: pl
lastmod: 2026-10-28
og_description: Utwórz kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode. Ten
  samouczek pokazuje, jak wygenerować obraz kodu PDF417, dostosować rozmiar, liczbę
  kolumn oraz tryb kompaktowy.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Utwórz kod kreskowy z tekstu w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Jak utworzyć kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode
url: /pl/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy z tekstu w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć kod kreskowy z tekstu** w aplikacji .NET, ten przewodnik zapewnia gotowe rozwiązanie do uruchomienia. Zobaczysz, jak **generować obrazy kodu kreskowego PDF417**, kontrolować szerokość modułu, liczbę kolumn i włączyć tryb kompaktowy bez opuszczania IDE.

Samouczek obejmuje wszystko, co potrzebne do **generowania kodu kreskowego C#**, od instalacji biblioteki po zapisanie finalnego pliku PNG. Po zakończeniu możesz osadzić wysokiej gęstości kod kreskowy PDF417 w raportach, biletach lub etykietach inwentaryzacyjnych.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolny edytor obsługujący .NET)  
* Dostęp do Internetu w celu pobrania pakietu NuGet Aspose.BarCode for .NET  

Te elementy wystarczą, aby skompilować i uruchomić przykład na Windows, Linux lub macOS.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Biblioteka napędzająca generowanie kodów kreskowych to **Aspose.BarCode for .NET**. Zainstaluj ją za pomocą .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, która zawiera klasę `BarcodeGenerator` używaną w całym tym samouczku.

## Krok 2: Utwórz projekt konsolowy i dodaj kod

Utwórz nowy projekt konsolowy i zamień wygenerowany plik `Program.cs` na poniższy kod. Program demonstruje, jak **utworzyć kod kreskowy z tekstu** i zapisać go jako **obraz kodu kreskowego PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Dlaczego każdy wiersz ma znaczenie

* **`EncodeTypes.Pdf417`** wybiera symbologię PDF417, która jest idealna do kodowania dużych ilości danych w dwuwymiarowym formacie.  
* **`XDimension.Pixels = 2`** zmniejsza szerokość modułu, czyniąc kod kreskowy bardziej gęstym i lepiej dopasowanym do ograniczonej przestrzeni.  
* **`Pdf417.Columns = 3`** kontroluje liczbę pionowych kolumn danych; mniejsza liczba daje wyższy, ale węższy kod kreskowy.  
* **`Pdf417.Truncate = true`** aktywuje tryb kompaktowy, przycinając nieużywane kolumny po prawej stronie. To kluczowe ustawienie, które zamienia zwykły PDF417 w **obraz kodu kreskowego kompaktowego PDF417**.  

## Krok 3: Zbuduj i uruchom projekt

Wykonaj następujące polecenia w katalogu projektu:

```bash
dotnet build
dotnet run
```

Po zakończeniu programu zobaczysz komunikat w konsoli potwierdzający lokalizację pliku. Otwórz `CompactPdf417.png` w dowolnej przeglądarce obrazów, aby zweryfikować wynik.

**Oczekiwany wynik** – PNG o wysokim kontraście pokazujący kompaktowy kod PDF417, który koduje ciąg `Åspóse.Barcóde©`. Zeskanowanie obrazu standardowym czytnikiem kodów kreskowych zwraca oryginalny tekst, potwierdzając, że **generate pdf417 barcode** zakończyło się sukcesem.

## Krok 4: Dostosowywanie kodu kreskowego do różnych scenariuszy

Chociaż przykład używa stałej liczby kolumn i wymiaru X, możesz dostosować generator do innych wymagań:

| Scenariusz | Dostosowanie |
|------------|--------------|
| Większy ładunek danych | Zwiększ `Pdf417.Columns` lub ustaw `Pdf417.Rows` ręcznie |
| Wyższa niezawodność skanowania | Zwiększ `XDimension.Pixels` do 3 lub 4 |
| Inny format obrazu | Zastąp `BarCodeImageFormat.Png` przez `Jpeg` lub `Bmp` |
| Przezroczyste tło | Ustaw `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Te opcje pozwalają Ci **generate barcode C#** rozwiązania, które pasują do aplikacji mobilnych, raportów desktopowych lub usług sieciowych.

## Krok 5: Obsługa przypadków brzegowych i najlepsze praktyki

* **Wsparcie Unicode** – Generator automatycznie koduje znaki Unicode, ale upewnij się, że Twój ciąg źródłowy jest zakodowany w UTF‑8, jeśli odczytujesz go z pliku.  
* **Duży tekst** – PDF417 może zakodować do 1850 znaków alfanumerycznych. Jeśli przekroczysz ten limit, biblioteka zgłosi wyjątek; podziel dane na wiele kodów kreskowych lub przejdź na symbologię o większej pojemności.  
* **Obsługa błędów** – Otocz kod generujący w blok `try/catch`, aby przechwycić `BarCodeException` i dostarczyć przyjazny komunikat o błędzie.  
* **Wydajność** – Generowanie wielu kodów kreskowych w pętli korzysta z ponownego użycia jednej instancji `BarcodeGenerator` i jedynie aktualizacji `CodeText` pomiędzy iteracjami.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Pełny listing źródłowy

Poniżej znajduje się kompletny, samodzielny program, który możesz skopiować do `Program.cs`. Nie są wymagane żadne dodatkowe pliki.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Uruchomienie tego programu tworzy **pdf417 barcode image** pokazany na ilustracji poniżej.

![Kompaktowy kod PDF417 utworzony z tekstu przy użyciu C#](/images/compact-pdf417.png){.img-fluid alt="przykład tworzenia kodu kreskowego z tekstu pokazujący kompaktowy obraz kodu PDF417"}

*Opis obrazu: Plik PNG wyświetla kompaktowy kod PDF417, który koduje ciąg „Åspóse.Barcóde©”.*  

## Zakończenie

Teraz wiesz, jak **utworzyć kod kreskowy z tekstu** w C# i wyprodukować **obraz kodu kreskowego PDF417** z niestandardowymi wymiarami oraz trybem kompaktowym. Przykład demonstruje kluczowe kroki do **generate barcode C#**, obsługi danych Unicode i dostosowywania parametrów wizualnych dla różnych scenariuszy wdrożeniowych.

Następnie zapoznaj się z powiązanymi tematami, takimi jak **generate QR code in C#**, **add barcode to PDF documents**, lub **embed barcodes in ASP.NET Core APIs**. Każdy z nich opiera się na tych samych podstawach `BarcodeGenerator` omówionych tutaj.

Miłego kodowania i przyjemnego integrowania kodów kreskowych w rozwiązaniach .NET!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które budują na technikach przedstawionych w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj kod PDF417 w C# – Utwórz kod PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Jak wygenerować kod PDF417 przy użyciu Aspose.BarCode w C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Jak utworzyć obraz kodu PDF417 w C# – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}