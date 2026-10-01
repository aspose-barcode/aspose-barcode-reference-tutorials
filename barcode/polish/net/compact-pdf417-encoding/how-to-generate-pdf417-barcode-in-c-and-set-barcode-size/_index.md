---
category: general
date: 2026-08-22
description: Dowiedz się, jak generować kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode,
  ustawiać rozmiar kodu, regulować kolumny i włączać tryb kompaktowy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: pl
lastmod: 2026-08-22
og_description: Generuj kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Ten przewodnik
  pokazuje, jak ustawić rozmiar kodu, kontrolować liczbę kolumn oraz włączyć tryb
  kompaktowy, aby uzyskać mniejszy obraz.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Generowanie kodu kreskowego PDF417 w C# – ustaw rozmiar, kolumny i tryb
  kompaktowy
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Jak wygenerować kod kreskowy PDF417 w C# i ustawić jego rozmiar
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 w C# i ustawić rozmiar kodu kreskowego

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik przeprowadzi Cię przez cały proces. Zobaczysz dokładnie **jak wygenerować PDF417** przy użyciu Aspose.BarCode, jak dostosować **rozmiar kodu kreskowego**, oraz jak stworzyć skompresowany PNG, który można osadzić w raportach lub aplikacjach mobilnych.

Tworzenie kodu kreskowego nie wymaga osobnego edytora graficznego. Po zakończeniu tego samouczka będziesz mieć w pełni funkcjonalną metodę w C#, która generuje obraz PDF417 o dokładnych wymiarach, które potrzebujesz, gotowy do dalszego przetwarzania.

## Czego się nauczysz

* Zainstaluj i odwołaj się do biblioteki Aspose.BarCode.
* Utwórz generator kodu kreskowego PDF417 i określ kodowany tekst.
* **Ustaw rozmiar kodu kreskowego** poprzez konfigurację wymiaru X i liczby kolumn.
* Włącz tryb kompaktowy (przycięty), aby zmniejszyć symbol.
* Zapisz wynik jako plik PNG.
* Rozwiąż typowe problemy, takie jak nieczytelne kody i zbyt duże obrazy.

### Wymagania wstępne

* .NET 6.0 lub nowszy (API działa również z .NET Framework 4.6+).
* Podstawowa znajomość C# i Visual Studio (lub dowolnego IDE C#).
* Ważna licencja Aspose.BarCode (darmowa wersja ewaluacyjna działa do testów).

> **Pro tip:** Jeśli planujesz generować wiele kodów kreskowych w pętli, ponownie używaj jednej instancji `BarcodeGenerator` i zmieniaj jedynie właściwość `CodeText`. To zmniejsza alokacje pamięci.

