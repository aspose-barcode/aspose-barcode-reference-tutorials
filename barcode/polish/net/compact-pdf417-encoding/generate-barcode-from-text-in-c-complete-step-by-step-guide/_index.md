---
category: general
date: 2026-10-09
description: Dowiedz się, jak generować kod kreskowy c# przy użyciu Aspose.BarCode,
  obsługiwać znaki specjalne i szybko tworzyć obrazy kodów kreskowych PDF417 w .NET.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- barcode generator .net
- create barcode image c#
- barcode with special characters
- pdf417 barcode c#
lastmod: 2026-10-09
og_description: Generuj kod kreskowy c# przy użyciu Aspose.BarCode w aplikacji konsolowej
  .NET. Ten przewodnik krok po kroku pokazuje, jak obsługiwać Unicode, wybierać typy
  kodowania i tworzyć obrazy kodów kreskowych PDF417.
og_image_alt: Developer view of a MicroPdf417 barcode PNG generated with Aspose.BarCode
og_title: Generowanie kodu kreskowego c# – szybki przewodnik krok po kroku dla .NET
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Generate barcode c# with Aspose.BarCode. Learn how to generate barcode,
    support special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode c# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Generowanie kodu kreskowego c# – kompletny przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego c# – kompletny przewodnik krok po kroku

Jeśli potrzebujesz **generate barcode c#** w aplikacji .NET, ten przewodnik przeprowadzi Cię przez cały proces. Zobaczysz, jak generować kod kreskowy, obsługiwać znaki specjalne i stworzyć implementację kodu kreskowego PDF417 w C#, która działa od razu.

Generowanie kodu kreskowego z tekstu jest powszechnym wymogiem w systemach inwentaryzacji, platformach biletowych i przepływach dokumentów. Po zakończeniu tego samouczka będziesz mieć działającą aplikację konsolową C#, która tworzy obraz PNG MicroPdf417 przy użyciu Aspose.BarCode. Nie są wymagane żadne zewnętrzne usługi, a kod obsługuje znaki Unicode, takie jak „Å”, „©” i „é”.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem użyć?** Aspose.BarCode for .NET zapewnia najbardziej kompletny zestaw typów kodowania i natywną obsługę Unicode.  
- **Czy mogę uruchomić to na .NET 6?** Tak, kod jest skierowany na .NET 6 i działa również z .NET Core 3.1 oraz .NET Framework 4.7+.  
- **Jak obsłużyć znaki specjalne?** Ustaw `TextEncoding = Encoding.UTF8` w generatorze, aby zapewnić prawidłowe renderowanie.  
- **Jaki format obrazu jest tworzony?** Przykład zapisuje plik PNG, ale możesz przełączyć na JPEG, BMP lub TIFF za pomocą jednej zmiany właściwości.  
- **Czy wymagana jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana przy wdrożeniach produkcyjnych.

## Co to jest generate barcode c#?
`generate barcode c#` odnosi się do programowego tworzenia wizualnego obrazu kodu kreskowego przy użyciu kodu C#. Aspose.BarCode for .NET zamienia dowolny ciąg znaków — ASCII lub Unicode — w obraz rastrowy, który może być drukowany, wyświetlany na ekranie lub osadzony w pliku PDF.

## Dlaczego używać Aspose.BarCode dla .NET?
Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i może renderować obrazy do **5000 × 5000 px** bez utraty jakości. Biblioteka przetwarza 1 KB danych w mniej niż **30 ms** na typowym laptopie deweloperskim, co oznacza, że generowanie w czasie rzeczywistym jest wykonalne w scenariuszach o wysokim przepustowości, takich jak kioski biletowe czy masowa produkcja etykiet.

## Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Core 3.1 i .NET Framework 4.7+)
- Visual Studio 2022 (lub dowolne IDE obsługujące C#)
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Podstawowa znajomość składni C#

## Jak skonfigurować generator kodów kreskowych?
Klasa `BarcodeGenerator` jest podstawowym komponentem tworzącym obrazy kodów kreskowych na podstawie podanych ustawień.  
Utwórz instancję `BarcodeGenerator`, określ, którego **typu kodowania** potrzebujesz, i przekaż surowy tekst do zakodowania. Ten pojedynczy wiersz tworzy w pełni skonfigurowany generator gotowy do renderowania kodu MicroPdf417.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Wartość wyliczeniowa `EncodeTypes.MicroPdf417` wybiera kompaktowy wariant PDF417, idealny dla krótkich ciągów danych przy minimalnym rozmiarze symbolu.

## Jak generować kod kreskowy ze znakami specjalnymi?
Gdy Twoje dane zawierają symbole spoza ASCII, musisz zapewnić, że generator używa kodowania UTF‑8. Aspose.BarCode automatycznie wykrywa Unicode, ale możesz jawnie ustawić kodowanie tekstu, jeśli napotkasz problemy. Ustawienie kodowania gwarantuje, że znaki takie jak „Å”, „©” i „é” zostaną poprawnie wyrenderowane w obrazie kodu kreskowego, zapobiegając problemowi zamazanych lub brakujących glifów.

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Dodanie tej linii przed innymi ustawieniami zapewnia, że **kod kreskowy ze znakami specjalnymi** renderuje się prawidłowo na każdej platformie.

### Praktyczna wskazówka
Jeśli wynik wygląda na zamazany, sprawdź, czy czcionka używana przez renderer kodów kreskowych obsługuje wymagane glify. Możesz osadzić własną czcionkę TrueType poprzez:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Jakie typy kodowania kodów kreskowych mogę wybrać?
Aspose.BarCode obsługuje dziesiątki **typów kodowania kodów kreskowych**, z których każdy jest przeznaczony do innych zastosowań. Biblioteka dostarcza obszerną listę symbologii, od kodów liniowych używanych w logistyce po dwuwymiarowe kody macierzowe dla aplikacji mobilnych. Wybór odpowiedniego typu kodowania zapewnia optymalną czytelność i gęstość danych dla Twojego scenariusza.

| Typ kodowania                | Typowe zastosowanie                     |
|------------------------------|------------------------------------------|
| `EncodeTypes.Code128`        | Etykiety wysyłkowe, inwentarz           |
| `EncodeTypes.QR`             | Płatności mobilne, URL                   |
| `EncodeTypes.Pdf417`         | Prawo jazdy, karty pokładowe             |
| `EncodeTypes.MicroPdf417`    | Małe ładunki danych, ograniczona przestrzeń |
| `EncodeTypes.DataMatrix`     | Małe przedmioty, wysoka gęstość danych   |

Zmiana typu kodowania jest tak prosta, jak zamiana wartości wyliczeniowej w konstruktorze:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Ta elastyczność pozwala odpowiadać na pytania o **typy kodowania kodów kreskowych** bez opuszczania IDE.

## Jak stworzyć kod kreskowy PDF417 w C# – końcowe kroki i weryfikacja
Po skonfigurowaniu generatora, ostatnim elementem **create pdf417 barcode c#** jest zapis obrazu i potwierdzenie wyniku. Należy wywołać metodę `Save` z podaniem ścieżki pliku i opcjonalnie określić format obrazu. Po zapisaniu pliku otwórz go w przeglądarce obrazów lub zeskanuj czytnikiem kodów kreskowych, aby zweryfikować, że zakodowany tekst odpowiada pierwotnemu wejściu.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Uruchom program (`dotnet run`) i powinieneś zobaczyć komunikat w konsoli podobny do:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Otwórz plik PNG; zobaczysz wyraźny kod MicroPdf417, który koduje ciąg „Åspóse.Barcóde©”. Zeskanowanie go mobilnym skanerem kodów (np. ZXing) zwróci oryginalny tekst, potwierdzając, że **generate barcode c#** działa nawet ze znakami specjalnymi.

## Co się dzieje przy bardzo długim tekście?
MicroPdf417 ma maksymalną pojemność danych **1 KB**. Gdy ładunek przekracza obsługiwany rozmiar, generator nie może utworzyć prawidłowego symbolu i zgłasza wyjątek. Powinieneś obsłużyć ten warunek, przycinając dane, dzieląc je na wiele kodów kreskowych lub przełączając się na symbologię o większej pojemności, taką jak pełny PDF417 lub DataMatrix. Aby zrobić to elegancko:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

Dla większych ładunków przełącz się na pełny `EncodeTypes.Pdf417` lub `EncodeTypes.DataMatrix`, które obsługują do **1,5 KB** i **3 KB** odpowiednio.

## Typowe pułapki i jak ich unikać

| Problem                               | Przyczyna                                 | Rozwiązanie |
|---------------------------------------|-------------------------------------------|-------------|
| Kod kreskowy jest rozmyty             | XDimension zbyt niska (np. 1 px)          | Zwiększ `XDimension.Pixels` do 2‑3 px |
| Znaki Unicode stają się `?`           | Domyślne kodowanie tekstu to ASCII        | Ustaw `TextEncoding = Encoding.UTF8` |
| Plik obrazu nie został utworzony      | Katalog wyjściowy nie istnieje            | Użyj `Directory.CreateDirectory` przed `Save` |
| Skaner nie może odczytać kodu kreskowego | Zbyt wiele kolumn dla krótkich danych      | Zredukuj `Pdf417.Columns` (np. 3‑4) |

## Pełny kod źródłowy (gotowy do skopiowania)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Oczekiwany wynik:** plik o nazwie `MicroPdf417.png` znajdujący się w folderze `output`, zawierający wyraźny kod MicroPdf417, który koduje oryginalny ciąg ze znakami specjalnymi.

## Zakończenie

Teraz wiesz, jak **generate barcode c#** przy użyciu Aspose.BarCode, jak obsługiwać **kod kreskowy ze znakami specjalnymi**, oraz jak **create pdf417 barcode c#** z pełną kontrolą nad opcjami kodowania. Dostosowując **typy kodowania kodów kreskowych**, możesz tworzyć kody QR, Code128, DataMatrix i inne obsługiwane formaty.

Następnie zgłębiaj poniższe tematy, aby poszerzyć swoją wiedzę o kodach kreskowych:

- **Jak generować kody kreskowe** w partiach dla tysięcy rekordów (użyj `Parallel.ForEach` dla szybkości)
- Dostosowywanie kolorów i dodawanie logo wewnątrz kodu kreskowego
- Integracja generowania kodów kreskowych z API ASP.NET Core w celu dostarczania obrazów w locie
- Używanie innych bibliotek, takich jak ZXing.Net lub IronBarcode, jako alternatyw open‑source

Eksperymentuj z różnymi wymiarami, ustawieniami kolumn i typami kodowania. Szczęśliwego kodowania i niech Twoje aplikacje skanują bezbłędnie!

## Co powinieneś się nauczyć dalej?
Poniższe samouczki obejmują tematy blisko powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak stworzyć kod kreskowy – Compact PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generować kod kreskowy – konfiguracja Code 39 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generować kod kreskowy – typy jednowymiarowych kodów kreskowych](/barcode/english/net/one-dimensional-barcode-types/)

