---
category: general
date: 2026-11-14
description: Dowiedz się, jak tworzyć obraz kodu kreskowego w C# przy użyciu Aspose.BarCode.
  Ten przewodnik krok po kroku obejmuje konfigurację generatora kodów kreskowych w
  C#, formatowanie GS1 oraz eksport do PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: pl
lastmod: 2026-11-14
og_description: Szybko utwórz obraz kodu kreskowego w C#. Przejdź do tego przewodnika,
  aby dowiedzieć się, jak generować kod kreskowy, używać generatora kodów kreskowych
  w C# i eksportować PNG GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Tworzenie obrazu kodu kreskowego w C# – pełny przewodnik po GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Jak utworzyć obraz kodu kreskowego w C# z GS1 MicroPDF417
url: /pl/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego w C# z GS1 MicroPDF417

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego** w C#, ten przewodnik pokaże Ci kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz **jak wygenerować dane kodu kreskowego**, które spełniają standard GS1, skonfigurujesz generator i wyeksportujesz wysokiej jakości plik PNG.

Poradnik obejmuje wszystko – od instalacji wymaganego biblioteki po obsługę typowych pułapek formatowania danych. Po zakończeniu będziesz w stanie wyprodukować **obraz kodu kreskowego z danych** za pomocą kilku linii kodu oraz zrozumiesz, dlaczego każde ustawienie ma znaczenie.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany (kod działa także z .NET Framework 4.7+).
* IDE, takie jak Visual Studio 2022 lub Visual Studio Code.
* Pakiet NuGet **Aspose.BarCode for .NET**. Zainstaluj go poleceniem:

```bash
dotnet add package Aspose.BarCode
```

* Podstawową znajomość składni C# oraz formatu GS1 Application Identifier (AI).

> **Pro tip:** Utrzymuj wersję biblioteki aktualną; najnowsze wydanie dodaje obsługę nowych symbologii kodów kreskowych oraz usprawnienia wydajności.

## Utworzenie obrazu kodu kreskowego przy użyciu BarcodeGenerator

Ten fragment zawiera podstawową implementację. Kod tworzy **instancję barcode generator c#**, konfiguruje wymiar X dla czytelności i zapisuje wynik jako plik PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Dlaczego każdy wiersz ma znaczenie

* **EncodeTypes.MicroPdf417** informuje bibliotekę, aby użyła symbologii GS1 MicroPDF417, która jest kompaktowa i idealna do skanowania mobilnego.
* **ciąg danych** musi zaczynać się od GS1 AI `(01)` dla Global Trade Item Number (GTIN) oraz `(21)` dla numeru seryjnego. Jeśli format jest nieprawidłowy, generator zgłosi wyjątek.
* **XDimension.Pixels** kontroluje szerokość najmniejszego paska. Większa wartość zwiększa czytelność na wyświetlaczach o niskiej rozdzielczości, natomiast mniejsza zmniejsza rozmiar obrazu.
* **BarCodeImageFormat.Png** generuje obraz bezstratny, zachowując ostre krawędzie niezbędne do niezawodnego skanowania.

Uruchomienie programu tworzy plik `GS1MicroPdf417.png` na pulpicie. Otworzenie pliku pokazuje gęsty, czarno‑biały kod kreskowy, który koduje GTIN `12345678901234` oraz numer seryjny `ABC123`.

## Jak wygenerować kod kreskowy przy użyciu GS1 MicroPDF417

Jeśli dopiero zaczynasz przygodę z formatowaniem GS1, oto najważniejsze zasady:

| GS1 AI | Znaczenie                     | Przykład               |
|--------|------------------------------|-----------------------|
| (01)   | Global Trade Item Number     | 12345678901234        |
| (21)   | Numer seryjny (opcjonalny)   | ABC123                |

Łącząc AI z ich wartościami, umieszczasz każde AI w nawiasach i wstawiasz wartości bezpośrednio po nich. Otrzymany ciąg może być przekazany do **barcode generator c#** bez dodatkowego kodowania.

### Typowe pułapki

