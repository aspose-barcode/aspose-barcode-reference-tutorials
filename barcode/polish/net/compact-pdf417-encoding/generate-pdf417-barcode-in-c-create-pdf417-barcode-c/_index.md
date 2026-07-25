---
category: general
date: 2026-07-24
description: Generuj kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak w ciągu kilku minut utworzyć kod kreskowy PDF417 w C# w trybie kompaktowym.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: pl
lastmod: 2026-07-24
og_description: Szybko generuj kod kreskowy PDF417 w C# za pomocą Aspose.BarCode.
  Ten samouczek pokazuje, jak stworzyć kod PDF417 w C# w trybie kompaktowym, obejmując
  konfigurację, kod i weryfikację.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Generowanie kodu kreskowego PDF417 w C# – Szybki przewodnik
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Generuj kod kreskowy PDF417 w C# – Utwórz kod kreskowy PDF417 w C#
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wygeneruj kod kreskowy PDF417 w C# – Kompletny przewodnik programistyczny

Zastanawiałeś się kiedyś, jak **wygenerować kod kreskowy PDF417** w aplikacji C# bez przeszukiwania niezliczonych wątków na forach? Nie jesteś jedyny. Niezależnie od tego, czy tworzysz system biletowy, bezpieczną kartę identyfikacyjną, czy po prostu potrzebujesz szybkiego sposobu na osadzenie danych w formacie do druku, opanowanie formatu PDF417 może zaoszczędzić Ci godziny prób i błędów.

W tym przewodniku przeprowadzimy Cię przez **kompletny, gotowy do uruchomienia przykład**, który pokaże dokładnie, jak **utworzyć kod kreskowy PDF417 w C#** przy użyciu popularnej biblioteki Aspose.BarCode. Omówimy wszystko, od instalacji pakietu NuGet po dostosowanie trybu kompaktowego, abyś mógł skopiować‑wkleić kod i od razu zobaczyć wyniki.

## Czego się nauczysz

- Jak skonfigurować bibliotekę Aspose.BarCode w projekcie .NET.  
- Dokładne instrukcje C# potrzebne do **generowania kodu kreskowego PDF417** z własnym tekstem, rozmiarem modułu i liczbą kolumn.  
- Dlaczego przełączanie opcji *Compact* (Truncate) ma znaczenie przy gęstych danych.  
- Sposoby zapisu kodu kreskowego jako PNG i weryfikacji wyniku.  

Nie wymagana jest wcześniejsza znajomość kodów kreskowych; wystarczy podstawowa znajomość C# i Visual Studio (lub dowolnego ulubionego IDE). Po zakończeniu będziesz mieć metodę, którą możesz wstawić do dowolnego projektu potrzebującego obrazu PDF417.

