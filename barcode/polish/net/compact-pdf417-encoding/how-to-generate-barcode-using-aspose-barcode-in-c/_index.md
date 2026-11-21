---
category: general
date: 2026-11-20
description: Dowiedz się, jak generować kod kreskowy przy użyciu Aspose.Barcode w
  C#. Ten przewodnik krok po kroku pokaże, jak utworzyć kod MicroPdf417 i zapisać
  go jako obraz PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: pl
lastmod: 2026-11-20
og_description: Jak generować kod kreskowy przy użyciu Aspose.Barcode w C#. Przejdź
  przez ten kompletny samouczek, aby stworzyć kod MicroPdf417 i wyeksportować go jako
  PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Jak wygenerować kod kreskowy przy użyciu Aspose.Barcode – krok po kroku
  przewodnik C#
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Jak wygenerować kod kreskowy przy użyciu Aspose.Barcode w C#
url: /pl/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy przy użyciu Aspose.Barcode w C#

Jeśli potrzebujesz **jak generować kod kreskowy** dla aplikacji desktopowej lub webowej, Aspose.Barcode oferuje prosty interfejs API. Ten tutorial pokazuje dokładnie, jak wygenerować kod kreskowy MicroPdf417, dostosować jego wymiary i zapisać wynik jako plik PNG. Zobaczysz również, jak **tworzyć kod kreskowy przy użyciu Aspose** dla innych formatów bez opuszczania IDE.

Generowanie kodu kreskowego jest powszechnym wymaganiem w systemach inwentaryzacji, platformach biletowych i bezpiecznych przepływach dokumentów. Po zakończeniu tego przewodnika będziesz mieć działający program, który generuje wysokiej jakości obraz kodu kreskowego gotowy do druku lub osadzenia.

