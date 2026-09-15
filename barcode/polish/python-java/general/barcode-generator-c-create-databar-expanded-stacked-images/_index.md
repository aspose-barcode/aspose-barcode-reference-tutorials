---
category: general
date: 2026-07-24
description: Samouczek generatora kodów kreskowych w C#, który pokazuje, jak wygenerować
  obraz kodu kreskowego, ustawić kolumny, ustawić wiersze oraz stworzyć kod Databar
  w kilku linijkach kodu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: pl
lastmod: 2026-07-24
og_description: Samouczek Generatora Kodów Kreskowych w C# prowadzi Cię przez generowanie
  obrazu kodu kreskowego, konfigurowanie kolumn i wierszy oraz tworzenie kodu Databar
  z przejrzystymi przykładami kodu.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Generator kodów kreskowych C# – Szybko generuj kody DataBar Stacked
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Generator kodów kreskowych C# – Tworzenie obrazów DataBar Expanded Stacked
url: /pl/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generator kodów kreskowych C# – Kompletny przewodnik po DataBar Expanded Stacked

Zastanawiałeś się kiedyś, jak używać **barcode generator c#**, aby w kilka sekund generować ostre, skanowalne obrazy? Być może patrzyłeś na pusty projekt, nie wiedząc, gdzie powinny znajdować się kolumny lub wiersze, albo jak faktycznie *generate barcode image* pliki bez bólu głowy. Cóż, jesteś we właściwym miejscu. W tym samouczku skonfigurujemy małą aplikację konsolową, utworzymy kod kreskowy DataBar Expanded Stacked, dostosujemy jego układ i zapisujemy wynik jako PNG — wszystko przy użyciu biblioteki **barcode generator c#**.

Omówimy wszystko, co musisz wiedzieć: instalację pakietu, konfigurowanie kolumn i wierszy (tak, odpowiemy na *how to set columns* i *how to set rows*), oraz w końcu jak **create databar barcode** obiekty, które możesz wstawić do faktur, biletów lub czegokolwiek, co wymaga etykiety odczytywanej maszynowo. Nie potrzebujesz zewnętrznej dokumentacji; po prostu kopiuj‑wklej, uruchom i zobaczysz dwa pliki PNG w swoim folderze.

## Co będziesz potrzebować

