---
category: general
date: 2026-09-23
description: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu Aspose.BarCode.
  Dowiedz się, jak generować kod kreskowy w C#, dostosowywać rozmiar i efektywnie
  eksportować obraz kodu kreskowego.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: pl
lastmod: 2026-09-23
og_description: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu Aspose.BarCode.
  Postępuj zgodnie z tym przewodnikiem, aby wygenerować kod C# dla kodu kreskowego,
  dostosować wymiary i wyeksportować obraz kodu kreskowego.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Jak zmienić rozmiar kodu kreskowego w C# – kompletny poradnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Jak zmienić rozmiar kodu kreskowego w C# przy użyciu Aspose.BarCode – przewodnik
  krok po kroku
url: /pl/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zmienić rozmiar kodu kreskowego w C# przy użyciu Aspose.BarCode – przewodnik krok po kroku

Jeśli potrzebujesz **jak zmienić rozmiar kodu kreskowego** w aplikacji .NET, ten samouczek pokazuje dokładny kod, który możesz skopiować‑wkleić i uruchomić już dziś. Nauczysz się, jak **generować kod kreskowy w C#**, dostosować wysokość pasków oraz **eksportować obrazy kodów kreskowych** bez opuszczania IDE.

Tworzenie kodów kreskowych jest powszechne w systemach inwentaryzacji, etykietach wysyłkowych i terminalach punktu sprzedaży. Po zakończeniu tego przewodnika będziesz w stanie **tworzyć obrazy kodu Databar** o dowolnej wymaganej wysokości oraz zrozumiesz kluczowe właściwości kontrolujące rozmiar, rozdzielczość i format pliku.

## Prerequisites

- .NET 6 lub nowszy (przykład działa również z .NET Framework 4.6+)
- Pakiet NuGet Aspose.BarCode dla .NET (`Install-Package Aspose.BarCode`)
- Podstawowa znajomość składni C# oraz Visual Studio (lub dowolnego IDE C#)

Nie są potrzebne dodatkowe biblioteki; Aspose.BarCode obsługuje renderowanie, skalowanie i eksport obrazu wewnętrznie.

## Krok 1: Skonfiguruj projekt i zaimportuj Aspose.BarCode

Utwórz nowy projekt konsolowy (lub zintegrować go z istniejącym) i dodaj przestrzeń nazw Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Pro tip:** Użyj najnowszej wersji Aspose.BarCode (stan na wrzesień 2026), aby skorzystać z poprawek błędów i nowych symbologii kodów kreskowych.

## Krok 2: Zainicjalizuj generator kodu DataBar Omni‑directional

