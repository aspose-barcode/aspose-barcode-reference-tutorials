---
category: general
date: 2026-08-22
description: Samouczek generatora kodów kreskowych w C# pokazuje, jak utworzyć kod
  Macro PDF417 z metadanymi i zapisać go jako PNG przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: pl
lastmod: 2026-08-22
og_description: generator kodów kreskowych C# umożliwia tworzenie kodu Macro PDF417
  z pełnymi metadanymi na poziomie pliku i eksportowanie go jako PNG. Postępuj zgodnie
  z tym przewodnikiem, aby wdrożyć rozwiązanie.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: generator kodów kreskowych C# – twórz kody Macro PDF417 krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak używać generatora kodów kreskowych C# dla Macro PDF417
url: /pl/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać generatora kodów kreskowych C# dla Macro PDF417

Jeśli potrzebujesz **generatora kodów kreskowych C#**, który może generować symbol Macro PDF417 z metadanymi na poziomie pliku, ten przewodnik zapewnia kompletną, gotową do uruchomienia rozwiązanie. Zobaczysz, jak skonfigurować wygląd kodu kreskowego, osadzić informacje makro, takie jak identyfikator pliku i liczba segmentów, oraz ostatecznie zapisać wynik jako obraz PNG.

Przykład wykorzystuje bibliotekę Aspose.BarCode, powszechnie stosowaną **bibliotekę kodów kreskowych C#**, która obsługuje pełny zestaw funkcji PDF417. Nie są wymagane żadne zewnętrzne usługi, a kod działa z .NET 6 lub nowszym.

## Prerequisites

* .NET 6 SDK (lub nowsza wersja) zainstalowany.
* Visual Studio 2022, VS Code lub inne środowisko IDE C#.
* Odwołanie NuGet do **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Zrozumienie podstawowej składni C# oraz koncepcji kodów kreskowych PDF417 pomoże Ci śledzić kolejne kroki, ale sam poradnik wyjaśnia każdą opcję konfiguracji szczegółowo.

## What the tutorial covers

* Inicjalizacja instancji **generatora kodów kreskowych C#** dla formatu Macro PDF417.  
* Dostosowanie parametrów wizualnych, takich jak wymiar X i liczba kolumn.  
* Podanie pól na poziomie pliku Macro PDF417: identyfikator pliku, identyfikator segmentu, liczba segmentów, nazwa pliku, suma kontrolna, rozmiar pliku, znacznik czasu, adresat, nadawca oraz znacznik zakończenia.  
* Zapis wygenerowanego symbolu jako plik PNG.  
* Wskazówki dotyczące obsługi przypadków brzegowych, takich jak duże rozmiary plików lub własne znaczniki czasu.

Po zakończeniu tego artykułu będziesz mieć samodzielny program, który generuje w pełni zgodny kod Macro PDF417.

## Step 1: Create the barcode generator C# instance

Pierwszą operacją jest utworzenie instancji `BarcodeGenerator` z wartością wyliczenia `EncodeTypes.MacroPdf417` oraz tekstem, który chcesz zakodować. Konstruktor przyjmuje także ciąg ładunku, który staje się częścią danych makro kodu kreskowego.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Dlaczego to ważne** – Flaga `EncodeTypes.MacroPdf417` informuje Aspose.BarCode, aby traktował symbol jako kod makro, umożliwiając dodatkowe pola, które pojawią się później. Bez tej flagi biblioteka wygenerowałaby zwykły kod PDF417 bez metadanych na poziomie pliku.

## Step 2: Adjust basic barcode appearance (PDF417 visual settings)

Czytelność wizualna jest kluczowa dla niezawodnego skanowania. Dwa powszechne parametry to szerokość modułu (`XDimension`) oraz liczba kolumn. Ustawienie tych wartości równoważy rozmiar i czytelność.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` kontroluje szerokość każdego czarnego/białego paska. Wartość **2** sprawdza się w większości drukarek etykiet.
* `Pdf417.Columns` określa, ile kolumn użyje kod kreskowy. Pięć kolumn tworzy kompaktowy symbol bez utraty pojemności danych.

## Step 3: Define Macro PDF417 file‑level information

Macro PDF417 rozszerza standardowy format PDF417 o pola opisujące, jak duży plik jest podzielony na wiele segmentów kodu kreskowego. Dostarczenie tych pól zapewnia, że skanery po stronie odbiorcy mogą odtworzyć oryginalny plik.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` musi być taki sam dla każdego segmentu należącego do tego samego logicznego pliku.
* `MacroPdf417SegmentID` zwiększa się od **0** do `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` informuje dekoder, ile części ma się spodziewać.
* `MacroPdf417FileName` jest opcjonalny, ale przydatny do identyfikacji czytelnej dla człowieka.