* **Brak nawiasów** – Generator traktuje ciąg jako surowe dane i nie zastosuje kontroli GS1.
* **Przekroczenie limitu długości** – MicroPDF417 obsługuje maksymalnie 155 znaków. Usuń zbędne spacje.
* **Nieprawidłowe znaki** – Dla GTIN dozwolone są wyłącznie cyfry; numer seryjny może zawierać wielkie litery i cyfry.

## Dostosowywanie obrazu kodu kreskowego z danych

Poza podstawowym wymiarem X, Aspose.BarCode oferuje wiele wizualnych poprawek. Poniżej kilka ustawień, które możesz zastosować w zależności od wymagań projektu.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Każde ustawienie jest opcjonalne; domyślne wartości już generują czysty, skanowalny **obraz kodu kreskowego**. Eksperymentuj z kolorami i rozdzielczością dopiero po potwierdzeniu, że skanery nadal odczytują kod.

## Zapisywanie kodu kreskowego w innych formatach

Choć PNG jest najczęściej używanym formatem w sieci i na urządzeniach mobilnych, możesz potrzebować JPEG, BMP lub SVG. Metoda `Save` przyjmuje dowolną wartość `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG zmniejsza rozmiar pliku, ale wprowadza artefakty kompresji, które mogą wpływać na czytelność.
* SVG zachowuje jakość wektorową i jest idealny dla responsywnych projektów internetowych.

## Weryfikacja wygenerowanego kodu kreskowego

Szybki sposób, aby potwierdzić, że krok **create barcode image** zakończył się sukcesem, to użycie aplikacji skanującej na telefonie, obsługującej GS1 MicroPDF417. Zeskanuj zapisany PNG; aplikacja powinna wyświetlić:

```
GTIN: 12345678901234
Serial: ABC123
```

Jeśli skaner zgłosi błąd, sprawdź ponownie formatowanie AI oraz wartość wymiaru X.

## Pełny przykład – samodzielny program konsolowy

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić bez modyfikacji (poza krokiem instalacji NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Po uruchomieniu program wypisze pełną ścieżkę pliku, a PNG pojawi się na pulpicie. Ten przykład demonstruje **jak wygenerować dane kodu kreskowego**, dostosować wygląd i wyeksportować **obraz kodu kreskowego z danych** w jednym, spójnym przepływie pracy.

## Najczęściej zadawane pytania

| Pytanie | Odpowiedź |
|----------|-----------|
| *Czy mogę generować inne symbologie GS1?* | Tak. Zamień `EncodeTypes.MicroPdf417` na `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix` itp., i odpowiednio dostosuj ciąg danych. |
| *Co zrobić, gdy moje dane przekraczają pojemność MicroPDF417?* | Przejdź na standardowy PDF417, który obsługuje dłuższe ładunki. |
| *Czy potrzebna jest licencja na Aspose.BarCode?* | Bezpłatna licencja ewaluacyjna działa w środowisku deweloperskim. W produkcji zakup licencji, aby usunąć znak wodny ewaluacji. |
| *Czy PNG nadaje się do druku na etykietach?* | Zwiększ `ImageResolution` do 300 dpi lub wyżej oraz rozważ zapis jako TIFF dla drukarek przemysłowych. |

## Zakończenie

Teraz wiesz, jak **utworzyć obraz kodu kreskowego** w C# przy użyciu podejścia **barcode generator c#**, jak sformatować dane dla scenariusza **create gs1 barcode** oraz jak wyeksportować wynik jako PNG lub inny typ obrazu. Pełny przykład pokazuje każdy krok – od przygotowania danych po dostosowanie wyglądu – dzięki czemu możesz zintegrować tworzenie kodów kreskowych w dowolnej aplikacji .NET.

Następnie zgłęb tematy pokrewne, takie jak **barcode image from data** dla kodów QR, dodawanie wielu kodów kreskowych do jednego PDF lub automatyzacja masowej generacji dla systemów inwentaryzacyjnych. Eksperymentuj z różnymi wartościami wymiaru X i formatami obrazu, aby znaleźć optymalne ustawienia dla swojego środowiska skanowania.

Miłego kodowania i niech Twoje aplikacje zaczynają **tworzyć obrazy kodów kreskowych**, które działają niezawodnie w rzeczywistym świecie!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}