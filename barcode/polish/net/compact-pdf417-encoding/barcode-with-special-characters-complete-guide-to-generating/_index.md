---
category: general
date: 2026-07-27
description: Samouczek dotyczący kodów kreskowych ze znakami specjalnymi pokazuje,
  jak generować kody PDF417 przy użyciu Aspose. Dowiedz się, jak krok po kroku tworzyć
  i obsługiwać dane Unicode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: pl
lastmod: 2026-07-27
og_description: Samouczek dotyczący kodów kreskowych ze specjalnymi znakami wyjaśnia,
  jak generować kody PDF417 przy użyciu Aspose, obejmując obsługę Unicode i metadane
  makr.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Kod kreskowy ze specjalnymi znakami – Generuj PDF417 przy użyciu Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Kod kreskowy ze specjalnymi znakami – Kompletny przewodnik po generowaniu PDF417
  przy użyciu Aspose
url: /pl/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kod kreskowy ze znakami specjalnymi – Kompletny przewodnik po generowaniu PDF417 przy użyciu Aspose

Zastanawiałeś się kiedyś, jak stworzyć **kod kreskowy ze znakami specjalnymi**, który zawiera akcenty, symbole lub nawet znaki copyright? Nie jesteś sam. Wielu programistów napotyka problemy, gdy ich dane zawierają znaki takie jak „Å”, „é” czy „©”, a standardowe przykłady rzadko pokazują, jak sobie z nimi radzić. W tym samouczku przeprowadzimy Cię przez konkretny przykład, który nie tylko rozwiązuje ten problem, ale także demonstruje **jak generować PDF417** kody kreskowe przy użyciu biblioteki Aspose.BarCode.

Rozpoczniemy od skonfigurowania prostej aplikacji konsolowej .NET, a następnie przejdziemy do kodu, który generuje kod PDF417 zawierający ciąg `"Åspóse.Barcóde©"`. Po drodze zobaczysz, dlaczego każde ustawienie ma znaczenie, jak skonfigurować metadane macro‑PDF417 oraz na co zwrócić uwagę przy obsłudze Unicode. Po zakończeniu będziesz gotowy **tworzyć kod kreskowy przy użyciu Aspose** w dowolnym projekcie, niezależnie od tego, czy chodzi o inwentaryzację, biletowanie czy śledzenie dokumentów.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
- Visual Studio 2022 (lub dowolne inne IDE)
- Ważna licencja Aspose.BarCode dla .NET (możesz rozpocząć od darmowej wersji próbnej)
- Podstawowa znajomość składni C#

Jeśli którekolwiek z powyższych jest Ci nieznane, nie panikuj — po prostu zainstaluj .NET SDK i pobierz pakiet NuGet `Aspose.BarCode`, a będziesz gotowy do działania.

## Krok 1: Zainstaluj Aspose.BarCode i skonfiguruj projekt

Aby wygenerować **kod kreskowy ze znakami specjalnymi**, pierwszą rzeczą, której potrzebujesz, jest biblioteka Aspose.BarCode. Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

To pobiera najnowszą wersję (stan na lipiec 2026, wersja 23.12), która obsługuje pełną obsługę Unicode od razu. Po przywróceniu pakietu, utwórz nowy plik C# o nazwie `Program.cs` i dodaj standardowe dyrektywy `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Dlaczego `using Aspose.BarCode.Generation`? Daje nam dostęp do klasy `BarcodeGenerator`, serca **jak generować PDF417** kodów kreskowych z Aspose.

## Krok 2: Zainicjalizuj generator kodów kreskowych z tekstem Unicode

Teraz nadchodzi część, która faktycznie tworzy **kod kreskowy ze znakami specjalnymi**. Zauważ, że ciąg przekazywany do konstruktora zawiera „Å”, „ó” i „©”. Aspose automatycznie wykrywa zakres Unicode, więc nie musisz wykonywać dodatkowych kroków kodowania — po prostu podaj zwykły ciąg .NET:

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`EncodeTypes.MacroPdf417` informuje Aspose, że chcemy kod PDF417, który może przenosić informacje makro (przydatne przy podziale dużych ładunków). Generator teraz zawiera **kod kreskowy ze znakami specjalnymi**, gotowy do dalszych modyfikacji.

## Krok 3: Dostosuj wygląd i metadane makro

Zwykły kod kreskowy działa, ale w większości rzeczywistych scenariuszy potrzebna jest kontrola nad rozmiarem, liczbą kolumn i polami makro. Poniżej dostosowujemy wymiar X, liczbę kolumn, a następnie ustawiamy kilka właściwości macro‑PDF417. Każda linia jest skomentowana, abyś mógł zobaczyć *dlaczego* ma znaczenie.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Szybka wskazówka: jeśli zauważysz, że wygenerowany kod staje się zbyt szeroki, zmniejsz wartość `Columns` lub zwiększ `XDimension`. Oba parametry wpływają na ostateczny rozmiar obrazu, co jest kluczowe przy osadzaniu kodu w PDF‑ach lub etykietach drukowanych.