## Czego będziesz potrzebować

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
* Visual Studio 2022 (lub dowolny edytor C#)
* Ważna licencja na Aspose.Barcode dla .NET – darmowa wersja próbna działa w celach rozwojowych i testowych
* Podstawowa znajomość składni C#

Nie są wymagane dodatkowe pakiety NuGet poza `Aspose.Barcode`.

## Jak generować kod kreskowy przy użyciu Aspose.Barcode

Poniższe sekcje dzielą proces na poszczególne kroki. Każdy krok wyjaśnia **dlaczego** kod jest potrzebny, a nie tylko **co** robi.

### Krok 1: Zainstaluj pakiet NuGet Aspose.Barcode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.Barcode
```

To polecenie dodaje najnowszą stabilną wersję Aspose.Barcode do pliku projektu, zapewniając dostępność klasy `BarcodeGenerator` w czasie kompilacji.

**Dlaczego to jest ważne:** Pakiet zawiera podstawowy silnik renderujący oraz zestaw predefiniowanych `EncodeTypes`. Bez niego kompilator nie może rozwiązać `BarcodeGenerator` ani `EncodeTypes`.

### Krok 2: Utwórz instancję `BarcodeGenerator` dla MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Dlaczego to jest ważne:** Konstruktor łączy symbolikę (`EncodeTypes.MicroPdf417`) z surowymi danymi, które chcesz zakodować. MicroPdf417 jest idealny, gdy potrzebny jest mniejszy rozmiar niż pełny PDF417, przy jednoczesnym wsparciu danych alfanumerycznych.

### Krok 3: Dostosuj wymiar X (szerokość modułu)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to jest ważne:** Wymiar X określa rozmiar każdej komórki kodu kreskowego. Zbyt niska wartość powoduje rozmyty obraz; zbyt wysoka sprawia, że kod kreskowy jest niepotrzebnie duży. Dwa piksele to zrównoważona domyślna wartość dla większości scenariuszy ekranowych i drukowanych.

### Krok 4: Wybierz liczbę kolumn dla komponentu PDF417

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Dlaczego to jest ważne:** MicroPdf417 wewnętrznie używa komponentu PDF417. Dostosowanie liczby kolumn wpływa na proporcje kodu kreskowego i pojemność danych. Cztery kolumny dają kompaktowy kształt przy zachowaniu czytelności.

### Krok 5: Zapisz obraz kodu kreskowego

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Dlaczego to jest ważne:** `Save` zapisuje wygenerowany kod kreskowy na dysku. PNG jest bezstratny, co zachowuje ostre krawędzie niezbędne dla skanerów. Możesz zamienić `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif`, jeśli Twój przepływ pracy wymaga innego formatu.

### Pełny kod źródłowy

Połączenie wszystkich kroków daje kompletną, samodzielną aplikację konsolową:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Uruchom program (`dotnet run`), a znajdziesz plik `MicroPdf417.png` na pulpicie. Otworzenie pliku pokaże wyraźny kod MicroPdf417, który koduje tekst `"Åspóse.Barcóde©"`.

## Weryfikacja kodu kreskowego

Aby potwierdzić, że kod kreskowy został wygenerowany poprawnie:

1. Otwórz plik PNG w dowolnej przeglądarce obrazów.
2. Użyj aplikacji mobilnej skanującej kody kreskowe, która obsługuje PDF417 lub MicroPdf417.
3. Zeskanuj obraz; aplikacja powinna wyświetlić oryginalny tekst, w tym znaki specjalne.

Jeśli skaner nie działa, sprawdź następujące elementy:

* **Wymiar X:** Wartości poniżej 1 px mogą powodować artefakty renderowania.
* **Liczba kolumn:** Wartości spoza zakresu 1‑4 wywołują wyjątek.
* **Zestaw znaków:** Aspose.Barcode obsługuje UTF‑8; upewnij się, że plik źródłowy jest zapisany w kodowaniu UTF‑8.

## Typowe wariacje i przypadki brzegowe

### Generowanie innych symbologii

Jeśli chcesz **tworzyć kod kreskowy przy użyciu Aspose** dla kodów QR, Code128 lub UPC, zamień `EncodeTypes.MicroPdf417` na odpowiednią wartość wyliczeniową, np.:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Wszystkie pozostałe kroki konfiguracyjne (wymiar X, zapisywanie) pozostają bez zmian.

### Zmiana formatu obrazu

Aspose.Barcode obsługuje wiele formatów rastrowych. Aby wyeksportować jako JPEG z jakością 90 %:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Obsługa dużych ładunków danych

MicroPdf417 może przechowywać do 1 KB danych. Dla większych ładunków przełącz się na pełny `EncodeTypes.Pdf417` i odpowiednio dostosuj `Rows` oraz `Columns`.

### Unicode i znaki specjalne

Biblioteka automatycznie koduje ciągi Unicode. Jednak niektóre starsze skanery rozpoznają tylko ASCII. Jeśli celujesz w takie urządzenia, ogranicz wejście do zakresu ASCII lub użyj innej symbologii, która zapewnia kompatybilność.

## Profesjonalne wskazówki dla środowiska produkcyjnego

* **Cache'uj generator** przy generowaniu wielu kodów kreskowych z tymi samymi ustawieniami – zmniejsza to narzut tworzenia obiektów.
* **Ustaw `Resolution`** (`generator.Parameters.ImageResolution`) na 300 dpi dla wysokiej jakości wydruków.
* **Włącz korekcję błędów** dla kodów 2‑D (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) aby zwiększyć niezawodność skanowania uszkodzonych mediów.
* **Otocz logikę zapisu** w blok `try / catch`, aby obsłużyć wyjątki I/O, szczególnie przy zapisie na udziały sieciowe.

## Podsumowanie

Teraz wiesz **jak generować kod kreskowy** przy użyciu Aspose.Barcode w C#. Tutorial obejmował instalację pakietu NuGet, tworzenie `BarcodeGenerator`, konfigurowanie wymiarów i kolumn oraz zapisywanie wyniku jako obrazu PNG. Dzięki tej podstawie możesz **tworzyć kod kreskowy przy użyciu Aspose** dla dowolnej obsługiwanej symbologii, dostosowywać parametry wizualne i integrować generowanie kodów kreskowych w większych rozwiązaniach .NET.

Gotowy, aby dalej eksplorować? Spróbuj generować kody QR do skracania URL, osadzać kody kreskowe w raportach PDF przy użyciu Aspose.PDF lub automatyzować masową kreację kodów kreskowych dla zarządzania inwentarzem. Każdy nowy scenariusz opiera się na tych samych podstawowych koncepcjach przedstawionych tutaj. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod PDF417 przy użyciu Aspose – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak wygenerować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – Przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak wygenerować obraz kodu kreskowego przy użyciu Aspose.BarCode w C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}