---
category: general
date: 2026-09-26
description: Dowiedz się, jak szybko tworzyć kod kreskowy Planet w C#. Ten przewodnik
  obejmuje wypełnione i puste kody kreskowe Planet, ustawienia wymiaru X oraz eksport
  obrazu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: pl
lastmod: 2026-09-26
og_description: Utwórz kod kreskowy Planet w C# z pełnym przykładem kodu. Generuj
  zarówno wypełnione, jak i puste kody kreskowe Planet, ustaw szerokość kreski i zapisz
  jako PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Tworzenie obrazów kodów kreskowych planet w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak tworzyć obrazy kodów kreskowych planet w C# z użyciem BarcodeGenerator
url: /pl/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć obrazy planet barcode w C# przy użyciu BarcodeGenerator

Jeśli potrzebujesz **create planet barcode** obrazy w aplikacji .NET, ten tutorial pokaże Ci dokładne kroki. Nauczysz się generować zarówno wypełniony, jak i pusty Planet barcode, regulować szerokość pasków oraz eksportować wyniki jako pliki PNG — wszystko przy użyciu biblioteki Aspose.BarCode for .NET.

Generowanie rozwiązania **Planet barcode C#** jest proste, gdy zrozumiesz kluczowe **barcode generator parameters**. W kolejnych sekcjach przeprowadzimy Cię przez kompletny, działający kod, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, oraz wskażemy typowe pułapki, abyś mógł ich uniknąć od pierwszego podejścia.

## Wymagania wstępne

* Zainstalowany .NET 6.0 SDK lub nowszy.
* Visual Studio 2022 (lub dowolne IDE C#, które preferujesz).
* Pakiet NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) dodany do projektu.

Pakiet możesz dodać za pomocą konsoli NuGet Package Manager Console:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Konfiguracja BarcodeGenerator

Klasa `BarcodeGenerator` jest punktem wejścia dla wszystkich zadań tworzenia kodów kreskowych. Wymaga dwóch argumentów: typu kodu kreskowego (`EncodeTypes.Planet`) oraz danych do zakodowania.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Dlaczego to ważne:* Utworzenie generatora z `EncodeTypes.Planet` informuje bibliotekę, aby używała symboliki **Planet barcode**, która jest powszechnie stosowana w usługach pocztowych w niektórych krajach. Ciąg znaków `"123456"` jest ładunkiem, który pojawi się w kodzie kreskowym.

## Krok 2: Konfiguracja wymiaru X (szerokość paska)

Wymiar X kontroluje fizyczną szerokość każdego paska. Typowa wartość dla renderowania na ekranie to 4 piksele, ale możesz ją dostosować do wymagań drukowania.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Dlaczego to ważne:* Ustawienie `XDimension.Pixels` zapewnia, że wygenerowany kod kreskowy nie będzie ani zbyt cienki (co powoduje niepowodzenia skanowania), ani zbyt gruby (co marnuje miejsce). To samo ustawienie zostanie ponownie użyte dla pustego kodu.

## Krok 3: Zapis wypełnionego kodu Planet

Wyeksportuj kod kreskowy do pliku PNG przy użyciu metody `Save`. Enum `BarCodeImageFormat.Png` informuje bibliotekę, aby wygenerowała obraz bezstratny, odpowiedni do dalszego przetwarzania.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Po uruchomieniu programu znajdziesz plik `PostalPlanetFilledBars.png` w folderze wyjściowym. Otwórz go, aby zweryfikować, że paski są solidne (wypełnione).

## Krok 4: Utworzenie generatora dla pustego kodu Planet

**Pusty planet barcode** wyświetla te same dane, ale z niewypełnionymi (białymi) paskami. Jest to przydatne w projektach wizualnych, które nakładają kod kreskowy na kolorowe tło.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Wywołanie konstruktora jest identyczne jak w wersji wypełnionej; różnica leży w parametrze, który zmienimy w następnym kroku.

## Krok 5: Ponowne użycie tego samego wymiaru X

Aby zachować spójny rozmiar wizualny, zastosuj tę samą szerokość paska w pustym kodzie.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Ponowne użycie **barcode generator parameters** zapewnia, że oba obrazy będą idealnie wyrównane, gdy zostaną umieszczone obok siebie.

