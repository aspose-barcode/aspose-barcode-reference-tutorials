---
category: general
date: 2026-10-15
description: Utwórz kod kreskowy PNG w C# z przykładem kompaktowego PDF417 – dowiedz
  się, jak ustawić kolumny, dostosować wymiary i wygenerować obraz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: pl
lastmod: 2026-10-15
og_description: Utwórz kod kreskowy PNG w C# z przykładem kompaktowego PDF417. Ten
  przewodnik pokazuje, jak ustawić kolumny, dostosować wymiary i zapisać obraz.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Tworzenie kodu kreskowego PNG w C# – kompletny poradnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Jak stworzyć plik PNG z kodem kreskowym w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć plik PNG z kodem kreskowym w C# – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć plik PNG z kodem kreskowym** z kodu C#, ten tutorial pokaże Ci kompletną rozwiązanie w zaledwie kilku linijkach. Zobaczysz, jak ustawić kolumny, dostosować rozmiar modułu i zapisać kompaktowy kod PDF417 jako obraz PNG — wszystko w jednym, łatwym do zrozumienia przykładzie.

Generowanie kodów kreskowych programowo eliminuje ręczny krok użycia edytora graficznego i pozwala osadzać kody kreskowe bezpośrednio w fakturach, biletach lub etykietach inwentaryzacyjnych. W kolejnych sekcjach omówimy wszystko, co musisz wiedzieć, aby **utworzyć kod kreskowy** w formie obrazów, dlaczego każda konfiguracja ma znaczenie oraz jak dostosować kod do różnych przypadków użycia.

## Wymagania wstępne

* .NET 6.0 lub nowszy (kod działa również z .NET Framework 4.7+)
* Odwołanie do biblioteki kodów kreskowych obsługującej PDF417, takiej jak **Aspose.BarCode for .NET** lub **IronBarcode**. Przykład używa Aspose.BarCode, którą możesz zainstalować przez NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Podstawowa znajomość składni C# oraz Visual Studio (lub dowolnego wybranego IDE).

> **Wskazówka:** Jeśli wolisz darmową alternatywę, otwarto‑źródłowa biblioteka **ZXing.Net** również obsługuje PDF417, ale nazwy właściwości różnią się nieco. Pokazane tutaj koncepcje pozostają takie same.

## Jak utworzyć plik PNG z kodem kreskowym w C# (główny krok)

Sednem rozwiązania jest obiekt `BarcodeGenerator` skonfigurowany do kodowania PDF417. W kolejnych sekcjach rozłożymy każdy wiersz kodu, wyjaśnimy **jak ustawić kolumny** i pokażemy, dlaczego ustawienia wpływają na ostateczny rozmiar PNG.

### Krok 1: Zainicjalizuj generator kodu kreskowego z żądanym tekstem

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Dlaczego to ważne*: Enum `EncodeTypes.Pdf417` informuje bibliotekę, aby wygenerowała dwuwymiarowy, układany kod kreskowy. Konstruktor przyjmuje również dane, które chcesz zakodować, więc nie potrzebujesz osobnego wywołania `SetData`.

### Krok 2: Ustaw wymiar modułu (X) w pikselach

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Wymiar X** kontroluje gęstość wizualną kodu kreskowego. Mniejsza wartość daje bardziej zwarty obraz, co jest przydatne, gdy potrzebny jest kompaktowy PNG na ekrany mobilne lub przy ograniczonej przestrzeni drukowania.

### Krok 3: Zdefiniuj liczbę kolumn dla kodu PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Ten wiersz demonstruje **jak ustawić kolumny**. PDF417 może automatycznie wybrać optymalną liczbę kolumn, ale jawne ustawienie zapewnia przewidywaną szerokość, szczególnie gdy osadzasz PNG w układzie o stałym rozmiarze.

### Krok 4: Włącz kompaktowy układ poprzez przycięcie kodu kreskowego

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Gdy `Truncate` jest ustawione na true, biblioteka usuwa końcowe wiersze, które nie zawierają danych, zmniejszając ogólną wysokość obrazu bez utraty informacji.

### Krok 5: Zapisz obraz kodu kreskowego jako PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Metoda `Save` zapisuje kod kreskowy na dysku w określonym formacie. PNG jest bezstratny, co czyni go idealnym dla aplikacji skanujących, które wymagają precyzyjnego wykrywania krawędzi.

### Pełny, gotowy do uruchomienia przykład

Łącząc wszystko razem, oto samodzielny program, który możesz skopiować, wkleić i uruchomić:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Oczekiwany wynik** – Po uruchomieniu programu znajdziesz plik `CompactPdf417.png` w folderze wykonywania. Obraz zawiera trzy‑kolumnowy kod PDF417, który jest na tyle kompaktowy, że zmieści się na standardowej etykiecie 2 × 2 cm, pozostając w pełni skanowalnym.

