---
category: general
date: 2026-09-19
description: przykład generatora kodów kreskowych pokazujący, jak zmienić wysokość,
  utworzyć DataBar Omni‑Directional oraz dostosować wymiary kodu kreskowego dla wyjścia
  obrazu w C#
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: pl
lastmod: 2026-09-19
og_description: przykład generatora kodów kreskowych, który uczy, jak zmienić wysokość,
  utworzyć DataBar Omni‑Directional oraz dostosować wymiary kodu kreskowego dla obrazu
  PNG w C#
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Przykład generatora kodów kreskowych w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak stworzyć przykład generatora kodów kreskowych w C#
url: /pl/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych w C# – kompletny przewodnik programistyczny

Jeśli potrzebujesz **przykładu generatora kodów kreskowych** dla projektu .NET, ten przewodnik pokaże Ci dokładnie, jak utworzyć, skonfigurować i zapisać kod kreskowy DataBar Omni‑Directional przy użyciu C#. Nauczysz się, jak zmienić wysokość, dostosować wymiary kodu kreskowego oraz wyeksportować wysokiej jakości obraz PNG — wszystko w jednej, uruchamialnej aplikacji konsolowej.

Poniższe kroki obejmują wszystko, od instalacji wymaganego SDK po dostosowanie wymiaru X i wysokości paska. Po zakończeniu samouczka będziesz mieć gotowy do użycia generator kodów kreskowych, który możesz zintegrować z fakturowaniem, inwentaryzacją lub dowolnym procesem skanowania.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)  
* Aktywną licencję na **Aspose.BarCode for .NET** (bezpłatna wersja próbna działa do testów)

Jeśli wolisz inną bibliotekę, koncepcje dostosowywania wymiarów i zapisywania obrazu pozostają takie same; po prostu zamień wywołania API odpowiednio.

## Krok 1: Skonfiguruj projekt i dodaj pakiet Aspose.BarCode

Utwórz nowy projekt konsolowy i odwołaj się do biblioteki kodów kreskowych.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Polecenie `dotnet add package` pobiera najnowszą stabilną wersję Aspose.BarCode, która zawiera pełne wsparcie dla symboli DataBar Omni‑Directional.

## Krok 2: Napisz kompletny przykład generatora kodów kreskowych

Otwórz **Program.cs** i zamień jego zawartość na poniższy kod. Ten blok zawiera pełny **przykład generatora kodów kreskowych** — bez brakujących fragmentów.

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

* **Create a barcode generator** – Konstruktor `BarcodeGenerator` wiąże typ kodowania (`EncodeTypes.DatabarOmniDirectional`) z danymi, które chcesz zakodować. To jest sedno kroku **how to create databar**.  
* **Adjust barcode dimensions** – Właściwość `XDimension.Pixels` definiuje szerokość najwęższego paska. Zmiana tej wartości wpływa na ogólny rozmiar i niezawodność skanowania.  
* **How to change height** – Właściwość `BarHeight.Pixels` kontroluje rozmiar pionowy. Zwiększenie wysokości poprawia czytelność dla skanerów ręcznych, natomiast zmniejszenie oszczędza miejsce na małych etykietach.  
* **Optional tweaks** – Ustawienie kolorów pierwszego planu/tła lub poziomów korekcji błędów jest opcjonalne, ale demonstruje, jak rozszerzyć koncepcję **adjust barcode dimensions**.  
* **Create barcode image C#** – Metoda `Save` zapisuje kod kreskowy na dysku. Użycie `BarCodeImageFormat.Png` zapewnia bezstratną kompresję, co jest idealne dla większości zastosowań.

## Krok 3: Zbuduj i uruchom przykład

Skompiluj i uruchom program:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście w konsoli:

```
Barcode saved to DatabarOmniDirectional.png
```

Plik o nazwie **DatabarOmniDirectional.png** pojawia się w folderze projektu. Otworzenie obrazu pokazuje wyraźny kod kreskowy DataBar Omni‑Directional gotowy do skanowania.

## Jak zmienić wysokość po wygenerowaniu

Jeśli potrzebujesz generować kody kreskowe o różnych wysokościach, umieść przypisanie wysokości w metodzie:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Wywołaj `SetBarHeight(generator, 45);` przed `Save`. To podejście pozwala Ci **how to change height** dynamicznie w zależności od danych wejściowych użytkownika lub plików konfiguracyjnych.

## Jak tworzyć kody DataBar Omni‑Directional z różnymi danymi

