---
category: general
date: 2026-10-21
description: Szybko generuj kod kreskowy PDF417 w C#. Dowiedz się, jak generować kod
  PDF417 z niestandardowym układem, kolumnami, wierszami i wyjściem PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: pl
lastmod: 2026-10-21
og_description: Generuj kod kreskowy pdf417 w C#. Przejdź do tego samouczka, aby dowiedzieć
  się, jak generować kod pdf417 z własnymi kolumnami, wierszami i wyjściem PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generowanie kodu kreskowego PDF417 w C# – pełny przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Generuj kod kreskowy PDF417 w C# z niestandardowymi kolumnami i wierszami
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wygeneruj kod kreskowy pdf417 w C# – kompletny przewodnik programistyczny

Jeśli potrzebujesz **wygenerować kod kreskowy pdf417** w aplikacji .NET, ten przewodnik pokaże Ci, jak to zrobić w kilku linijkach kodu. Zobaczysz praktyczny przykład, który konfiguruje liczbę kolumn i wierszy, a następnie zapisuje wynik jako obraz PNG. To samo podejście działa dla dowolnego tekstu, który chcesz zakodować, więc możesz je dostosować do faktur, biletów czy kart identyfikacyjnych.

Generowanie **kod kreskowy pdf417** często wydaje się oddzielnym zadaniem od reszty Twojej bazy kodu. Po zakończeniu tego samouczka zrozumiesz, dlaczego parametry układu mają znaczenie, jak kontrolować jakość obrazu oraz które wywołania biblioteki są potrzebne, aby **wygenerować kod kreskowy pdf417** w sposób niezawodny.

## Czego będziesz potrzebować

Zanim zaczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* IDE kompatybilne z C# (Visual Studio, VS Code, Rider, itp.)  
* Pakiet NuGet **Aspose.BarCode for .NET** (lub dowolną kompatybilną bibliotekę kodów kreskowych)  

Możesz dodać bibliotekę przy pomocy następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

Biblioteka udostępnia klasę `BarcodeGenerator` używaną w całym tym samouczku.

## Krok 1: Utwórz instancję generatora kodów kreskowych

Pierwsza linijka tworzy obiekt, który potrafi **wygenerować kod kreskowy pdf417**. Musisz określić typ kodowania (`EncodeTypes.Pdf417`) oraz tekst, który chcesz zakodować.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Dlaczego ten krok ma znaczenie* – `BarcodeGenerator` enkapsuluje wszystkie ustawienia kodu kreskowego. Utworzenie go z właściwym `EncodeTypes` informuje silnik, aby użył symboliki PDF417 zamiast QR, Code128 czy innych formatów.

## Krok 2: Skonfiguruj układ PDF417

PDF417 pozwala kontrolować liczbę kolumn i wierszy, co bezpośrednio wpływa na rozmiar i gęstość kodu kreskowego. Dostosowanie tych wartości jest sednem **jak wygenerować kod kreskowy pdf417** z własnym układem.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Dlaczego możesz chcieć zmienić te wartości* – Więcej kolumn zmniejsza wysokość kodu, a więcej wierszy zwiększa jego szerokość. Dobierz wartości tak, aby pasowały do docelowego urządzenia skanującego i dostępnego obszaru druku.

> **Pro tip:** Jeśli pominiesz wiersze, biblioteka automatycznie obliczy optymalną ich liczbę na podstawie długości danych. Jawne ustawienie wierszy jest przydatne, gdy potrzebny jest stały rozmiar obrazu w układach UI.

## Krok 3: Wybierz format obrazu i zapisz plik

Po skonfigurowaniu układu możesz wyrenderować kod kreskowy do obrazu. Poniższy przykład zapisuje kod jako plik PNG, ale możesz także wybrać JPEG, BMP lub TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Gdy kod zostanie uruchomiony, `CustomLayout.png` będzie zawierał wyraźny **kod kreskowy pdf417**, który odpowiada podanym ustawieniom kolumn/wierszy.

### Oczekiwany wynik

