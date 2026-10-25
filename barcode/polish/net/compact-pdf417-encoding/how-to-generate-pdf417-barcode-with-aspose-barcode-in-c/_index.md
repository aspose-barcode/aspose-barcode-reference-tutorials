---
category: general
date: 2026-10-24
description: Dowiedz się, jak generować kod kreskowy PDF417 przy użyciu Aspose.BarCode
  w C# z ustawieniami kompaktowymi oraz kontrolą XDimension kodu kreskowego.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: pl
lastmod: 2026-10-24
og_description: Generuj kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Skorzystaj
  z tego pełnego przewodnika, aby tworzyć kompaktowe obrazy PDF417, kontrolować XDimension
  i ustawiać kolumny.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Generuj kod kreskowy PDF417 przy użyciu Aspose.BarCode – krok po kroku w
  C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Jak wygenerować kod kreskowy PDF417 przy użyciu Aspose.BarCode w C#
url: /pl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy PDF417 przy użyciu Aspose.BarCode w C#

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz, jak Aspose.BarCode upraszcza proces, jednocześnie dając precyzyjną kontrolę nad **compact PDF417**, **barcode XDimension** i **PDF417 columns**.

Tworzenie kodu kreskowego to częsty wymóg systemów inwentaryzacyjnych, platform biletowych i przepływów dokumentów. Po zakończeniu tego tutorialu będziesz mieć samodzielny program w C#, który generuje wyraźny obraz PNG kodu PDF417, gotowy do osadzenia w dowolnym interfejsie lub wydrukowania na etykiecie.

## Czego będziesz potrzebować

- .NET 6.0 SDK lub nowszy (kod działa także z .NET Framework 4.6+)
- Visual Studio 2022 lub dowolny edytor C#, którego używasz
- Ważna licencja Aspose.BarCode for .NET (bezpłatna wersja próbna wystarczy do rozwoju)
- Podstawowa znajomość składni C#

> **Pro tip:** Jeśli testujesz Aspose.BarCode, pobierz wersję próbną ze strony producenta i dodaj pakiet NuGet `Aspose.BarCode` do swojego projektu. Wersja próbna dodaje mały znak wodny do wygenerowanego obrazu, który znika po zastosowaniu licencji.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz terminal w folderze rozwiązania i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie pobiera najnowszą stabilną wersję (stan na październik 2026, wersja 23.12). Dodanie pakietu przywraca przestrzeń nazw `Aspose.BarCode.Generation`, której użyjesz do **generowania obrazów kodu PDF417**.

## Krok 2: Utwórz podstawowy projekt konsolowy C#

Jeśli nie masz jeszcze projektu, utwórz go:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Otwórz `Program.cs`. Szablon już zawiera metodę `Main`, w której umieścimy kod generujący kod kreskowy.

## Krok 3: Zainicjalizuj generator kodu kreskowego

Najpierw zaimportuj wymaganą przestrzeń nazw:

```csharp
using Aspose.BarCode.Generation;
```

Następnie, wewnątrz `Main`, utwórz instancję `BarcodeGenerator` z symbologią PDF417 i danymi, które chcesz zakodować:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Ciąg znaków zawiera znaki Unicode, aby pokazać, że Aspose.BarCode prawidłowo obsługuje dane nie‑ASCII. Jeśli potrzebujesz tylko ASCII, zamień tekst na dowolny zwykły ciąg.

## Krok 4: Dostosuj XDimension kodu kreskowego (rozmiar modułu)

**barcode XDimension** określa szerokość najmniejszego paska (modułu). Ustawienie go w pikselach daje precyzyjną kontrolę nad ostatecznym rozmiarem obrazu:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Wartość `2` piksele zapewnia kompaktowy obraz bez utraty niezawodności skanowania. Zwiększ ją, aby uzyskać większe kody kreskowe, lub zmniejsz, aby uzyskać bardzo gęste układy.

## Krok 5: Skonfiguruj opcje compact PDF417

