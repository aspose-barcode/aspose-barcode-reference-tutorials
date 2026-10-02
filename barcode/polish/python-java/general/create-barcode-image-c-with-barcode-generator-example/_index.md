---
category: general
date: 2026-09-10
description: Szybko utwórz obraz kodu kreskowego w C# przy użyciu przykładu generatora
  kodów kreskowych w C#, który pokazuje, jak ustawić wymiary i zapisać pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: pl
lastmod: 2026-09-10
og_description: Utwórz obraz kodu kreskowego w C# za pomocą zwięzłego przykładu generatora
  kodów kreskowych w C#. Dowiedz się, jak skonfigurować rozmiar, wysokość i eksportować
  pliki PNG w kilka minut.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Tworzenie obrazu kodu kreskowego w C# – przykład generatora krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Tworzenie obrazu kodu kreskowego w C# z przykładem generatora kodu kreskowego
url: /pl/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego C# przy użyciu przykładu generatora kodów kreskowych

Jeśli potrzebujesz **create barcode image C#** do etykietowania produktów, śledzenia zapasów lub skanowania mobilnego, ten przewodnik pokazuje pełne rozwiązanie. Zobaczysz **barcode generator example C#**, który konfiguruje szerokość modułu, wysokość pasków i zapisuje pliki PNG w zaledwie kilku linijkach kodu.

Poradnik obejmuje wszystko, od instalacji wymaganego biblioteki po uruchomienie gotowego do kompilacji programu konsolowego. Po zakończeniu będziesz mieć dwa pliki PNG z kodem kreskowym — jeden z wysokością paska 30 pikseli i drugi z wysokością paska 60 pikseli — gotowe do użycia w dowolnej aplikacji .NET.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Środowisko programistyczne, takie jak Visual Studio 2022 lub VS Code  
* Pakiet NuGet **Aspose.BarCode** (kod używa `BarcodeGenerator` z tej biblioteki)  

Możesz dodać pakiet za pomocą następującego polecenia CLI:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Skonfiguruj projekt konsolowy

Utwórz nowy projekt konsolowy i odwołaj się do biblioteki kodów kreskowych.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Polecenie tworzy plik `Program.cs`, w którym umieścisz kod **barcode generator example C#**.

## Krok 2: Napisz pełny program generujący kod kreskowy

Zastąp zawartość `Program.cs` kompletnym, działającym przykładem poniżej. Program demonstruje, jak **create barcode image C#** z własnymi wymiarami i jak zapisać wynik jako pliki PNG.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Dlaczego każdy wiersz ma znaczenie

* **EncodeTypes.DatabarOmniDirectional** – wybiera symbolikę DataBar Omnidirectional, która koduje dane numeryczne i jest szeroko stosowana w handlu detalicznym.  
* **XDimension.Pixels = 2** – ustawia szerokość modułu; mniejsza wartość daje bardziej kompaktowy kod kreskowy.  
* **BarHeight.Pixels** – kontroluje wizualną wysokość pasków. Dostosowanie tej wartości pozwala tworzyć kody kreskowe pasujące do różnych rozmiarów etykiet.  
* **Save method** – zapisuje kod kreskowy do pliku PNG, formatu zachowującego ostre krawędzie i działającego z większością bibliotek graficznych.

## Krok 3: Zbuduj i uruchom program

Wykonaj następujące polecenie z folderu projektu:

```bash
dotnet run
```

Po zakończeniu programu zobaczysz dwa pliki PNG w podfolderze `output`:

* `DatabarBarHeight30Pixels.png` – wysokość paska 30 pikseli  
* `DatabarBarHeight60Pixels.png` – wysokość paska 60 pikseli  

Oba obrazy zawierają te same zakodowane dane, ale różnią się wysokością wizualną, co ilustruje, jak **barcode generator example C#** można dostosować do różnych wymagań etykiet.

## Krok 4: Zweryfikuj wygenerowane kody kreskowe

Otwórz pliki PNG w dowolnym przeglądarce obrazów. Powinieneś zobaczyć wyraźny, wysokokontrastowy kod DataBar. Aby potwierdzić, że kody są czytelne, możesz użyć aplikacji skanującej na telefon (np. aplikacje oparte na ZXing) lub biblioteki desktopowej takiej jak **Aspose.BarCode** w trybie dekodowania:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Jeśli wynik odpowiada `(01)12345678901231`, generowanie zakończyło się sukcesem.

## Typowe wariacje i przypadki brzegowe

| Sytuacja | Dostosowanie | Fragment kodu |
|-----------|------------|--------------|
| **Inna symbolika** (np. QR, Code128) | Zmień wartość `EncodeTypes` | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Niestandardowy format obrazu** (JPEG, BMP) | Użyj innego wyliczenia `BarCodeImageFormat` | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamiczne dane** (wejście użytkownika) | Zastąp na stałe zakodowany ciąg zmienną | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Nieprawidłowa długość danych** | Przechwyć `ArgumentException` zgłaszany przez generator | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Pro tip: zawsze weryfikuj długość wejścia dla wybranej symboliki; Aspose.BarCode zgłasza wyjątek, jeśli dane nie spełniają specyfikacji.

## Lista kontrolna rozwiązywania problemów

* **Directory not found** – Pomocnicza metoda `SaveBarcode` tworzy folder `output` automatycznie, ale upewnij się, że aplikacja ma uprawnienia do zapisu.  
* **Unexpected image size** – Sprawdź, czy `XDimension.Pixels` i `BarHeight.Pixels` są ustawione przed wywołaniem `Save`. Zmiana tych wartości po zapisaniu nie wpływa na już zapisane pliki.  
* **Unreadable barcode** – Upewnij się, że zakodowany ciąg spełnia format GS1 przy użyciu symbolik DataBar. Brakujące nawiasy lub nieprawidłowe identyfikatory aplikacji powodują niepowodzenia w dekodowaniu.

## Zakończenie

Teraz wiesz, jak **create barcode image C#** przy użyciu praktycznego **barcode generator example C#**. Pełny program ustawia szerokość modułu, dostosowuje wysokość pasków i zapisuje pliki PNG przy minimalnym kodzie. Od tego momentu możesz eksplorować dodatkowe funkcje, takie jak dostosowanie kolorów, eksport wielostronicowego PDF lub generowanie w czasie rzeczywistym w API webowych ASP.NET Core.

**Next steps**

* Eksperymentuj z innymi symbolikami (`EncodeTypes.Code128`, `EncodeTypes.QR`), aby poszerzyć możliwości skanowania.  
* Zintegruj generator z usługą webową, która zwraca obrazy kodów kreskowych na żądanie.  
* Połącz kod kreskowy z metadanymi produktu w fakturze PDF przy użyciu Aspose.PDF.

Miłego kodowania i ciesz się elastycznością, jaką C# zapewnia przy tworzeniu obrazów kodów kreskowych!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Utwórz obraz kodu kreskowego C# – Przykład GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Przykład generatora kodów kreskowych – Tworzenie obrazu DataBar w C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}