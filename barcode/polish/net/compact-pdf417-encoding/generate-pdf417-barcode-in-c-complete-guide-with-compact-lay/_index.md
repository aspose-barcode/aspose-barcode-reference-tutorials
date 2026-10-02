---
category: general
date: 2026-08-19
description: Szybko generuj kod kreskowy PDF417 w C#. Dowiedz się, jak generować kod
  kreskowy PDF417 w C# przy użyciu Aspose.BarCode w trybie kompaktowym i z własnymi
  ustawieniami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: pl
lastmod: 2026-08-19
og_description: Generuj kod kreskowy PDF417 w C# za pomocą Aspose.BarCode. Ten samouczek
  pokazuje, jak wygenerować kod kreskowy PDF417 w C# w trybie kompaktowym, ustawić
  wymiar X i zapisać jako PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Generowanie kodu kreskowego PDF417 w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik z kompaktowym
  układem
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego PDF417 w C# – kompletny przewodnik

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten tutorial pokaże Ci dokładnie, jak to zrobić. Zobaczysz zwięzły, gotowy do produkcji przykład, który tworzy kompaktowy kod PDF417, dostosowuje wymiar X‑dimensji i zapisuje wynik jako obraz PNG.

Generowanie kodu PDF417 jest powszechne, gdy trzeba zakodować duże ilości danych — takich jak informacje o bilecie, listy przewozowe czy dokumenty tożsamości — w formacie czytelnym maszynowo. Dzięki Aspose.BarCode proces jest prosty, a kod działa z .NET 6+ lub .NET Framework 4.7.2 i nowszymi.

W tym przewodniku dowiesz się, jak:

* Zainstalować pakiet NuGet Aspose.BarCode.
* Napisać samodzielny program w C#, który **generuje kod PDF417** z małą liczbą kolumn i w trybie kompaktowym (truncated).
* Dostosować szerokość kreski (X‑dimension) dla ostrzejszego renderowania.
* Zapisz kod kreskowy jako plik PNG.
* Poznać warianty, przypadki brzegowe i wskazówki najlepszych praktyk.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Visual Studio 2022 (lub dowolne IDE C#) z zainstalowanym .NET 6 SDK.
* Dostęp do Internetu, aby pobrać pakiet **Aspose.BarCode** NuGet.
* Uprawnienia do zapisu w folderze, w którym zostanie zapisany plik PNG.

Nie są potrzebne dodatkowe biblioteki; Aspose.BarCode obsługuje kodowanie obrazu wewnętrznie.

## Krok 1: Dodaj pakiet Aspose.BarCode

Otwórz projekt w Visual Studio, kliknij prawym przyciskiem myszy rozwiązanie i wybierz **Manage NuGet Packages**. Wyszukaj `Aspose.BarCode` i zainstaluj najnowszą stabilną wersję.

```bash
dotnet add package Aspose.BarCode
```

> **Porada:** Utrzymuj pakiet w aktualności. Nowe wydania często zawierają usprawnienia wydajności i wsparcie dla najnowszych środowisk .NET.

## Krok 2: Utwórz minimalną aplikację konsolową

Utwórz nowy projekt konsolowy C#, jeśli jeszcze go nie masz:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Zastąp zawartość pliku `Program.cs` pełnym przykładem poniżej. Program ten demonstruje **jak wygenerować kod PDF417 w C#** od początku do końca.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

* **`EncodeTypes.Pdf417`** – wybiera symbologię PDF417, która obsługuje do ~1,1 KB danych.
* **`XDimension.Pixels = 2`** – ustawia podstawową szerokość kreski. Mniejsze wartości sprawiają, że kod jest cieńszy; większe wartości poprawiają czytelność na urządzeniach o niskiej rozdzielczości.
* **`Pdf417.Columns = 3`** – ogranicza liczbę kolumn, wymuszając użycie większej liczby wierszy, co skutkuje wyższym, ale węższym kodem.
* **`Pdf417.Truncate = true`** – aktywuje tryb kompaktowy, usuwając wzorzec stop i zmniejszając obraz bez utraty integralności danych.
* **`Save(..., BarCodeImageFormat.Png)`** – zapisuje plik PNG. Możesz także wybrać `Jpeg`, `Bmp` lub `Svg` w zależności od dalszych potrzeb.

Uruchom program:

```bash
dotnet run
```

Powinieneś zobaczyć w konsoli komunikat potwierdzający lokalizację pliku, a w folderze znajdzie się `CompactPdf417.png`. Otwierając PNG zobaczysz wyraźny, kompaktowy kod PDF417, który koduje łańcuch Unicode.

## Krok 3: Zweryfikuj kod kreskowy (opcjonalnie, ale zalecane)

Aby upewnić się, że kod jest czytelny, możesz użyć dowolnej standardowej aplikacji skanującej PDF417 na smartfonie lub biblioteki dekodującej na komputerze. Zakodowany tekst powinien dokładnie odpowiadać oryginalnemu łańcuchowi `data`, łącznie ze znakami specjalnymi.

Jeśli napotkasz problemy z dekodowaniem:

* Zwiększ `XDimension` do 3 lub 4 pikseli.
* Zmniejsz liczbę kolumn (np. ustaw `Columns = 2`).
* Wyłącz `Truncate` (`Truncate = false`), aby dodać wzorzec stop.

Te korekty wymieniają rozmiar na czytelność, co jest przydatne przy drukarkach lub skanerach o niskiej rozdzielczości.

## Krok 4: Poznaj typowe warianty

### 4️⃣ Generowanie kodu PDF417 o wysokiej gęstości do druku

Jeśli potrzebujesz kodu, który zmieści się na małej etykiecie, zwiększ liczbę kolumn i obniż X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Zmiana formatu wyjściowego na SVG dla skalowania wektorowego

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Wyjście SVG skaluje się bez utraty jakości, idealne dla responsywnych stron internetowych.

### 6️⃣ Kodowanie danych binarnych (np. tablicy bajtów)

Jeśli musisz osadzić ładunek binarny, najpierw przekształć go w łańcuch Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Kod kreskowy teraz przenosi informacje binarne, a dekoder musi odwrócić krok Base64.

## Najczęściej zadawane pytania

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę generować PDF417 bez Aspose?** | Tak, istnieją inne biblioteki, takie jak ZXing.Net czy Dynamsoft, ale Aspose.BarCode oferuje bogatszą kontrolę układu (kolumny, przycinanie) oraz lepsze wsparcie Unicode. |
| **Jaka jest maksymalna długość danych?** | PDF417 może zakodować do 1 108 bajtów (≈ 1 KB) danych binarnych. Jeśli przekroczysz tę wartość, rozważ podzielenie danych na kilka kodów kreskowych. |
| **Czy tryb kompaktowy jest zgodny ze standardem?** | Skrócony PDF417 jest częścią specyfikacji ISO/IEC 15438 i jest szeroko wspierany, ale upewnij się, że docelowy skaner explicite go obsługuje. |
| **Jak zmienić kolor tła?** | Ustaw `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` oraz `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` przed zapisem. |

## Zakończenie

Teraz wiesz **jak generować kod PDF417 w C#** przy użyciu Aspose.BarCode, jak precyzyjnie dostroić X‑dimension, włączyć tryb kompaktowy i wyeksportować wynik jako obraz PNG. Pełny, gotowy do uruchomienia przykład możesz skopiować do dowolnego projektu .NET, a przedstawione warianty pozwolą Ci dostosować kod do druku, sieci czy scenariuszy z ładunkiem binarnym.

Kolejne kroki, które możesz rozważyć:

* Zintegrować generowanie kodu kreskowego w API ASP.NET Core, które zwraca obraz na żądanie.
* Połączyć PDF417 z kodami QR na tej samej etykiecie dla podwójnego skanowania.
* Skorzystać z klasy `Reader` Aspose.BarCode, aby programowo odczytać wygenerowany obraz i zweryfikować dane.

Miłego kodowania i ciesz się elastycznością, jaką **generowanie kodu PDF417** daje Twoim aplikacjom!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}