## Wymagania wstępne

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 lub nowszy (lub .NET Framework 4.7+) | Aspose.BarCode obsługuje oba; nowsze środowiska zapewniają lepszą wydajność. |
| Visual Studio 2022 (lub VS Code z rozszerzeniami C#) | Dostarcza IntelliSense i ułatwia debugowanie. |
| Połączenie internetowe (do pierwszego przywrócenia pakietu NuGet) | Biblioteka jest pobierana z NuGet.org. |
| Podstawowa znajomość C# | Konieczna do zrozumienia struktur klas i wywołań metod. |

Jeśli już masz te elementy, świetnie — zanurzmy się.

## Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz folder projektu w terminalu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Lub, w Visual Studio, kliknij prawym przyciskiem **Dependencies → Manage NuGet Packages**, wyszukaj *Aspose.BarCode* i kliknij **Install**. To jedno polecenie pobiera wszystkie typy, których użyjemy, w tym `BarcodeGenerator`, `EncodeTypes` oraz `BarCodeImageFormat`.

> **Wskazówka:** Po instalacji wyczyść i przebuduj rozwiązanie, aby upewnić się, że zestaw jest poprawnie odwoływany.

## Generowanie kodu PDF417 – konfiguracja i zależności

Najpierw potrzebujemy bloku `using`, który wciągnie odpowiednie przestrzenie nazw do zasięgu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te przestrzenie nazw dają dostęp do klasy generatora oraz wyliczenia typów kodów kreskowych. Nic skomplikowanego — tylko trzy linijki i możemy zaczynać tworzyć kod kreskowy.

## Utwórz kod PDF417 w C# – implementacja krok po kroku

Poniżej znajduje się **samodzielny program konsolowy**, który tworzy kompaktowy kod PDF417 z łańcucha `"Åspóse.Barcóde©"` i zapisuje go jako `CompactPdf417.png`. Śmiało zamień tekst na dowolny potrzebny; generator obsługuje znaki Unicode od razu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Dlaczego każdy krok ma znaczenie

1. **Definicja danych** – PDF417 może przechowywać do ~1850 znaków, ale dla demonstracji trzymamy je krótkie. Obsługa Unicode oznacza, że te znaki diakrytyczne nie spowodują problemów.  
2. **Konstrukcja generatora** – wartość wyliczenia `EncodeTypes.Pdf417` informuje Aspose, jaką symbologię użyć; zamiana jej na `EncodeTypes.QR` spowodowałaby wygenerowanie kodu QR.  
3. **Wymiar X** – kontroluje szerokość każdego modułu (małych kwadratów tworzących kod kreskowy). Wartość `2` piksele daje wyraźny obraz, który nadal jest czytelny przy druku w 300 dpi.  
4. **Opcje PDF417** – `Columns` wpływa na proporcje kodu; mniejsza liczba kolumn sprawia, że obraz jest wyższy, co może być przydatne przy paragonach. `Truncate` (zwany także *trybem kompaktowym*) usuwa wypełnienie wzorca start/stop, zmniejszając rozmiar pliku bez utraty integralności danych.  
5. **Ścieżka wyjściowa** – użycie `Environment.CurrentDirectory` zapewnia, że obraz zostanie zapisany obok pliku wykonywalnego, co ułatwia jego odnalezienie podczas developmentu.  
6. **Zapisywanie** – `BarCodeImageFormat.Png` zapewnia jakość bezstratną, idealną do dalszego przetwarzania lub osadzania w PDF.

Uruchom program (`dotnet run` lub naciśnij **F5** w Visual Studio). Po kilku sekundach powinieneś zobaczyć komunikat w konsoli potwierdzający lokalizację pliku, a PNG pojawi się w folderze projektu.

![Przykład generowania kodu PDF417](generated-pdf417.png)

*Tekst alternatywny obrazu: przykład generowania kodu PDF417 – obraz PNG kompaktowego kodu PDF417 utworzonego w C#.*

## Konfiguracja trybu kompaktowego – opcje generatora kodu PDF417 w C#

Jeśli potrzebujesz większego kodu (np. do skanowania z większej odległości), dostosuj właściwości `Columns` i `Rows`. Oto szybki fragment kodu demonstrujący alternatywne konfiguracje:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Częste pytanie:** *Czy wyłączenie Truncate uszkodzi istniejące skanery?*  
> Zazwyczaj nie. Większość nowoczesnych skanerów rozumie zarówno pełnowymiarowy, jak i kompaktowy PDF417. Jednak jeśli celujesz w starszy sprzęt, pozostaw `Truncate` ustawione na `false`.

## Zapis i weryfikacja – jak wygenerować wyjście kodu PDF417

Po zapisaniu możesz otworzyć PNG w dowolnym przeglądarce obrazów. Aby podwójnie sprawdzić, że kod kreskowy zawiera zamierzone dane, użyj `BarCodeReader` Aspose:



## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [biblioteka kodów kreskowych Java – Dodaj kod kreskowy do PDF przy użyciu Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}