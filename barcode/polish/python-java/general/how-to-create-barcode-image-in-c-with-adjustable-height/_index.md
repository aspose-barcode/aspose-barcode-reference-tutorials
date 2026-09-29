---
category: general
date: 2026-09-07
description: Dowiedz się, jak tworzyć obraz kodu kreskowego w C# oraz dostosowywać
  jego wysokość, szerokość i format, aby szybko generować pliki PNG z kodami kreskowymi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: pl
lastmod: 2026-09-07
og_description: Utwórz obraz kodu kreskowego w C# i dowiedz się, jak ustawiać wymiary
  kodu kreskowego, zmieniać jego wysokość oraz generować pliki PNG kodu kreskowego
  dla dowolnej aplikacji.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Tworzenie obrazu kodu kreskowego w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Jak stworzyć obraz kodu kreskowego w C# z regulowaną wysokością
url: /pl/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego w C# z regulowaną wysokością

Jeśli potrzebujesz utworzyć obraz kodu kreskowego w C# dla systemu sprzedaży detalicznej lub systemu śledzenia zapasów, ten przewodnik pokaże Ci kompletny przepływ pracy. Zobaczysz, jak ustawić parametry kodu kreskowego, zmienić jego wysokość oraz wygenerować pliki PNG kodu kreskowego spełniające wymagania wizualne.

Generowanie obrazu kodu kreskowego to częste zadanie przy integracji sprzętu skanującego, drukowaniu etykiet lub budowaniu pulpitów raportowych. Po zakończeniu tego tutorialu będziesz mieć wielokrotnego użytku fragment kodu, który pozwala regulować wymiar X, wysokość i format wyjściowy kodu kreskowego bez opuszczania IDE.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 (lub nowszy) – kod kompiluje się z dowolnym aktualnym SDK .NET.
* Odwołanie do biblioteki **Aspose.BarCode** (dostępnej przez NuGet `Aspose.BarCode`).
* Podstawową znajomość aplikacji konsolowych w C#.

Te wymagania zapewniają, że przykład uruchomi się od razu na Windows, Linux lub macOS.

## Krok 1: Utwórz projekt i zaimportuj bibliotekę

Utwórz nowy projekt konsolowy i dodaj pakiet kodu kreskowego:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Teraz otwórz *Program.cs* i dodaj niezbędne dyrektywy `using`:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Te importy dają dostęp do `BarcodeGenerator`, `EncodeTypes` oraz wyliczeń formatów obrazu potrzebnych do **tworzenia obrazu kodu kreskowego**.

## Krok 2: Zainicjuj generator z żądaną symbologią

Pierwsza linia kodu tworzy `BarcodeGenerator`, który wie, jaki typ kodu kreskowego zakodować. W tym przykładzie używamy symbologii DataBar Omni‑Directional, ale możesz zamienić `EncodeTypes.DatabarOmniDirectional` na dowolny inny typ obsługiwany przez Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Ciąg `"(01)12345678901231"` spełnia format identyfikatora aplikacji GS1, którego wymaga wielu detalistów. Inicjalizacja generatora jest podstawą każdej operacji **jak ustawić kod kreskowy**, która następuje później.

## Krok 3: Jak ustawić wymiary kodu kreskowego – wymiar X i wysokość

### 3.1 Regulacja szerokości wąskiego paska (wymiar X)

Wymiar X kontroluje grubość najcieńszego paska. Wartość **2 piksele** daje bardziej delikatny wygląd, przydatny, gdy potrzebna jest kompaktowa etykieta.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Zmiana wysokości kodu kreskowego dla równowagi wizualnej

Wysokość paska określa, jak wysoki jest kod kreskowy. Poniżej pokazujemy dwie typowe wysokości — 30 pikseli dla małej etykiety i 60 pikseli dla większej. To demonstruje **jak regulować wysokość kodu kreskowego** programowo.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Krok 4: Generowanie plików PNG kodu kreskowego o różnych wysokościach