## Krok 4: Zapisz kod kreskowy jako obraz

Na koniec zapisujemy kod kreskowy do pliku PNG. Metoda `Save` automatycznie renderuje **kod kreskowy ze znakami specjalnymi** do formatu rastrowego, który możesz wyświetlić na stronie internetowej, osadzić w raporcie lub wysłać do drukarki.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Zastąp `YOUR_DIRECTORY` ścieżką absolutną lub względną, która istnieje na Twoim komputerze. Po zakończeniu programu powinieneś zobaczyć plik `ExtPDF417Meta.png` zawierający wyraźny kod PDF417, który koduje ciąg Unicode.

### Oczekiwany wynik

Jeśli otworzysz plik PNG, zobaczysz prostokątny kod kreskowy z serią czarnych i białych pasków. Zeskanowanie go przy użyciu skanera kompatybilnego z PDF417 (lub aplikacji mobilnej takiej jak „Barcode Scanner”) zwróci dokładny tekst `"Åspóse.Barcóde©"` wraz z ustawionymi metadanymi makro. Innymi słowy, kod zachowuje znaki specjalne bez utraty danych.

## Częste pytania i przypadki brzegowe

### Co zrobić, jeśli mój tekst zawiera emoji lub znaki spoza BMP?

Aspose.BarCode obsługuje pełny UTF‑16, więc emoji działają, o ile docelowy skaner potrafi je odczytać. Po prostu przekaż ciąg bezpośrednio; biblioteka zajmuje się kodowaniem wewnętrznie.

### Czy muszę ustawić konkretny zestaw znaków?

Nie. W przeciwieństwie do starszych SDK‑ów do kodów kreskowych, które wymagały ustawień `CodePage`, Aspose automatycznie wykrywa Unicode. Jednak jeśli celujesz w starsze urządzenie rozumiejące wyłącznie ASCII, będziesz musiał usunąć lub zamienić znaki specjalne przed generacją.

### czym różni się to od zwykłego kodu PDF417?

Wariant `MacroPdf417` dodaje dodatkowe pola (identyfikator pliku, liczba segmentów itp.), które pomagają podzielić duży ładunek na wiele kodów kreskowych. Jeśli nie potrzebujesz tych funkcji, możesz przełączyć się na `EncodeTypes.Pdf417` i pominąć właściwości specyficzne dla makro.

### Czy mogę wygenerować kod kreskowy jako wektor (SVG) zamiast PNG?

Oczywiście. Zmień `BarCodeImageFormat` na `Svg`:

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

Wyjście wektorowe skaluje się bez utraty jakości — przydatne przy druku wysokiej rozdzielczości.

## Pełny działający przykład

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Skopiuj i wklej go do `Program.cs`, dostosuj ścieżkę wyjściową i naciśnij **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

Uruchomienie tego programu wypisuje linię potwierdzającą i zapisuje `ExtPDF417Meta.png` w folderze wykonywalnym. Otwórz plik, zeskanuj go i zweryfikuj, że znaki specjalne przetrwały pełny cykl.

## Profesjonalne wskazówki dla produkcji

- **Cache the generator** jeśli tworzysz wiele kodów w pętli; ponowne użycie tej samej instancji `BarcodeGenerator` zmniejsza obciążenie pamięci.
- **Set `Resolution`** (`barcodeGenerator.Parameters.ImageResolution`) gdy potrzebujesz wyższej DPI dla zasobów gotowych do druku.
- **Validate input**: usuń znaki kontrolne, które mogą zepsuć pola makro. Proste wyrażenie regularne takie jak `^[\u0020-\u007E\u00A0-\u00FF]+$` działa w większości przypadków użycia Latin‑1.
- **Thread safety**: każdy wątek powinien posiadać własny `BarcodeGenerator`. Klasa nie jest bezpieczna wątkowo.

## Zakończenie

Masz teraz solidny, kompleksowy przepis na tworzenie **kodu kreskowego ze znakami specjalnymi** przy użyciu Aspose, a także zobaczyłeś **jak generować PDF417** kody, które przenoszą metadane makro. Przykład obejmuje wszystko — od instalacji pakietu NuGet po zapis finalnego PNG — i podkreśla typowe pułapki, takie jak obsługa Unicode i rozmiar obrazu.

Gotowy na kolejny krok? Spróbuj zamienić format obrazu na SVG, poeksperymentuj z większymi ładunkami


## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Recognizing PDF417 Barcode with Chinese Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Recognizing PDF417 Barcode with Turkish Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}