## Step 4: Set additional macro metadata

Poza podstawowymi informacjami o pliku, specyfikacja dopuszcza dodatkowe pola, takie jak suma kontrolna, rozmiar pliku, znacznik czasu, adresat, nadawca oraz flaga zakończenia. Wypełnienie tych pól zwiększa integralność danych i ich śledzenie.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` dostarcza 16‑bitową sumę kontrolną CCITT dla całego pliku; dekoder może zweryfikować integralność po odtworzeniu.
* `MacroPdf417FileSize` powinien odzwierciedlać dokładną liczbę bajtów oryginalnego pliku; wartości większe niż `2^31‑1` wymagają pola 64‑bitowego, które Aspose obsługuje automatycznie.
* `MacroPdf417TimeStamp` rejestruje moment generowania kodu kreskowego. Używaj UTC, aby uniknąć niejasności stref czasowych.
* `MacroPdf417Addressee` i `MacroPdf417Sender` to dowolne ciągi znaków, które mogą przechowywać informacje o trasie.
* `MacroPdf417Terminator` sygnalizuje, że jest to ostatni segment; ustaw go na `Set` dla ostatniego fragmentu, w przeciwnym razie pozostaw domyślne (`NotSet`).

**Wskazówka w przypadku brzegowym** – Jeśli rozmiar pliku przekracza 4 GB, podziel zawartość na wiele segmentów makro i odpowiednio dostosuj `SegmentsCount`. Biblioteka poradzi sobie z polem dużego rozmiaru bez przepełnienia.

## Step 5: Save the barcode as a PNG image

Ostatni krok zapisuje wygenerowany symbol na dysku. PNG zachowuje dokładne wymiary pikseli i jest szeroko wspierany przez sprzęt skanujący.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Zastąp `YOUR_DIRECTORY` ścieżką absolutną lub względną, do której proces wykonujący może zapisywać. Enum `BarCodeImageFormat.Png` zapewnia wyjście bezstratne.

**Dlaczego PNG?** – Format rastrowy, taki jak PNG, utrzymuje ostre krawędzie modułów, co jest niezbędne dla skanerów opierających się na wysokim kontraście krawędzi. Jeśli potrzebujesz formatu wektorowego, Aspose obsługuje także `Pdf` i `Svg`.

## Full runnable example

Poniżej znajduje się kompletny program, który możesz skopiować do aplikacji konsolowej. Zawiera niezbędne dyrektywy `using` oraz metodę `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Expected output

Uruchomienie programu tworzy plik o nazwie **MacroPdf417.png** w katalogu roboczym projektu. Otworzenie obrazu pokazuje kompaktowy kod PDF417 z osadzonymi polami makro. Skanowanie obrazu przy użyciu czytnika kompatybilnego z PDF417 (np. ZXing, dekoder Aspose.BarCode) zwraca oryginalny ładunek `"Sample text"` wraz z metadanymi makro.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| *Co zrobić, jeśli kod kreskowy jest zbyt duży dla docelowej etykiety?* | Zmniejsz `XDimension.Pixels` lub zwiększ `Pdf417.Columns`. Oba parametry wpływają na ogólny rozmiar. |
| *Czy mogę wygenerować obraz wektorowy zamiast PNG?* | Tak. Wywołaj `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` aby uzyskać skalowalny wynik. |
| *Jak zweryfikować sumę kontrolną po skanowaniu?* | Dekoder Aspose.BarCode automatycznie weryfikuje `MacroPdf417Checksum` i zgłasza niezgodności w obiekcie `MacroPdf417Result`. |
| *Czy biblioteka jest kompatybilna z .NET Core?* | Pakiet NuGet obsługuje .NET Standard 2.0+, co obejmuje .NET Core, .NET 5, .NET 6 i nowsze. |
| *Co zrobić, jeśli muszę osadzić dane binarne zamiast tekstu?* | Konwertuj binarny ładunek na Base64 lub użyj przeciążenia `EncodeTypes.MacroPdf417`, które przyjmuje tablicę bajtów. |

## Pro tips for production use

* **Cache'uj generator** – 

## What Should You Learn Next?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z instrukcjami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak odczytać kod kreskowy z PDF w Javie przy użyciu Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Utwórz kod kreskowy Codabar z Aspose.Barcode – API generatora i czytnika](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}