## Generowanie kodu kreskowego PDF417 przy użyciu Aspose.BarCode

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` dla symboliki PDF417. Ten obiekt jest punktem wejścia dla wszystkich operacji na kodach kreskowych.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Dlaczego to ważne*: `EncodeTypes.Pdf417` informuje bibliotekę, aby użyła standardu PDF417, który obsługuje duże wolumeny danych i korekcję błędów. Konstruktor przyjmuje również dane do zakodowania, eliminując potrzebę późniejszego oddzielnego przypisania `CodeText`.

## Ustaw rozmiar kodu kreskowego i liczbę kolumn

Symbole PDF417 składają się z wierszy i kolumn małych prostokątnych modułów. Kontrolowanie szerokości modułu (wymiar X) i liczby kolumn pozwala precyzyjnie dostroić całkowite wymiary.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Wyjaśnienie*:  
* **X‑dimension** (`Pixels`) określa, jak szeroki jest każdy moduł. Mniejsze wartości tworzą bardziej zwartą kod kreskowy, podczas gdy większe wartości zwiększają czytelność na skanerach o niskiej rozdzielczości.  
* **Columns** kontrolują układ poziomy. Mniej kolumn sprawia, że kod kreskowy jest wyższy; więcej kolumn sprawia, że jest szerszy. Dostosuj te dwa ustawienia razem, aby uzyskać dokładny **rozmiar kodu kreskowego**, którego potrzebujesz.

## Włącz tryb kompaktowy dla mniejszego kodu kreskowego

PDF417 zawiera tryb „compact” (lub przycięty), który usuwa niepotrzebne wypełnienie i zmniejsza ogólny rozmiar. Jest to szczególnie przydatne, gdy masz ograniczoną przestrzeń ekranu.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Dlaczego włączyć przycinanie?* Gdy `Truncate` jest ustawione na `true`, generator pomija wzorzec stopu oraz niektóre słowa korekcji błędów, które nie są wymagane w większości scenariuszy skanowania. Powstały obraz jest o około 15‑20 % mniejszy, nie poświęcając integralności danych w typowych zastosowaniach.

## Zapisz kod kreskowy jako obraz PNG

Po skonfigurowaniu rozmiaru i trybu, zapisz kod kreskowy na dysk. PNG jest bezstratny, zapewniając ostre krawędzie modułów.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Plik `CompactPdf417.png` będzie zawierał wyraźny symbol PDF417, który odpowiada wymiarom ustawionym w poprzednich krokach.

### Oczekiwany wynik

Otwarcie zapisanego pliku PNG powinno wyświetlić pionowo‑zorientowany kod kreskowy PDF417 składający się z trzech kolumn, każdy moduł ma szerokość 2 px, a całkowity rozmiar wynosi około **120 × 240 px** (szerokość × wysokość). Zeskanowanie obrazu dowolnym standardowym czytnikiem PDF417 zwróci oryginalny tekst „Sample text for PDF417”.

## Typowe pułapki i jak ich unikać

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|-----|
| Kod kreskowy jest nieczytelny | Wymiar X jest zbyt mały dla skanera | Zwiększ `XDimension.Pixels` do 3 lub 4 |
| Obraz jest zbyt szeroki dla interfejsu UI | Ustawiono zbyt wiele kolumn | Zredukuj `Pdf417.Columns` lub włącz `Truncate` |
| Wyjątek `ArgumentOutOfRangeException` | Ujemna lub zerowa liczba kolumn | Upewnij się, że `Columns` jest dodatnią liczbą całkowitą (minimum 1) |
| Plik PNG jest pusty | Ścieżka wyjściowa nie istnieje lub brak uprawnień do zapisu | Sprawdź, czy katalog istnieje i aplikacja ma prawa do zapisu |

> **Pro tip:** Użyj `barcodeGenerator.ValidateParameters()` przed wywołaniem `Save()`, aby wcześnie wykryć błędy konfiguracji.

## Pełny, działający przykład

Poniżej znajduje się samodzielny program konsolowy, który zawiera wszystkie powyższe kroki. Skopiuj go do nowego projektu C#, przywróć pakiet NuGet Aspose.BarCode i uruchom, aby zobaczyć wynik.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Uruchomienie programu** tworzy `CompactPdf417.png` w katalogu roboczym pliku wykonywalnego. Zeskanuj obraz aplikacją mobilną (np. „Barcode Scanner”), aby zweryfikować, że zakodowany tekst odpowiada źródłowemu ciągowi.

## Kolejne kroki i powiązane tematy

* **Zwiększ poziom korekcji błędów** – dostosuj `Pdf417.ErrorLevel` dla środowisk z szumem skanowania.  
* **Zmień orientację** – ustaw `Pdf417.Rotate` na `RotationAngle.Rotate90`, jeśli potrzebny jest układ poziomy.  
* **Osadź kod kreskowy w PDF** – połącz Aspose.PDF z Aspose.BarCode, aby umieścić obraz bezpośrednio w dokumencie.  
* **Generuj inne kody 2‑D** – klasa `BarcodeGenerator` obsługuje DataMatrix, QR i kody Aztec; wystarczy zamienić `EncodeTypes.Pdf417` na żądaną symbolikę.

Teraz wiesz, jak **wygenerować kod kreskowy PDF417** w C#, precyzyjnie **ustawić rozmiar kodu kreskowego**, skonfigurować kolumny, włączyć tryb kompaktowy i zapisać wynik jako PNG. Zastosuj te ustawienia, aby dopasować się do dowolnych ograniczeń UI lub wymagań skanowania, i rozszerz podejście na inne formaty kodów kreskowych w razie potrzeby. Szczęśliwego kodowania!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz szczegółowe wyjaśnienia, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 – Kompaktowe kodowanie PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak utworzyć kod kreskowy – Kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak wygenerować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – Przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}