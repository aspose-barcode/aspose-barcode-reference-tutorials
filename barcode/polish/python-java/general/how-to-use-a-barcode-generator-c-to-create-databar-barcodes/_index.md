---
category: general
date: 2026-09-07
description: samouczek generatora kodów kreskowych w C#, który pokazuje, jak generować
  pliki PNG kodów kreskowych oraz tworzyć kody DataBar z konfigurowalnymi wierszami
  i kolumnami
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: pl
lastmod: 2026-09-07
og_description: 'generator kodów kreskowych C# – tutorial: dowiedz się, jak generować
  pliki PNG kodów kreskowych i tworzyć kody DataBar z własnymi wierszami i kolumnami
  w zaledwie kilka minut'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: generator kodów kreskowych C# – twórz kody DataBar i obrazy PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar
url: /pl/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać generatora kodów kreskowych C# do tworzenia kodów DataBar

Jeśli potrzebujesz **barcode generator C#** do tworzenia wysokiej jakości kodów kreskowych, ten przewodnik pokaże Ci, jak **generate barcode PNG** pliki i **create DataBar barcodes** z niestandardowymi wierszami i kolumnami. Niezależnie od tego, czy budujesz system zarządzania zapasami w handlu detalicznym, czy platformę biletową, poniższe kroki pozwolą Ci wygenerować kod DataBar Expanded Stacked w jednym, samodzielnym przykładzie.

W tym samouczku nauczysz się:

* Jak utworzyć instancję `BarcodeGenerator` dla symbologii DataBar Expanded Stacked.  
* Jak dostosować ustawienia kolumn i wierszy, aby spełniały specyfikacje ISO / GS1.  
* Jak zapisać wynik jako obraz PNG, który można osadzić w stronach internetowych lub wydrukować na etykietach.  

Nie wymagane są żadne zewnętrzne usługi — wystarczy biblioteka Aspose.BarCode for .NET (lub dowolna kompatybilna biblioteka, która korzysta z tego samego API). Kod działa na .NET 6+ i działa w Visual Studio, Rider lub dowolnym IDE obsługującym C#.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Zainstalowany .NET 6 SDK lub nowszy.  
* Odwołanie do pakietu NuGet `Aspose.BarCode` (lub równoważnej biblioteki, która udostępnia `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`).  
* Podstawowa znajomość składni C# oraz struktury projektu.  

Możesz dodać pakiet za pomocą wiersza poleceń:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Zainicjalizuj generator kodów kreskowych C# dla DataBar Expanded Stacked

Pierwszym krokiem jest stworzenie instancji `BarcodeGenerator`, która celuje w symbologię **DataBar Expanded Stacked**. Ten obiekt przechowuje wszystkie parametry renderowania, w tym tekst do zakodowania.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Dlaczego to ważne:** Wartość wyliczenia `EncodeTypes.DatabarExpandedStacked` informuje bibliotekę, którego standardu kodu kreskowego użyć. Użycie właściwego wyliczenia zapewnia, że wygenerowany obraz spełnia specyfikacje GS1 DataBar.

## Krok 2: Skonfiguruj liczbę kolumn (używane są domyślne wiersze)

DataBar Expanded Stacked może być podzielony na wiele kolumn. Dostosowanie liczby kolumn zmienia gęstość wizualną i może pomóc zmieścić dłuższe ciągi danych w ograniczonej przestrzeni.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Wskazówka:** Domyślna liczba kolumn to 1. Ustawienie jej na 4 tworzy cztery ułożone kolumny, co jest idealne dla dłuższych ciągów liczbowych, jednocześnie utrzymując wysokość kodu kreskowego w rozsądnych granicach.

## Krok 3: Wygeneruj PNG kodu kreskowego z zastosowanym ustawieniem kolumn

Teraz zapisz kod kreskowy jako obraz PNG. PNG zachowuje ostre krawędzie potrzebne skanerom i dobrze sprawdza się zarówno w mediach internetowych, jak i drukowanych.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Plik `DatabarCols4.png` zawiera **barcode PNG**, który możesz osadzić bezpośrednio w HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Krok 4: Utwórz osobną instancję generatora dla konfiguracji wierszy

