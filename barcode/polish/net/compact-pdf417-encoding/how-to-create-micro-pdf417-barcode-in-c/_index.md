---
category: general
date: 2026-11-14
description: Utwórz mikro‑kod PDF417 w C# przy użyciu Aspose.BarCode – przewodnik
  krok po kroku obejmujący konfigurację generatora, wymiar X, kolumny i eksport do
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: pl
lastmod: 2026-11-14
og_description: Utwórz mikro kod kreskowy PDF417 w C# przy użyciu Aspose.BarCode.
  Dowiedz się, jak skonfigurować generator, ustawić XDimension, wybrać kolumny i wyeksportować
  jako PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Utwórz mikro kod kreskowy PDF417 w C# – pełny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Jak utworzyć mikro kod kreskowy PDF417 w C#
url: /pl/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć mikro kod PDF417 w C#  

Jeśli potrzebujesz szybko **utworzyć mikro kod PDF417**, ten przewodnik pokaże Ci kompletne, gotowe do uruchomienia rozwiązanie. Zobaczysz, jak zainicjować generator kodów kreskowych, skonfigurować wymiar X, wybrać liczbę kolumn oraz ostatecznie zapisać wynik jako obraz PNG — wszystko przy użyciu biblioteki Aspose.BarCode dla .NET.

Generowanie mikro kodu PDF417 nie wymaga skomplikowanego potoku budowania. Po zakończeniu tego samouczka będziesz mieć pojedynczy plik C#, który generuje wysokiej jakości obraz kodu kreskowego, który możesz osadzić w raportach, etykietach lub aplikacjach mobilnych.

## Wymagania wstępne  

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+).  
* Środowisko programistyczne, takie jak Visual Studio 2022, VS Code lub Rider.  
* Licencję Aspose.BarCode dla .NET (lub darmowy klucz ewaluacyjny). Możesz ją uzyskać ze [strony Aspose](https://purchase.aspose.com/barcode/net).  

> **Wskazówka:** Jeśli używasz wersji ewaluacyjnej, wygenerowany plik PNG będzie zawierał małą znak wodny „Evaluation”. Wersja licencjonowana usuwa ją automatycznie.

## Krok 1: Konfiguracja projektu  

Utwórz nowy projekt konsolowy i dodaj pakiet NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Polecenie `dotnet add package` pobiera zależności **przykładu Aspose.BarCode C#**, więc nie musisz ręcznie zarządzać plikami DLL.

## Krok 2: Napisz kompletny kod  

Zastąp automatycznie wygenerowany plik `Program.cs` poniższym kodem. Pokazuje on, jak **utworzyć mikro kod pdf417** od początku do końca.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Dlaczego każdy wiersz ma znaczenie  

* **BarcodeGenerator constructor** – Tworzy **generator mikro pdf417** z tekstem, który chcesz zakodować.  
* **XDimension.Pixels** – Kontroluje szerokość modułu; ustawienie na `2` piksele daje gęsty, wysokiej rozdzielczości kod kreskowy odpowiedni dla większości skanerów.  
* **Pdf417.Columns** – MicroPDF417 obsługuje tylko 1‑4 kolumny. Wybranie `4` zmniejsza wysokość kodu, co jest przydatne przy ograniczonej przestrzeni pionowej.  
* **Save method** – Zapisuje kod kreskowy do pliku PNG. PNG jest bezstratny, zapewniając, że skaner odczyta dokładny wzór, który wygenerowano.  

## Krok 3: Kompilacja i uruchomienie  

Skompiluj i uruchom program:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście w konsoli:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Plik o nazwie **MicroPdf417.png** pojawi się w folderze projektu. Otwórz go w dowolnej przeglądarce obrazów; zobaczysz wyraźny mikro kod PDF417, który koduje ciąg znaków `"Åspóse.Barcóde©"`.

![Wygenerowany przykład mikro kodu PDF417](MicroPdf417.png "Wygenerowany przykład mikro kodu PDF417"){.center-image width=400 alt="Wygenerowany przykład obrazu mikro kodu PDF417"}

*Powyższy obraz jest wynikiem kodu przedstawionego w Kroku 2.*

## Krok 4: Typowe warianty i przypadki brzegowe  

| Sytuacja | Jak dostosować kod |
|-----------|----------------------|
| **Różna długość danych** | MicroPDF417 może kodować do 1 200 znaków. Po prostu zmień drugi argument `BarcodeGenerator`. |
| **Wyższa rozdzielczość** | Zwiększ `XDimension.Pixels` do `3` lub `4`. Większe moduły poprawiają czytelność na skanerach o niskiej rozdzielczości, ale zwiększają rozmiar obrazu. |
| **Niestandardowe kolory** | Po utworzeniu generatora ustaw `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` oraz `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Zapisywanie w innych formatach** | Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Gif` w zależności od wymagań downstream. |
| **Osadzanie w PDF** | Użyj `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` a następnie połącz PDF z innymi dokumentami przy użyciu Aspose.PDF. |

> **Uwaga:** Ustawienie `XDimension.Pixels` poniżej `1` powoduje wyrzucenie `ArgumentOutOfRangeException`. Zawsze ustawiaj wartość `1` lub wyższą.

## Krok 5: Weryfikacja kodu kreskowego  

Aby upewnić się, że kod kreskowy skanuje się poprawnie:

1. Otwórz plik PNG w przeglądarce obrazów.  
2. Użyj dowolnej aplikacji skanującej kody kreskowe na smartfonie, która obsługuje PDF417 (większość aplikacji „skaner QR‑kodów” ją zawiera).  
3. Zeskanuj obraz; aplikacja powinna wyświetlić oryginalny tekst `"Åspóse.Barcóde©"`.

Jeśli skanowanie się nie powiedzie, dokładnie sprawdź ustawienia **X‑dimension** i **column** — zbyt mała szerokość modułu lub nieobsługiwana liczba kolumn może spowodować, że wzór będzie nieczytelny.

## Zakończenie  

Teraz wiesz, jak **utworzyć mikro kod pdf417** w C# przy użyciu Aspose.BarCode. Samouczek obejmował:

* Inicjalizację **generatora mikro pdf417**.  
* **Ustawienie XDimension w pikselach** w celu kontroli szerokości modułu.  
* **Zdefiniowanie kolumn kodu kreskowego** w celu dopasowania kształtu.  
* **Zapisanie kodu kreskowego jako PNG** dla bezstratnego wyjścia obrazu.  

Od tego momentu możesz eksplorować dodatkowe funkcje, takie jak dostosowanie kolorów, osadzanie kodu w PDF‑ach lub generowanie kodów w locie w interfejsach API ASP.NET Core. Miłego kodowania!

## Co warto nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod kreskowy PNG w C# – pełny przewodnik po GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Jak utworzyć makro kod PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Utwórz kod PDF417 w C# przy użyciu Aspose.BarCode – przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}