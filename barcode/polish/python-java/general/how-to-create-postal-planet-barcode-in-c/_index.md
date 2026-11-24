---
category: general
date: 2026-11-23
description: Utwórz kod kreskowy Planet (pocztowy) w C# przy użyciu Aspose.BarCode.
  Dowiedz się, jak generować kod Planet, ustawiać wymiar X oraz zapisywać wypełnione
  lub puste paski.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: pl
lastmod: 2026-11-23
og_description: Utwórz kod kreskowy Planet w C# i dowiedz się, jak generować kod kreskowy
  Planet przy użyciu Aspose.BarCode. Postępuj zgodnie z pełnym przykładem, aby uzyskać
  wypełnione i puste paski.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Jak stworzyć kod kreskowy Postal Planet w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak utworzyć kod kreskowy Postal Planet w C#
url: /pl/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy Planet dla poczty w C#

Jeśli potrzebujesz **utworzyć kod kreskowy Planet dla poczty** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie **jak wygenerować kod kreskowy Planet** przy użyciu biblioteki Aspose.BarCode. Zobaczysz, jak skonfigurować wymiar X, przełączać się między wypełnionymi a pustymi paskami oraz zapisywać obrazy w formacie PNG.

Generowanie kodu kreskowego Planet jest powszechne w usługach pocztowych, które wymagają wysokiej gęstości, maszynowo odczytywalnych symboli. Po zakończeniu tego samouczka będziesz mieć dwa pliki PNG — jeden z pełnymi paskami i jeden z pustymi paskami — gotowe do integracji w dowolnym procesie wysyłkowym.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany.
* Visual Studio 2022 (lub dowolny edytor C#) skonfigurowany do programowania w .NET.
* Aktywną licencję NuGet na **Aspose.BarCode for .NET**. Zainstaluj pakiet za pomocą:

```bash
dotnet add package Aspose.BarCode
```

Nie są wymagane dodatkowe usługi zewnętrzne; biblioteka wykonuje całe kodowanie lokalnie.

## Krok 1 – utwórz kod kreskowy Planet dla poczty

Pierwszą operacją jest utworzenie instancji `BarcodeGenerator` dla symbolu **Planet** i podanie danych do zakodowania. Ciąg danych musi być numeryczny i mieć maksymalnie 12 cyfr zgodnie ze specyfikacją pocztową.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Utworzenie generatora alokuje wszystkie wewnętrzne struktury potrzebne do renderowania. Wartość wyliczenia `EncodeTypes.Planet` wybiera właściwy algorytm kodowania dla formatu pocztowego.

## Krok 2 – ustaw wymiar X dla lepszej widoczności

Wymiar X definiuje szerokość pojedynczego modułu (najmniejszego elementu paska). Wartość 4 piksele zapewnia czytelną reprezentację wizualną bez powiększania całego obrazu.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Dostosowanie wymiaru X jest niezbędne, gdy kod kreskowy będzie drukowany na nośnikach o niskiej rozdzielczości. To samo ustawienie zostanie ponownie użyte dla wersji z pustymi paskami, aby oba obrazy były spójne.

## Krok 3 – zapisz kod kreskowy z wypełnionymi paskami

Domyślnie generator renderuje **wypełnione paski** (solidne czarne moduły). Zapis obrazu odbywa się jednym wywołaniem metody, które zapisuje plik PNG na dysku.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Zastąp `YOUR_DIRECTORY` rzeczywistą ścieżką, w której chcesz zapisać pliki wyjściowe. Wyliczenie `BarCodeImageFormat.Png` zapewnia bezstratną kompresję, co jest idealne dla dalszego przetwarzania.

## Krok 4 – utwórz kolejny generator kodu kreskowego Planet dla pustych pasków

Aby uzyskać wersję używającą **pustych pasków** (białe moduły na czarnym tle), potrzebujesz drugiej instancji `BarcodeGenerator`. Ponowne użycie tego samego ciągu danych zapewnia, że oba obrazy reprezentują identyczny kod pocztowy.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Utworzenie osobnego generatora izoluje właściwość `FilledBars`, umożliwiając przełączanie stylu wizualnego bez wpływu na pierwszy obraz.

## Krok 5 – skonfiguruj generator do renderowania pustych pasków

Flaga `FilledBars` odwraca tryb renderowania. Ustawienie jej na `false` instruuje bibliotekę, aby rysowała paski jako puste (przezroczyste), zachowując jednocześnie jednolite tło.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Utrzymanie wymiaru X identycznego jak w wersji wypełnionej zapewnia, że oba pliki PNG mają te same wymiary, co upraszcza obliczenia układu w szablonach drukowania.

## Krok 6 – zapisz kod kreskowy renderujący puste paski

Na koniec zapisz obraz z pustymi paskami na dysku. Używany jest ten sam format PNG, ale możesz przełączyć się na JPEG lub BMP, zmieniając wartość `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Na tym etapie masz dwa pliki:

* `PostalPlanetFilledBars.png` – solidne czarne paski.
* `PostalPlanetEmptyBars.png` – puste paski na czarnym tle.

Oba spełniają specyfikację pocztową dla symbolu Planet.

## Pełny kod źródłowy

Połączenie wszystkich kroków daje kompaktową aplikację konsolową, którą możesz uruchomić bezpośrednio.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Skompiluj i uruchom program:

```bash
dotnet run
```

Konsola wyświetla *Barcodes generated successfully.* a dwa pliki PNG pojawiają się w folderze projektu.

## Oczekiwany wynik

Poniżej znajduje się wizualna reprezentacja obrazu z wypełnionymi paskami. Odpowiednik z pustymi paskami wygląda identycznie, z wyjątkiem tego, że paski są przezroczyste.

![Przykład utworzonego kodu kreskowego Planet dla poczty z wypełnionymi paskami](postal-planet-filled.png)

*Tekst alternatywny obrazu:* **Przykład utworzonego kodu kreskowego Planet dla poczty z wypełnionymi paskami** (zawiera główne słowo kluczowe).

Oba obrazy mają domyślnie 150 × 150 pikseli, ale możesz kontrolować ogólny rozmiar przy użyciu parametrów `ImageWidth` i `ImageHeight`, jeśli wymagana jest inna rozdzielczość.

## Opcjonalne warianty

### Zmiana formatu obrazu

Jeśli Twój system docelowy preferuje JPEG, zastąp `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. JPEG wprowadza artefakty kompresji, więc używaj go tylko wtedy, gdy rozmiar pliku jest krytycznym ograniczeniem.

### Skalowanie kodu kreskowego

Możesz powiększyć kod kreskowy, zachowując szerokość modułu, poprzez dostosowanie właściwości `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Wyższe wartości DPI poprawiają jakość druku na drukarkach laserowych.

### Użycie niestandardowego koloru tła

Tło można ustawić przy pomocy:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Jest to przydatne do testów wizualnych, ale powinno być unikane w produkcyjnych etykietach pocztowych, które wymagają białego tła.

## Najczęściej zadawane pytania

**Czy to działa z .NET Core?**  
Tak. Biblioteka Aspose.BarCode jest przeznaczona dla .NET Standard 2.0, co jest kompatybilne z .NET 5, .NET 6 oraz .NET Core 3.1.

**Co jeśli ciąg danych zawiera znaki nienumeryczne?**  
Kody kreskowe Planet akceptują wyłącznie dane numeryczne. Dostarczenie liter lub symboli powoduje wyrzucenie `BarcodeException`. Zweryfikuj dane przed utworzeniem generatora.

**Czy mogę wygenerować kod kreskowy w pamięci, bez zapisywania na dysk?**  
Użyj metody `GenerateBarCodeImage`, aby uzyskać obiekt `System.Drawing.Image`, a następnie przesyłaj go bezpośrednio w odpowiedzi lub do bazy danych.

## Podsumowanie

Teraz wiesz, jak **utworzyć kod kreskowy Planet dla poczty** w C# i rozumiesz **jak generować kod kreskowy Planet** zarówno w stylu wypełnionych, jak i pustych pasków. Samouczek obejmował pełny przepływ pracy — od inicjalizacji generatora, konfiguracji wymiaru X, przełączania flagi `FilledBars`, po zapisywanie plików PNG. Eksperymentuj z formatami obrazu, ustawieniami DPI i kolorami tła, aby dostosować kod kreskowy do swojego systemu wysyłkowego.

W kolejnym kroku, zapoznaj się z innymi symbologiami pocztowymi, takimi jak **POSTNET** lub **Intelligent Mail**, używając tego samego API Aspose.BarCode. Dostosowywanie parametrów, takich jak `EncodeTypes.Postnet`, podąża za tym samym schematem przedstawionym tutaj, co pozwala zbudować kompleksowy zestaw generowania kodów kreskowych w jednej bazie kodu.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz pusty kod kreskowy Planet, wygeneruj kod pocztowy w C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Jak ustawić szerokość i wygenerować kod kreskowy Planet w C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generowanie kodu pocztowego w C# – Kompletny przewodnik z kodem Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}