Jeśli potrzebujesz kontrolować liczbę wierszy zamiast kolumn, utwórz nową instancję `BarcodeGenerator`. Ponowne użycie tej samej instancji po zmianie wymiaru może prowadzić do nieoczekiwanych artefaktów układu, więc świeży obiekt jest najbezpieczniejszym rozwiązaniem.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Krok 5: Ustaw liczbę wierszy (używane są domyślne kolumny)

Wiersze wpływają na pionowe układanie modułów kodu kreskowego. Zwiększenie liczby wierszy może sprawić, że kod będzie wyższy, co może być wymagane dla niektórych rozmiarów etykiet.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Dlaczego wiersze vs. kolumny:** Kolumny dzielą kod kreskowy w poziomie, podczas gdy wiersze rozciągają go w pionie. Wybierz orientację, która najlepiej pasuje do układu Twojej etykiety.

## Krok 6: Wygeneruj PNG kodu kreskowego z zastosowanym ustawieniem wierszy

Na koniec zapisz kod kreskowy dostosowany pod względem wierszy jako plik PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Masz teraz dwa odrębne pliki PNG:

* `DatabarCols4.png` – 4 kolumny, 1 wiersz.  
* `DatabarRows3.png` – 1 kolumna, 3 wiersze.

Oba obrazy są gotowe do natychmiastowego użycia w aplikacjach, raportach lub drukowanych etykietach.

## Jak generować pliki PNG kodów kreskowych w C# z niestandardowymi wymiarami

Wzorzec przedstawiony powyżej można ponownie wykorzystać dla dowolnej wariacji DataBar lub innych symbologii obsługiwanych przez bibliotekę. Oto kompaktowy szablon, który możesz skopiować i wkleić do klasy pomocniczej:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Wywołaj metodę w ten sposób:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Przypadki brzegowe do rozważenia**

* **Data length** – DataBar Expanded Stacked może kodować do 74 znaków numerycznych. Przekroczenie tego limitu powoduje wyrzucenie wyjątku. Zweryfikuj długość wejścia przed wywołaniem generatora.  
* **Invalid dimensions** – Biblioteka ogranicza liczbę kolumn do 1‑4 i wierszy do 1‑3 dla tej symbologii. Podanie wartości poza tym zakresem zostanie zignorowane lub spowoduje błąd.  
* **Image DPI** – Jeśli potrzebujesz wyższej rozdzielczości do druku, ustaw `generator.Parameters.ImageResolution` przed zapisem.

## Oczekiwany wynik

Po otwarciu `DatabarCols4.png` lub `DatabarRows3.png` powinieneś zobaczyć wyraźny, wysokokontrastowy kod DataBar. Zeskanowanie obrazu skanerem kompatybilnym z GS1 zwróci oryginalny tekst `"Databar Expanded Stacked long"`.

![Przykładowy kod DataBar Expanded Stacked zapisany jako PNG przy użyciu generatora kodów kreskowych C#](image.png)

*Alt text: Przykładowy kod DataBar Expanded Stacked zapisany jako PNG przy użyciu generatora kodów kreskowych C#*

## Zakończenie

Ten samouczek pokazał, jak **barcode generator C#** może być użyty do **create DataBar barcodes** i **generate barcode PNG** plików z niestandardowymi ustawieniami wierszy i kolumn. Postępując zgodnie z sześcioma krokami — inicjalizacją generatora, konfigurowaniem kolumn lub wierszy oraz zapisem jako PNG — otrzymujesz obrazy gotowe do produkcji, odpowiednie dla systemów inwentaryzacji, biletowania lub dowolnego scenariusza wymagającego niezawodnego renderowania kodów kreskowych.

Następnie możesz zbadać:

* Dodawanie kolorów lub obrazów tła do PNG (wciąż kompatybilne z większością skanerów).  
* Korzystanie z innych symbologii, takich jak QR, Code 128 lub PDF417 za pomocą tego samego API `BarcodeGenerator`.  
* Osadzanie wygenerowanego PNG bezpośrednio w widokach ASP.NET Core MVC lub komponentach Blazor.

Śmiało eksperymentuj z różnymi ciągami danych, wymiarami i formatami obrazów (np. JPEG, BMP). Ten sam wzorzec ma zastosowanie, co czyni **barcode generator C#** wszechstronnym narzędziem w zestawie każdego programisty .NET. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj kod kreskowy C# – Utwórz kod DataBar](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Przykład generatora kodów kreskowych – Tworzenie obrazu DataBar w C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}