**Przykład generatora kodu kreskowego** zaczyna się od określenia symbologii (`EncodeTypes.DatabarOmniDirectional`) oraz danych. Dane są w formacie identyfikatora aplikacji GS1 `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Ten obiekt przechowuje wszystkie parametry, które później zmodyfikujesz, takie jak X‑dimension, wysokość paska i format obrazu.

## Krok 3: Zdefiniuj wspólne parametry rozmiaru

Przed eksportem ustaw X‑dimension (szerokość najcieńszego paska) oraz początkową wysokość paska. X‑dimension wyrażana jest w pikselach; wartość `2` sprawdza się w większości rozdzielczości ekranu.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Dlaczego to ważne:** Właściwość `BarHeight` bezpośrednio wpływa na wizualny rozmiar kodu kreskowego. Zmiana tej wartości jest sednem **jak zmienić rozmiar kodu kreskowego** w Aspose.BarCode.

## Krok 4: Wyeksportuj pierwszy obraz kodu kreskowego (wysokość 30 px)

Teraz możesz **eksportować obraz kodu kreskowego** do pliku PNG. Metoda `Save` automatycznie renderuje kod kreskowy z aktualnymi parametrami.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Wygenerowany plik wygląda tak:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Przykład zmiany rozmiaru kodu kreskowego – wysokość 30 pikseli"}

## Krok 5: Zmień wysokość pasków, aby utworzyć większy kod kreskowy

Aby pokazać **jak zmienić rozmiar kodu kreskowego** dynamicznie, zmodyfikuj właściwość `BarHeight` i ponownie zapisz. Nie wymaga to tworzenia nowej instancji `BarcodeGenerator`; wystarczy zmienić istniejący obiekt.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Krok 6: Wyeksportuj zmieniony rozmiar obrazu kodu kreskowego (wysokość 60 px)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Masz teraz dwa pliki PNG — jeden o wysokości 30 px, drugi o wysokości 60 px — pokazujące, jak te same dane mogą być renderowane w różnych rozmiarach.

### Oczekiwany wynik

| Nazwa pliku                     | Wysokość paska (px) | Wynik wizualny |
|---------------------------------|---------------------|----------------|
| `DatabarBarHeight30Pixels.png`  | 30                  | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="30‑pikselowy kod DataBar Omni‑directional"} |
| `DatabarBarHeight60Pixels.png`  | 60                  | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="60‑pikselowy kod DataBar Omni‑directional"} |

Oba obrazy są prawidłowymi kodami GS1‑128 DataBar gotowymi do skanowania.

## Krok 7: Opcjonalnie – Dostosuj dodatkowe ustawienia wizualne

Choć głównym celem jest **jak zmienić rozmiar kodu kreskowego**, możesz także chcieć dostroić:

| Właściwość | Opis | Typowe wartości |
|------------|------|-----------------|
| `XDimension.Pixels` | Szerokość najcieńszego paska | 1–4 |
| `BarHeight.Pixels`  | Wysokość całego kodu kreskowego | 20–200 |
| `Resolution` | DPI dla wyjścia rastrowego | 72, 150, 300 |
| `ForeColor` / `BackColor` | Kolory pierwszego planu i tła | `Color.Black`, `Color.White` |

Przykład:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Te drobne zmiany nie wpływają na logikę **zmiany rozmiaru**, ale dają pełną kontrolę nad jakością końcowego obrazu.

## Typowe pułapki i jak ich unikać

| Problem | Objaw | Rozwiązanie |
|---------|-------|-------------|
| Wysokość paska się nie zmienia | Zapisane obrazy wyglądają identycznie | Upewnij się, że modyfikujesz `barcode.Parameters.Barcode.BarHeight.Pixels` *przed* każdym wywołaniem `Save`. |
| Kod staje się nieczytelny | Skaner zgłasza „nie może odczytać” | Utrzymuj `XDimension` ≥ 2 px dla DataBar Omni‑directional; bardzo cienkie paski mogą uniemożliwić skanowanie. |
| Plik PNG jest rozmyty | Wyeksportowano przy niskim DPI | Ustaw `barcode.Parameters.ImageResolution.DpiX/Y` przynajmniej na 150 dla obrazów o jakości druku. |
| Plik został przypadkowo nadpisany | Nowy obraz zastępuje poprzedni | Używaj unikalnych nazw plików lub dołącz wartość wysokości do nazwy pliku, jak pokazano powyżej. |

## Pełny, gotowy do uruchomienia przykład

Skopiuj cały blok poniżej do nowej aplikacji konsolowej (`Program.cs`). Kod kompiluje się i działa bez zmian, generując dwa pliki PNG w folderze wyjściowym projektu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

Uruchomienie programu daje:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Sprawdź folder wyjściowy, aby zobaczyć dwa pliki PNG. Oba są gotowe do druku, osadzania w PDF‑ach lub wysyłania do zdalnego urządzenia.

## Zakończenie

W tym przewodniku omówiliśmy **jak zmienić rozmiar kodu kreskowego** w C# przy użyciu Aspose.BarCode, przedstawiliśmy kompletny **przykład generatora kodu kreskowego** oraz pokazaliśmy, jak **eksportować obrazy kodów kreskowych** w różnych wysokościach. Teraz wiesz, jak:

1. **Utworzyć obiekty Databar barcode** z niestandardowymi danymi.  
2. Dostosować `BarHeight` (główna część zmiany rozmiaru).  
3. Eksportować pliki PNG w dowolnym wymaganym rozmiarze.  

Od tego momentu możesz eksplorować dalsze możliwości — różne symbologie, schematy kolorów lub formaty wektorowe, takie jak SVG. Ten sam wzorzec (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) działa dla każdego typu kodu obsługiwanego przez Aspose.BarCode, więc możesz pewnie stosować wiedzę o **jak zmienić rozmiar kodu kreskowego** w całej swojej aplikacji.

---

**Kolejne kroki**

- Spróbuj zmienić rozmiar innych symbologii (QR, Code128), aby zobaczyć, jak współdziałają wysokość i szerokość.  
- Użyj `BarCodeImageFormat.Svg`, aby generować skalowalne grafiki wektorowe dla stron internetowych.  
- Zintegruj wygenerowane obrazy w raportach PDF przy użyciu Aspose.PDF lub iTextSharp.  

Miłego kodowania i ciesz się elastycznością, jaką daje programowe generowanie kodów kreskowych!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak generować i dostosowywać wysokość kodu kreskowego One-Dimensional Databar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generować kod kreskowy – konfiguracja Code 39 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}