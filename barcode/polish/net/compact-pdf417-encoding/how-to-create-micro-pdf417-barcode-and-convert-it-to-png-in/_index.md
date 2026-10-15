---
category: general
date: 2026-10-12
description: Naucz się tworzyć mikro‑kod PDF417 i konwertować kod kreskowy na PNG
  przy użyciu C#. Przewodnik krok po kroku z pełnym kodem i wskazówkami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: pl
lastmod: 2026-10-12
og_description: Utwórz mikrokod PDF417 i przekonwertuj kod kreskowy na PNG w C#. Skorzystaj
  z tego kompletnemu przewodnika, aby wygenerować zarówno wersję standardową, jak
  i GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Utwórz mikro kod kreskowy PDF417 i przekonwertuj go na PNG – samouczek C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak utworzyć mikro kod kreskowy PDF417 i przekonwertować go na PNG w C#
url: /pl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć mikro PDF417 kod kreskowy i przekonwertować go na PNG w C#

Jeśli potrzebujesz **utworzyć mikro PDF417 kod kreskowy** w aplikacji .NET, ten samouczek pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, działający przykład, który generuje zarówno standardowy kod Micro PDF417, jak i wersję zgodną z GS1, a następnie **konwertuje kod kreskowy na PNG** do dalszego użycia, takiego jak drukowanie lub wyświetlanie w sieci.

Generowanie kodu kreskowego to nie tylko wywołanie jednej metody — wybór odpowiedniego rozmiaru modułu, liczby kolumn i formatu kodowania decyduje o niezawodności skanowania. Po przeczytaniu tego przewodnika zrozumiesz, dlaczego każde ustawienie ma znaczenie i jak je dostosować do własnych projektów.

## Wymagania wstępne

| Wymaganie | Powód |
|-------------|--------|
| .NET 6.0 SDK lub nowszy | Zapewnia środowisko uruchomieniowe dla aplikacji konsolowej C# |
| Visual Studio 2022 (lub dowolne IDE C#) | Ułatwia edycję i debugowanie |
| **Aspose.BarCode for .NET** pakiet NuGet | Dostarcza klasy `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat` |
| Uprawnienia zapisu do folderu wyjściowego | Wymagane dla wywołań `Save`, które tworzą pliki PNG |

Możesz dodać pakiet Aspose.BarCode za pomocą CLI:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Utwórz minimalny projekt konsolowy

Utwórz nowy projekt konsolowy i odwołaj się do biblioteki kodów kreskowych. Poniższy plik `Program.cs` zawiera cały potrzebny kod; nie są wymagane żadne zewnętrzne pliki.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Dlaczego każdy wiersz ma znaczenie

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Pierwszy tworzy zwykły kod Micro PDF417, natomiast drugi spełnia standardy GS1, wstawiając identyfikatory aplikacji (AI). Wybierz w zależności od tego, czy Twój system downstream oczekuje danych GS1.
* **`XDimension.Pixels = 2`** – Kontroluje szerokość modułu. Mniejsze wartości tworzą gęstszy obraz, ale mogą stać się nieczytelne na skanerach o niskiej rozdzielczości. Dwa piksele to bezpieczna domyślna wartość dla większości drukarek etykiet.
* **`Pdf417.Columns = 4`** – Micro PDF417 pozwala ograniczyć liczbę kolumn, zmniejszając całkowitą szerokość. Cztery kolumny utrzymują kod kompaktowy, nie tracąc pojemności danych przy krótkich ładunkach.
* **`BarCodeImageFormat.Png`** – PNG zachowuje jakość bezstratną, co jest kluczowe dla czytelności kodu kreskowego. Dlatego **konwertujemy kod kreskowy na PNG**, a nie na JPEG.

## Krok 2: Uruchom program i zweryfikuj wynik

1. Zbuduj projekt: `dotnet build`.
2. Uruchom: `dotnet run`.

Powinieneś zobaczyć komunikaty w konsoli podobne do:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Otwórz wygenerowane pliki PNG dowolnym przeglądarką obrazów. Oba obrazy wyświetlają wyraźny, wysokokontrastowy kod kreskowy gotowy do skanowania.

### Oczekiwany wygląd wizualny

| Typ kodu kreskowego | Wygląd |
|--------------|------------|
| **Micro PDF417** | Mały prostokątny wzór z 4 kolumnami, czytelny dla większości skanerów kodów 2‑D. |
| **GS1 Micro PDF417** | Ten sam rozmiar, ale koduje AI GS1; skaner rozumiejący GS1 zwróci GTIN i numer seryjny. |

Jeśli skaner nie odczyta obrazu, spróbuj zwiększyć `XDimension.Pixels` do **3** lub **4**, lub zmniejsz liczbę kolumn dla standardowego Micro PDF417.

## Częste pułapki i jak ich unikać

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| Rozmyty kod po drukowaniu | Ustawienia drukarki o niskiej DPI | Eksportuj PNG w 300 dpi lub wyższym, lub pozwól sterownikowi drukarki obsłużyć skalowanie. |
| Skaner zwraca „nieprawidłowe dane” | Brak lub niepoprawny format AI GS1 | Upewnij się, że każdy AI jest otoczony nawiasami i zgodny ze specyfikacją GS1 (np. `(01)` dla GTIN‑14). |
| Plik obrazu nie został utworzony | Folder wyjściowy nie ma uprawnień do zapisu | Uruchom program z podwyższonymi uprawnieniami lub wybierz folder, np. `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Kod zbyt duży dla etykiety | Domyślna liczba kolumn jest za wysoka | Zredukuj `Pdf417.Columns` (np. do **3**) lub zwiększ `XDimension`, aby zmniejszyć całkowity rozmiar. |

## Rozszerzanie przykładu

* **Różne formaty obrazu** – Zastąp `BarCodeImageFormat.Png` `Jpeg` lub `Bmp`, jeśli Twój przepływ pracy tego wymaga. PNG pozostaje najlepszym wyborem dla jakości bezstratnej.
* **Dynamiczne dane** – Przekaż dane wejściowe użytkownika lub wartości z bazy danych do konstruktora `BarcodeGenerator`, aby tworzyć kody kreskowe w locie.
* **Generowanie wsadowe** – Umieść logikę tworzenia w pętli, która odczytuje wiersze z pliku CSV i zapisuje każdy kod kreskowy pod unikalną nazwą pliku.

## Podsumowanie

Teraz wiesz, jak **utworzyć mikro PDF417 kod kreskowy** w C# i **konwertować kod kreskowy na PNG** zarówno w scenariuszach standardowych, jak i zgodnych z GS1. Kompletny, działający kod demonstruje kluczowe ustawienia — wymiar X, liczbę kolumn i typ kodowania — dzięki czemu możesz dostosować rozwiązanie do dowolnego projektu .NET, który potrzebuje kompaktowych, wysokiej jakości kodów 2‑D.

*Kolejne kroki*: zapoznaj się z innymi symbologiami obsługiwanymi przez Aspose.BarCode (np. QR, DataMatrix), eksperymentuj z różnymi wartościami `XDimension` dla druku wysokiej rozdzielczości lub zintegrować wygenerowane PNG z API internetowym, które dostarcza kody kreskowe na żądanie.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć mikro pdf417 kod kreskowy w C# i zapisać go jako PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Utwórz PNG kodu kreskowego w C# – pełny przewodnik po GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Generuj Micro PDF417 kod kreskowy w C# – Kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}