### 4.1 Zapisz pierwszy obraz (wysokość 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Zwiększ wysokość i zapisz drugi obraz

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Te dwa wywołania `Save` ilustrują **generowanie plików PNG kodu kreskowego** o odmiennych wymiarach przy jednoczesnym użyciu tego samego obiektu generatora. Format obrazu jest jawnie ustawiony na PNG, co zachowuje jakość bezstratną — idealną do druku lub wyświetlania na ekranie.

## Krok 5: Pełny, gotowy do uruchomienia przykład

Połączenie wszystkiego w jedną metodę `Main`, którą możesz skopiować do dowolnego projektu konsolowego C#:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Uruchomienie tego programu wygeneruje dwa pliki PNG w folderze wyjściowym projektu:

* `DatabarBarHeight30Pixels.png` – kompaktowy kod kreskowy o wysokości 30 px.
* `DatabarBarHeight60Pixels.png` – większy kod kreskowy o wysokości 60 px.

Oba pliki zawierają **utworzony obraz kodu kreskowego**, który można osadzić w HTML, wydrukować na etykietach lub przesłać do aplikacji mobilnej w celu skanowania.

## Częste pytania i obsługa przypadków brzegowych

| Pytanie | Odpowiedź |
|----------|--------|
| **Co zrobić, jeśli potrzebny jest inny format obrazu?** | Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`, `Bmp` lub `Gif`. Biblioteka automatycznie zajmuje się konwersją. |
| **Czy mogę zmienić kolory pierwszego planu/tła?** | Tak. Użyj `generator.Parameters.Barcode.ForeColor` i `BackColor`, aby ustawić wartości `System.Drawing.Color` przed wywołaniem `Save`. |
| **Jak wygenerować kod kreskowy bez zapisywania pliku na dysku?** | Wywołaj `generator.GenerateBarCodeImage()`, aby otrzymać obiekt `System.Drawing.Image`, a następnie przekaż go bezpośrednio w odpowiedzi lub do bazy danych. |
| **Co jeśli ciąg danych przekracza limit symbologii?** | Generator rzuci `ArgumentException`. Zweryfikuj długość wejścia lub przytnij ją zgodnie ze specyfikacją symbologii. |
| **Czy istnieje sposób na przetwarzanie wsadowe wielu kodów kreskowych?** | Umieść kroki w pętli `foreach`, aktualizując `generator.CodeText` i `BarHeight` dla każdego elementu, a następnie wywołaj `Save` z unikalną nazwą pliku. |

Omówienie tych scenariuszy sprawia, że logika **jak regulować kod kreskowy** jest solidna w projektach produkcyjnych.

## Profesjonalne wskazówki dla niezawodnego generowania kodów kreskowych

* **Cache'uj generator** przy tworzeniu wielu kodów tego samego typu; ponowne użycie obiektu zmniejsza narzut alokacji.
* **Ustaw `Resolution`** (`generator.Parameters.ImageResolution.Dpi`), jeśli potrzebujesz wysokiej rozdzielczości PNG do druku.
* **Waliduj dane GS1** przed przypisaniem ich do `CodeText`, aby uniknąć błędów kodowania, które mogą powodować niepowodzenia skanowania.
* **Testuj na rzeczywistych skanerach** po zmianie wysokości lub wymiaru X — niektóre starsze urządzenia mają minimalne wymagania rozmiaru.

## Podsumowanie

Teraz wiesz, jak **utworzyć obraz kodu kreskowego** w C#, **jak ustawić wymiary kodu kreskowego**, **jak regulować wysokość kodu kreskowego** oraz **generować pliki PNG kodu kreskowego** dla dowolnych wymagań wizualnych. Poprzez dostosowanie `XDimension` i `BarHeight` możesz tworzyć kompaktowe lub duże kody kreskowe bez zmiany samej treści danych.

Następnie, poznaj tematy pokrewne, takie jak **dynamiczna zmiana wysokości kodu kreskowego** w zależności od danych wejściowych, osadzanie kodów kreskowych w raportach PDF przy użyciu Aspose.PDF lub przejście do generowania kodów QR przy pomocy `EncodeTypes.QR`. Eksperymentuj z różnymi symbologiami i formatami wyjściowymi, aby w pełni opanować tworzenie kodów kreskowych w C#.

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}