Dwa ustawienia specyficzne dla PDF417 znacząco wpływają na rozmiar wizualny:

| Ustawienie | Znaczenie | Typowa wartość dla wyjścia kompaktowego |
|------------|-----------|------------------------------------------|
| `Columns` | Liczba kolumn danych | `3` |
| `Truncate` (tryb kompaktowy) | Pomija prawą strefę ciszy i zmniejsza liczbę wierszy | `true` |

Zastosuj je w następujący sposób:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Użycie **PDF417 columns** ustawionych na `3` razem z `Truncate = true` tworzy *compact PDF417* kod, który mieści się na standardowej etykiecie, a jednocześnie jest czytelny dla większości skanerów.

## Krok 6: Zapisz obraz kodu kreskowego

Na koniec zapisz kod kreskowy na dysku. Przykład zapisuje PNG, ale Aspose.BarCode obsługuje także BMP, JPEG, GIF, TIFF i SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Stała `BarCodeImageFormat.Png` instruuje bibliotekę, aby wyprodukowała bezstratny PNG, co jest idealne do dalszego przetwarzania lub druku.

## Pełny, gotowy do uruchomienia kod źródłowy

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Uruchomienie programu tworzy plik `CompactPdf417.png` w katalogu głównym projektu. Otwórz go w dowolnym przeglądarce obrazów; zobaczysz ściśle upakowany kod PDF417, który koduje ciąg *Åspóse.Barcóde©*.

![Screenshot of generated PDF417 barcode using Aspose.BarCode](placeholder-image.png "Generated PDF417 barcode")

*Image alt text: Screenshot of generated PDF417 barcode using Aspose.BarCode* – ten tekst alternatywny zawiera główne słowo kluczowe dla dostępności i SEO.

## Weryfikacja wyniku

1. Otwórz plik PNG. Kod kreskowy powinien składać się z trzech pionowych kolumn danych z kompaktowym układem (bez dodatkowych stref ciszy po prawej stronie).
2. Zeskanuj obraz smartfonem z aplikacją obsługującą PDF417. Zdekodowany tekst musi odpowiadać pierwotnemu ciągowi wejściowemu.
3. Jeśli skanowanie się nie powiedzie, spróbuj zwiększyć `XDimension.Pixels` do `3` lub `4`. Większe moduły poprawiają czytelność na urządzeniach o niskiej rozdzielczości.

## Typowe warianty i przypadki brzegowe

### 1. Zmiana formatu obrazu

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG jest wektorowy, co utrzymuje ostrość kodu przy dowolnym poziomie powiększenia — przydatny dla stron internetowych.

### 2. Kodowanie dużych ilości danych

PDF417 może przechowywać do ~1,1 KB tekstu. Gdy ładunek przekracza pojemność trzech kolumn, biblioteka automatycznie dodaje wiersze. Aby zachować kod kompaktowy, możesz:

- Zmniejszyć długość danych (np. użyć identyfikatora zamiast pełnej wiadomości)
- Zwiększyć liczbę **PDF417 columns** (np. `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Użycie licencji w celu usunięcia znaku wodnego wersji próbnej

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Umieść plik licencji obok pliku wykonywalnego. Po zastosowaniu licencji wygenerowany obraz nie będzie zawierał znaku wodnego.

### 4. Obsługa wyjątków

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Typowe błędy to brak odpowiednich uprawnień do zapisu lub nieobsługiwany format obrazu.

## Dlaczego te ustawienia są ważne

- **barcode XDimension** – Kontroluje wizualną wagę każdego paska. Zbyt mały sprawia, że kod jest nieczytelny; zbyt duży marnuje miejsce.
- **PDF417 columns** – Mniej kolumn daje węższy kod, ale zwiększa liczbę wierszy.

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 przy użyciu Aspose – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generowanie kodu PDF417 z ustawieniami kompaktowymi w C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Jak zapisać kod kreskowy i wygenerować PDF417 przy użyciu Aspose w C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}