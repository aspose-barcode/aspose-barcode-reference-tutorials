---
category: general
date: 2026-10-21
description: Dowiedz się, jak generować obrazy kodów kreskowych w C# oraz jak eksportować
  pliki kodów kreskowych jako PNG przy użyciu Aspose.BarCode, aby uzyskać szybkie
  i niezawodne wyniki.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: pl
lastmod: 2026-10-21
og_description: Jak generować obrazy kodów kreskowych w C# oraz jak eksportować pliki
  kodów kreskowych jako PNG. Skorzystaj z tego pełnego samouczka, aby tworzyć kody
  kreskowe Planet i RM4SCC przy użyciu Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Jak generować obrazy kodów kreskowych i eksportować je w C# – przewodnik
  krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak generować obrazy kodów kreskowych i eksportować je w C#
url: /pl/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować obrazy kodów kreskowych i eksportować je w C#

Jeśli potrzebujesz **jak generować kod kreskowy** obrazy w aplikacji .NET, ten przewodnik pokazuje dokładne kroki tworzenia kodów kreskowych Planet i RM4SCC oraz **jak eksportować kod kreskowy** jako pliki PNG. Otrzymasz gotowy do uruchomienia przykład kodu, opis każdego ustawienia oraz wskazówki dotyczące typowych pułapek.

Tutorial obejmuje:

* Dodanie pakietu NuGet Aspose.BarCode
* Konfigurowanie szerokości modułu i opcjonalnej wysokości kreski
* Zapisywanie wygenerowanych kodów kreskowych na dysku
* Weryfikacja plików wyjściowych

> **Wymaganie wstępne** – .NET 6+ SDK, Visual Studio 2022 (lub dowolne IDE) oraz połączenie internetowe do pobrania pakietu Aspose.BarCode.

## Co osiągniesz

Pod koniec tego artykułu będziesz w stanie:

* Wygenerować kod kreskowy **Planet** z automatyczną wysokością kreski.
* Wygenerować kod kreskowy **RM4SCC** z automatyczną wysokością kreski.
* Zastąpić domyślną wysokość i uzyskać kod kreskowy o wysokości 100 pikseli.
* Eksportować każdy kod kreskowy do pliku PNG w wybranym folderze.

## Krok 1: Zainstaluj Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet udostępnia klasę `BarcodeGenerator` oraz wyliczenie `EncodeTypes` używane w poniższym kodzie.

## Krok 2: Skonfiguruj folder wyjściowy

Utwórz folder, w którym będą przechowywane pliki PNG. Folder może być podany jako ścieżka bezwzględna lub względna względem katalogu głównego projektu.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Wskazówka:** Użycie `Path.Combine` unika twardo zakodowanych separatorów ścieżek i działa na Windows, macOS i Linux.

## Krok 3: Generuj kody kreskowe z automatyczną wysokością kreski

Gdy nie określisz wysokości kreski, Aspose.BarCode wybiera rozmiar pasujący do zakodowanych danych. Poniższy kod tworzy dwa kody kreskowe — Planet i RM4SCC — używając szerokości modułu 4 piksele.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Dlaczego to działa:**  
* `EncodeTypes.Planet` i `EncodeTypes.RM4SCC` określają, której symbologii użyć.  
* `XDimension.Pixels` definiuje szerokość pojedynczego modułu kodu kreskowego; wartość 4 px daje wyraźny, możliwy do zeskanowania obraz.  
* Ponieważ `BarHeight` nie jest ustawione, biblioteka automatycznie oblicza optymalną wysokość.

## Krok 4: Generuj kody kreskowe o stałej wysokości 100 pikseli

Jeśli Twój projekt wymaga określonej wysokości kreski, możesz nadpisać automatyczne obliczenia:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Dlaczego możesz potrzebować stałej wysokości:**  
Specyfikacje projektowe etykiet wysyłkowych często określają dokładne wymiary kreski, aby zapewnić kompatybilność ze skanerami kodów kreskowych. Ustawienie `BarHeight.Pixels` gwarantuje jednolitość we wszystkich wygenerowanych obrazach.

## Krok 5: Zweryfikuj wyeksportowane pliki

Po uruchomieniu programu folder `Barcodes` zawiera cztery pliki PNG:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Otwórz dowolny z nich w przeglądarce obrazów lub osadź w PDF, aby potwierdzić prawidłowe renderowanie. Jeśli skaner nie odczyta kodu kreskowego, zwiększ wartość `XDimension.Pixels` lub ponownie sprawdź długość ciągu wejściowego.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Powinieneś zobaczyć wyjście podobne do:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę eksportować do formatów innych niż PNG?** | Tak. Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp`, `Gif` lub `Tiff`. |
| **Co jeśli moje dane zawierają znaki niedozwolone przez symbologię?** | Generator zgłasza `ArgumentException`. Zweryfikuj dane wejściowe lub przełącz się na symbologię obsługującą dany zestaw znaków. |
| **Jak zmienić kolory pierwszego planu/tła?** | Ustaw `Parameters.Barcode.ForeColor` i `Parameters.Barcode.BackColor` przed wywołaniem `Save`. |
| **Czy istnieje sposób generowania kodów kreskowych w pamięci zamiast zapisywania na dysk?** | Wywołaj `GenerateBarCodeImage()`, aby uzyskać obiekt `System.Drawing.Image`, a następnie manipuluj nim lub przesyłaj w strumieniu w razie potrzeby. |

## Porada: przetwarzanie wsadowe

Gdy potrzebujesz utworzyć wiele kodów kreskowych (np. dla listy mailingowej), otocz logikę generowania w pętli `foreach`:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Ten wzorzec skaluje się do tysięcy kodów kreskowych, zachowując zwięzłość kodu.

## Podsumowanie

Teraz wiesz **jak generować obrazy kodów kreskowych** w C# oraz **jak eksportować pliki kodów kreskowych** jako PNG przy użyciu Aspose.BarCode. Pełny przykład pokazuje zarówno generowanie automatyczne, jak i o stałej wysokości dla symbologii Planet i RM4SCC, dając solidną podstawę dla każdego projektu związanego z kodami kreskowymi.

**Kolejne kroki**

* Poznaj inne symbologie, takie jak Code128, QR lub DataMatrix.  
* Eksperymentuj z dostosowaniem kolorów (`ForeColor`, `BackColor`).  
* Zintegruj wygenerowane PNG z fakturami PDF lub etykietami wysyłkowymi przy użyciu biblioteki PDF.  

Miłego kodowania i niech Twoje kody kreskowe skanują się płynnie!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Utwórz obrazy kodów GS1 w C# – Jak szybko generować kod kreskowy w C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [jak generować obraz kodu kreskowego z Aspose.BarCode w C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}