Otwierając `CustomLayout.png` zobaczysz prostokątny kod kreskowy z czterema kolumnami danych i dziewięcioma wierszami. Zeskanowanie obrazu dowolnym czytnikiem PDF417 zwróci oryginalny tekst **„Sample Text”**.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Wygenerowany kod kreskowy pdf417 zapisany jako plik PNG"}

## Krok 4: Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się samodzielna aplikacja konsolowa, która łączy wszystkie elementy. Skopiuj kod do nowego projektu `.csproj` i uruchom go — nie są wymagane żadne dodatkowe pliki.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Uruchomienie programu wypisuje linię potwierdzającą i tworzy plik PNG w podfolderze `output`. Obraz może być osadzony w raportach, wydrukowany na etykietach lub wysłany do urządzenia mobilnego w celu zeskanowania.

## Typowe warianty i przypadki brzegowe

| Scenariusz | Co zmienić | Dlaczego ma to znaczenie |
|------------|------------|--------------------------|
| **Zakoduj długi ciąg znaków** | Zwiększ `Rows` lub pozwól bibliotece automatycznie obliczyć, pomijając przypisanie `Rows` | PDF417 może pomieścić do 1 850 znaków; niewystarczająca liczba wierszy powoduje obcięcie |
| **Wyższa jakość wizualna** | Ustaw `generator.Parameters.ImageResolution` na 600 DPI | Przydatne przy drukowaniu na drukarkach wysokiej rozdzielczości |
| **Inny format obrazu** | Zastąp `BarCodeImageFormat.Png` przez `Jpeg` lub `Tiff` | JPEG zmniejsza rozmiar pliku; TIFF zachowuje dane bezstratnie do archiwizacji |
| **Dodaj strefę ciszy** | `generator.Parameters.Barcode.XDimension = 2;` (lub dostosuj `Margins`) | Strefy ciszy zwiększają niezawodność skanera w hałaśliwych warunkach |
| **Dynamiczny tekst z wejścia użytkownika** | Zastąp na stałe zakodowany ciąg znaków wywołaniem `Console.ReadLine()` | Umożliwia generowanie w czasie rzeczywistym na podstawie danych użytkownika |

### Jak wygenerować kod kreskowy pdf417 w API internetowym

Jeśli musisz udostępnić generowanie kodów kreskowych przez endpoint ASP.NET Core, zwróć obraz jako tablicę bajtów:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Ten fragment odpowiada na pytanie **jak wygenerować kod kreskowy pdf417** w locie, bez zapisywania na dysku, co jest idealne dla mikrousług lub backendów mobilnych.

## Testowanie wygenerowanego kodu kreskowego

Aby zweryfikować, że kod kreskowy został utworzony prawidłowo:

1. Otwórz plik PNG w dowolnym przeglądarce obrazów.  
2. Użyj darmowej aplikacji skanującej PDF417 (np. ZXing, PDF417 Decoder), aby zeskanować obraz.  
3. Potwierdź, że odkodowany tekst jest zgodny z pierwotnym wejściem.

Jeśli skaner zgłasza błędy, sprawdź ponownie wartości kolumn/wierszy i upewnij się, że rozdzielczość obrazu jest wystarczająco wysoka dla Twojego urządzenia.

## Zakończenie

Teraz wiesz, jak **wygenerować kod kreskowy pdf417** w C# z pełną kontrolą nad kolumnami, wierszami i formatem wyjściowym. Pełny przykład demonstruje cały przepływ pracy — od stworzenia `BarcodeGenerator` po zapis pliku PNG — dzięki czemu możesz zintegrować tworzenie kodów kreskowych w dowolnym projekcie .NET.

Następnie zgłęb tematy pokrewne, takie jak optymalizacja **układu kodu kreskowego pdf417**, osadzanie kodów w raportach PDF czy dekodowanie kodów na urządzeniach mobilnych. Dostosowywanie poziomów korekcji błędów i eksperymentowanie z różnymi rozdzielczościami obrazu pomoże Ci dopracować rozwiązanie pod konkretny przypadek użycia. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 w C# – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak zapisać kod kreskowy w C# – generowanie kodów PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Jak wygenerować kod kreskowy PDF417 – kompletny przewodnik programistyczny](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}