![Przykład tworzenia kodu kreskowego PNG](placeholder.png){alt="Utworzyć kod kreskowy PNG przy użyciu C#"}

## Jak ustawić kolumny dla różnych rozmiarów danych (słowo kluczowe drugorzędne)

Liczba kolumn wpływa zarówno na szerokość, jak i czytelność kodu kreskowego:

| Kolumny | Przybliżona szerokość (px) | Typowe zastosowanie |
|--------|----------------------------|----------------------|
| 1‑2    | Wąska, wysoka               | Małe etykiety, wydruki podobne do RFID |
| 3‑5    | Zrównoważona                | Etykiety uniwersalne |
| 6‑9    | Szeroka, niska               | Duże plakaty lub opakowania |

Jeśli ciąg danych rośnie, biblioteka może automatycznie zwiększyć liczbę wierszy, aby utrzymać kod kreskowy w granicach limitu kolumn. Jednak wymuszenie zbyt niskiej liczby kolumn może spowodować, że kod stanie się nadmiernie wysoki, co może nie zmieścić się na drukarce paragonów. Dostosuj liczbę kolumn w zależności od fizycznych ograniczeń nośnika wyjściowego.

## Jak utworzyć obrazy kodów kreskowych w innych formatach (słowo kluczowe drugorzędne)

Chociaż PNG jest najczęściej używanym formatem w sieci i na urządzeniach mobilnych, możesz potrzebować **utworzyć kod kreskowy** w formatach JPEG, BMP lub SVG dla specjalistycznych przepływów pracy:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

* **PNG** – bezstratny, idealny dla skanerów.
* **JPEG** – mniejszy rozmiar pliku, akceptowalny, gdy drobne artefakty kompresji są dopuszczalne.
* **SVG** – doskonały do druku wysokiej rozdzielczości lub skalowania interfejsu UI.

## Przykład kodu kreskowego w C#: obsługa błędów i przypadków brzegowych

Solidny **przykład kodu kreskowego w C#** powinien przewidywać problemy w czasie wykonywania:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Dlaczego opakować w `try/catch`?* Nieprawidłowe znaki w tekście, nieobsługiwane wymiary lub problemy z uprawnieniami do zapisu spowodują wyrzucenie wyjątków. Ich eleganckie obsłużenie zapobiega awarii aplikacji podczas przetwarzania wsadowego.

## Rozszerzenie przykładu: dodanie logo lub tła

Wiele rzeczywistych scenariuszy wymaga nałożenia logo lub kolorowego tła. API Aspose.BarCode pozwala połączyć kod kreskowy z bitmapą:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Ta technika zachowuje przepływ pracy **tworzenia kodu kreskowego PNG** niezmieniony, jednocześnie wzbogacając wizualną identyfikację końcowego obrazu.

## Podsumowanie

W tym przewodniku pokazaliśmy, jak **utworzyć plik PNG z kodem kreskowym** w C# używając kompaktowej konfiguracji PDF417. Nauczyłeś się:

* Dokładny kod potrzebny do zainicjalizowania `BarcodeGenerator`.
* **Jak ustawić kolumny** i dlaczego liczba kolumn ma znaczenie dla rozmiaru i czytelności.
* Jak dostosować wymiar X i włączyć przycinanie, aby uzyskać bardziej zwarty PNG.
* Sposoby zapisu obrazu w formatach PNG, JPEG lub SVG.
* Wzorce obsługi błędów dla gotowego do produkcji **przykładu kodu kreskowego w C#**.
* Opcjonalne rozszerzenia, takie jak nałożenie logo i dostosowanie tła.

Masz teraz gotowy do uruchomienia fragment kodu, który możesz zintegrować z generatorami faktur, systemami biletowymi lub narzędziami do zarządzania zapasami. Eksperymentuj z różnymi wartościami kolumn, rozmiarami modułów lub typami kodów kreskowych (np. QR, Code128), aby zobaczyć, jak zmienia się obraz.

## Kolejne kroki

* Zbadaj inne typy kodowania (`EncodeTypes.QR`, `EncodeTypes.Code128`), aby objąć więcej przypadków użycia.
* Połącz generowanie kodów kreskowych z bibliotekami tworzącymi PDF (np. **iTextSharp**), aby osadzić PNG bezpośrednio w dokumentach.
* Zbadaj dynamiczne rozmiarowanie: oblicz optymalną liczbę kolumn w zależności od długości ciągu wejściowego i docelowych wymiarów etykiety.

Miłego kodowania i ciesz się prostotą programowego generowania wyraźnych kodów kreskowych PNG w C#!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod PDF417 i zapisać go jako PNG w C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Jak utworzyć kod PDF417 i ustawić jego rozmiar w C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Jak utworzyć kod PDF417 w C# w trybie kompaktowym](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}