## Krok 6: Przełączenie na niewypełnione paski

Flaga `FilledBars` określa, czy paski są renderowane jako solidna czerń (domyślnie) czy przezroczysta biel.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Dlaczego to ważne:* Ustawienie `FilledBars = false` odwraca tryb renderowania, co jest kluczową różnicą między wypełnionym a pustym kodem Planet.

## Krok 7: Zapis pustego kodu Planet

Na koniec wyeksportuj pustą wersję do PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Po uruchomieniu programu pojawią się dwa pliki:

* `PostalPlanetFilledBars.png` – solidne czarne paski.
* `PostalPlanetEmptyBars.png` – przezroczyste (niewypełnione) paski.

Oba obrazy zawierają te same dane (`123456`) i mają ten sam wymiar X, co sprawia, że są wymienne w większości scenariuszy UI.

## Pełny, działający przykład

Łącząc wszystko razem, oto kompletny plik źródłowy, który możesz skopiować i wkleić do nowego projektu konsolowego:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu tworzy dwa pliki PNG w katalogu roboczym wykonywalnego pliku. Otwórz je dowolnym przeglądarką obrazów:

* **Wersja wypełniona** – ciemne, solidne paski, które są łatwo odczytywalne przez standardowe skanery.
* **Wersja pusta** – paski pojawiają się jako białe przerwy na czarnym tle, przydatne do efektów nakładania.

## Typowe pułapki i wskazówki profesjonalne

| Problem | Dlaczego się dzieje | Jak to naprawić |
|-------|----------------|---------------|
| Paski wyglądają zbyt cienko | Wymiar X pozostawiony w domyślnej wartości (1 piksel) | Ustaw `XDimension.Pixels` na 3‑5 pikseli do użycia na ekranie; zwiększ dla wydruków wysokiej rozdzielczości. |
| Pusty kod kreskowy pojawia się całkowicie czarny | `FilledBars` nie ustawiono na `false` | Upewnij się, że `emptyPlanet.Parameters.Barcode.FilledBars = false;` jest wykonywane **po** ustawieniu wymiaru X. |
| Plik PNG jest brakujący | Ścieżka wyjściowa jest niepoprawna lub katalog nie istnieje | Podaj pełną ścieżkę (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) lub utwórz katalog wcześniej przy użyciu `Directory.CreateDirectory`. |
| Kod kreskowy nie jest odczytywany | Ciąg danych zawiera niedozwolone znaki dla symboliki Planet | Kody Planet akceptują wyłącznie ładunki numeryczne; zweryfikuj wejście przy użyciu `int.TryParse`. |

**Wskazówka profesjonalna:** Jeśli potrzebujesz osadzić kod kreskowy w PDF, możesz wczytać wygenerowany PNG do `PdfDocument` przy użyciu Aspose.PDF, lub bezpośrednio dodać kod jako strumień obrazu bez zapisywania na dysku.

## Kolejne kroki

Teraz, gdy możesz **create planet barcode** obrazy, rozważ zgłębienie następujących powiązanych tematów:

* **Planet barcode C#** – dostosowywanie kolorów, dodawanie tekstu czytelnego dla człowieka lub osadzanie kodu w PDF.
* **Barcode generator parameters** – dostrajanie poziomu korekcji błędów, strefy ciszy lub rotacji.
* **Batch generation** – iteracja po liście kodów pocztowych w celu wygenerowania pliku zip z PNG.
* **Alternative formats** – eksport do SVG lub JPEG dla dostarczenia przyjaznego dla sieci.

Eksperymentuj z różnymi wartościami `XDimension` i flagą `FilledBars`, aby zobaczyć, jak wpływają na niezawodność skanowania i styl wizualny. Gdy będziesz gotowy, zintegrować kod generujący z Twoim API webowym lub aplikacją desktopową, aby automatycznie tworzyć kody pocztowe w locie.

---

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz kod Planet w C# – Pełny przewodnik krok po kroku](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generator kodów kreskowych C# – przykład tworzenia kodu Planet i RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generuj kod pocztowy w C# – Kompletny przewodnik z kodem Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}