## Najczęściej zadawane pytania

**P: Czy mogę używać tego kodu w aplikacji komercyjnej?**  
O: Tak, możesz używać Aspose.BarCode w projektach komercyjnych, pod warunkiem posiadania ważnej licencji; dostępna jest darmowa wersja próbna do oceny.

**P: Czy Aspose.BarCode obsługuje .NET 6?**  
O: Absolutnie. Biblioteka jest skompilowana dla .NET Standard 2.0, co czyni ją kompatybilną z .NET 6, .NET 5, .NET Core 3.1 i .NET Framework 4.7+.

**P: Jak zmienić format wyjściowy z PNG na JPEG?**  
O: Ustaw właściwość `SaveFormat` na `SaveFormat.Jpeg` przed wywołaniem `Save`. Reszta kodu pozostaje niezmieniona.

**P: Jaki jest maksymalny rozmiar kodu MicroPdf417?**  
O: MicroPdf417 może zakodować do **1 KB** danych; próba przekroczenia tego limitu powoduje wyrzucenie `ArgumentException`.

**P: Czy można osadzić logo wewnątrz kodu kreskowego?**  
O: Tak. Użyj właściwości `BarcodeGenerator.Image`, aby wczytać obraz logo i przypisać go do `BarcodeGenerator.Image` przed zapisem.

**Last Updated:** 2026-10-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Powiązane samouczki

- [Stwórz kod PDF417 z Aspose Barcode – przewodnik krok po kroku](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/net/datamatrix-barcode-configuration/)
- [Generuj kod PNG z Aspose.BarCode dla .NET: jednowymiarowe wypełnione paski](/barcode/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}