- .NET 6.0 SDK lub nowszy (kod działa na .NET Core, .NET Framework oraz .NET 5+)
- Nowy projekt konsolowy (`dotnet new console`) – możesz także użyć Visual Studio, jeśli wolisz interfejs graficzny.
- Pakiet NuGet Aspose.BarCode for .NET (biblioteka napędzająca **barcode generator c#**). Zainstaluj go za pomocą:

```bash
dotnet add package Aspose.BarCode
```

To wszystko. Po przywróceniu pakietu jesteś gotowy do działania.

## Generator kodów kreskowych C# – Konfiguracja projektu

Najpierw wprowadźmy niezbędne przestrzenie nazw i utwórzmy metodę pomocniczą, która utrzyma naszą główną procedurę w porządku.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Dlaczego ta struktura działa

- **Separation of concerns** – każdy pomocnik skupia się na jednej konfiguracji (kolumny vs. wiersze). Dzięki temu kod jest łatwiejszy do odczytania i ponownego użycia.
- **Explicit parameters** – przekazujemy `columns` lub `rows` jako argumenty, więc możesz wywołać tę samą metodę z dowolną wartością bez edytowania ciała.
- **Immediate feedback** – `Console.WriteLine` informuje dokładnie, gdzie plik został zapisany, co jest przydatne podczas uruchamiania programu z terminala.

## Jak ustawić kolumny dla DataBar Expanded Stacked

Właściwość `DataBar.Columns` jest ustawieniem, które określa, ile pionowych segmentów będzie zawierał kod kreskowy. Domyślnie jest to `4`, ale możesz potrzebować `2` lub `6` w zależności od ilości danych, które kodujesz, lub wymagań skanera. Oto szybki fragment, który izoluje logikę ustawiania kolumn:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** Gdy zwiększasz liczbę kolumn, całkowita szerokość kodu kreskowego rośnie proporcjonalnie. Jeśli planujesz osadzić obraz w PDF-ie lub na stronie internetowej, upewnij się, że kontener pomieści dodatkową szerokość, w przeciwnym razie skaner może go nieprawidłowo odczytać.

## Jak ustawić wiersze dla DataBar Expanded Stacked

Wiersze działają w ten sam sposób, ale wpływają na wysokość kodu kreskowego. Domyślna liczba wierszy to `3`. Jeśli Twoja etykieta ma ograniczoną przestrzeń pionową, możesz zmniejszyć ją do `2`. Z drugiej strony, więcej wierszy może poprawić czytelność na drukarkach o niskiej rozdzielczości.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** Ustawienie wierszy na wartość niższą niż minimalna wymagana dla zakodowanych danych spowoduje wyjątek w czasie wykonywania. Biblioteka rzuca `ArgumentException` z czytelną wiadomością, więc od razu dowiesz się, czy konfiguracja jest nieprawidłowa.

## Generowanie obrazu kodu kreskowego – zapisywanie jako PNG

Obie powyższe metody kończą się wywołaniem `Save`. Enum `BarCodeImageFormat.Png` informuje Aspose.BarCode, aby wyjściowy plik był bezstratnym PNG, co jest idealne w większości scenariuszy skanowania, ponieważ zachowuje ostre krawędzie. Jeśli wolisz inny format (JPEG dla sieci, BMP dla starszych systemów), po prostu zamień wartość enum – nie są potrzebne żadne inne zmiany w kodzie.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

Wygenerowane pliki PNG wyglądają tak (wyobraź sobie obraz; poniższy tekst alternatywny go opisuje):

> **Tekst alternatywny dla wygenerowanych obrazów:** *Kod kreskowy DataBar Expanded Stacked z 4 kolumnami (po lewej) i 3 wierszami (po prawej), renderowany w wysokim kontraście czerni na przezroczystym tle.*

## Tworzenie kodu DataBar – pełny działający przykład

Łącząc wszystko razem, oto kompaktowa wersja, którą możesz wkleić bezpośrednio do `Program.cs`. Pokazuje zarówno konfigurację kolumn, jak i wierszy, oraz szybki test, czy pliki istnieją po zapisaniu.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Oczekiwany wynik

Gdy uruchomisz program (`dotnet run`), powinieneś zobaczyć w konsoli linie podobne do:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Otwórz dwa pliki PNG w dowolnej przeglądarce obrazów; zauważysz, że lewy plik ma cztery pionowe moduły (kolumny), podczas gdy prawy plik ma trzy moduły wysokości (wiersze). Oba są idealnie skanowalne dowolnym standardowym czytnikiem DataBar.

## Częste pułapki i jak ich uniknąć

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| `ArgumentException: Columns value is out of range` | Kolumny ustawione na 0 lub > 8 (biblioteka ogranicza do 8). | Używaj wartości od **1** do **8**. |
| Kod kreskowy jest rozmyty w PDF | PNG zapisany z domyślną rozdzielczością DPI (96) i następnie skalowany. | Użyj `generator.Parameters.ImageResolution = 300;` przed zapisem. |
| Skaner nie działa przy konfiguracji tylko z wierszami | Wiersze zmienione, ale kolumny pozostawione domyślne, które nie pasują do długości danych. | Dostosuj zarówno wiersze **jak i** kolumny razem, lub pozwól bibliotece automatycznie dopasować rozmiar, pomijając ręczne ustawienia. |

## Kolejne kroki

Teraz, gdy wiesz, jak **generate barcode image**, **set columns**, **set rows** i **create databar barcode** przy użyciu **barcode generator c#**, możesz:

- Osadź pliki PNG w PDF-ach przy użyciu `Aspose.PDF` lub `iTextSharp`.
- Przejdź na `EncodeTypes.DatabarLimited`, jeśli potrzebujesz mniejszego rozmiaru.
- Eksperymentuj z kolorami (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Dodaj kody QR lub inne symbologie w tym samym projekcie — Aspose.BarCode obsługuje ponad 150 typów.

Jeśli napotkasz jakiekolwiek problemy, zostaw komentarz poniżej lub sprawdź oficjalną dokumentację Aspose.BarCode (referencja API jest wyczerpująca i zawiera dziesiątki działających przykładów kodu). Szczęśliwego kodowania i niech Twoje skanery nigdy nie przegapią znaku!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Utwórz obraz kodu DotCode – wiersze i kolumny (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Utwórz obraz kodu kreskowego c# – skonfiguruj wiersze i kolumny Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generuj obraz kodu kreskowego – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}