Symbologia DataBar Omni‑Directional obsługuje GTIN‑14, GTIN‑13 i inne identyfikatory numeryczne. Aby zakodować inną wartość, po prostu zamień ciąg znaków w konstruktorze:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Pamiętaj, aby dane były liczbowe i prawidłowo sformatowane; w przeciwnym razie generator zgłosi `BarcodeException`.

## Dostosuj wymiary kodu kreskowego do różnych scenariuszy drukowania

Różne drukarki i rozmiary etykiet wymagają innych wymiarów X oraz wysokości. Skorzystaj z poniższej tabeli jako szybkiego odniesienia:

| Scenariusz                     | X‑Dimension (piksele) | Bar Height (piksele) |
|--------------------------------|-----------------------|----------------------|
| Mała etykieta (25 mm × 15 mm)  | 1                     | 20                   |
| Średnia etykieta (50 mm × 30 mm) | 2                     | 30                   |
| Duża etykieta (100 mm × 50 mm) | 3                     | 45                   |

Zastosuj te wartości, ustawiając `generator.Parameters.Barcode.XDimension.Pixels` oraz `BarHeight.Pixels` odpowiednio.

## Porada: zweryfikuj wygenerowany kod kreskowy

Przed wysłaniem etykiety możesz programowo zweryfikować jej czytelność:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Ten fragment kodu demonstruje szybki test poprawności **adjust barcode dimensions**, zapewniając, że kod kreskowy spełnia wymagania skanowania.

## Typowe pułapki i jak ich unikać

| Pułapka                              | Dlaczego się to dzieje                              | Rozwiązanie                                                                 |
|--------------------------------------|------------------------------------------------------|-----------------------------------------------------------------------------|
| Używanie danych nienumerycznych dla DataBar | DataBar oczekuje numerycznych formatów GTIN          | Upewnij się, że ciąg znaków pasuje do wzorca `(01)XXXXXXXXXXXXX`.           |
| Ustawianie X‑dimension na 0 lub wartość ujemną | Biblioteka zgłasza `ArgumentOutOfRangeException`     | Użyj minimum 1 piksela; najpierw przetestuj na docelowej drukarce.          |
| Zapisywanie do folderu tylko do odczytu | `UnauthorizedAccessException` przy `Save`           | Wybierz katalog z prawami zapisu lub uruchom aplikację z odpowiednimi uprawnieniami. |
| Zapomnienie o zwolnieniu `BarCodeReader` | Wycieki pamięci w długotrwale działających usługach | Umieść czytnik w bloku `using` lub wywołaj `Dispose()` ręcznie.             |

## Pełny kod źródłowy podsumowanie

Poniżej znajduje się kompletny, gotowy do skopiowania program, który implementuje **przykład generatora kodów kreskowych** od początku do końca.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Uruchomienie tego programu generuje plik PNG, który wygląda tak (ilustracyjnie):

![Wygenerowany w C# kod kreskowy DataBar Omni‑Directional](https://example.com/og-image.png "Wygenerowany w C# kod kreskowy DataBar Omni‑Directional")

*Tekst alternatywny obrazu*: **Wygenerowany w C# kod kreskowy DataBar Omni‑Directional** (zgodny z `og_image_alt`).

## Zakończenie

Teraz masz **przykład generatora kodów kreskowych**, który demonstruje, jak zmienić wysokość, jak tworzyć symbole DataBar Omni‑Directional oraz jak **dostosować wymiary kodu kreskowego** dla optymalnego skanowania. Pełny kod w C# zapisuje obraz PNG, weryfikuje go i może być rozszerzony o generowanie hurtowe lub integrację z usługami webowymi.

Następnie, zapoznaj się z powiązanymi tematami, takimi jak **tworzenie kodów QR przy użyciu Aspose.BarCode**, **przetwarzanie wsadowe wielu wartości kodów kreskowych** lub **osadzanie kodów kreskowych w dokumentach PDF**. Każdy z nich opiera się na tych samych podstawach omówionych w tym przewodniku.

Miłego kodowania i niech Twoje kody kreskowe zawsze będą skanowalne!

## Co powinieneś się nauczyć dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Przykład generatora kodów kreskowych – Tworzenie obrazu DataBar w C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Jak generować i dostosowywać wysokość kodu kreskowego dla jednowymiarowego DataBar przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Przykład generatora kodów kreskowych w C# – ustaw szerokość i wysokość](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}