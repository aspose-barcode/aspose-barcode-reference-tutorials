---
category: general
date: 2026-09-16
description: Dowiedz się, jak ustawić kolumny kodów kreskowych w C# przy użyciu BarcodeGenerator
  oraz jak ustawić wiersze kodów kreskowych dla kodów DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: pl
lastmod: 2026-09-16
og_description: Szybko ustaw kolumny kodów kreskowych w C#. Ten przewodnik pokazuje,
  jak skonfigurować kolumny, wiersze i format obrazu za pomocą BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Ustaw kolumny i wiersze kodu kreskowego w C# – kompletny przewodnik BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak ustawić kolumny i wiersze kodu kreskowego przy użyciu C# BarcodeGenerator
url: /pl/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ustawić kolumny i wiersze kodu kreskowego w C# BarcodeGenerator

Jeśli potrzebujesz ustawić kolumny kodu kreskowego w aplikacji C#, ten tutorial pokazuje dokładne wymagane kroki. Zobaczysz, jak skonfigurować zarówno kolumny, jak i wiersze dla kodu DataBar Expanded Stacked, a następnie zapisać wynik jako obraz PNG.

Generowanie kodów kreskowych programowo oszczędza Ci ręcznej pracy projektowej i zapewnia spójność w raportach, fakturach oraz etykietach produktów. Poniższy przykład obejmuje pełny przepływ pracy, od instalacji biblioteki po wygenerowanie dwóch obrazów — jednego z niestandardową liczbą kolumn i drugiego z niestandardową liczbą wierszy.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany.  
* Odwołanie do pakietu NuGet **Aspose.BarCode for .NET**. Zainstaluj go za pomocą:

```bash
dotnet add package Aspose.BarCode
```

* Uprawnienia zapisu do folderu, w którym będą zapisywane wygenerowane pliki PNG.

Te wymagania zapewniają, że kod zostanie skompilowany i uruchomiony bez dodatkowej konfiguracji.

## Jak ustawić kolumny kodu kreskowego w C#

Pierwszym istotnym krokiem jest utworzenie instancji `BarcodeGenerator` dla symbologii **DataBar Expanded Stacked** i przypisanie żądanej liczby kolumn.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to działa:**  
`EncodeTypes.DatabarExpandedStacked` informuje bibliotekę, którą symbologię ma renderować. Ustawienie `Parameters.Barcode.DataBar.Columns` zmienia wewnętrzny układ modułów, co bezpośrednio wpływa na wizualną szerokość kodu kreskowego. Metoda `Save` zapisuje obraz na dysku w żądanym formacie `BarCodeImageFormat`.

### Oczekiwany wynik
Otwórz `C:\Barcodes\DatabarCols4.png` w dowolnym przeglądarce obrazów. Powinieneś zobaczyć kod DataBar Expanded Stacked, który jest szerszy niż domyślny, ponieważ używa czterech kolumn.

## Jak ustawić wiersze kodu kreskowego w C#

Po zapisaniu obrazu opartego na kolumnach możesz potrzebować kodu kreskowego o zmiennej wysokości poprzez dostosowanie wierszy. Proces jest analogiczny do konfiguracji kolumn, ale używa właściwości `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Dlaczego to działa:**  
Ponowne zainicjowanie generatora zapewnia, że poprzednie ustawienie kolumn nie interferuje z konfiguracją wierszy. Zmiana `Parameters.Barcode.DataBar.Rows` modyfikuje wysokość kodu, tworząc wyższy obraz, gdy liczba wierszy przekracza domyślną wartość.

### Oczekiwany wynik
Otwórz `C:\Barcodes\DatabarRows3.png`. Kod kreskowy będzie wyższy, odzwierciedlając konfigurację trzech wierszy.

## Pełny przykład end‑to‑end

Poniżej znajduje się pojedynczy program, który tworzy oba obrazy w jednej egzekucji. Trzymanie kodu w jednym pliku demonstruje, jak można przełączać się między konfiguracjami kolumn i wierszy bez ponownego uruchamiania aplikacji.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Uruchomienie programu generuje dwa pliki PNG:

* **DatabarCols4.png** – kod kreskowy z czterema kolumnami.  
* **DatabarRows3.png** – kod kreskowy z trzema wierszami.

Oba pliki używają **formatu obrazu kodu kreskowego** PNG, który zachowuje ostre krawędzie i obsługuje bezstratną kompresję — idealny do druku i wyświetlania cyfrowego.

## Częste pytania i wskazówki

| Pytanie | Odpowiedź |
|----------|--------|
| *Czy mogę używać JPEG zamiast PNG?* | Tak. Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. JPEG jest mniejszy, ale wprowadza artefakty kompresji, które mogą wpływać na niezawodność skanera. |
| *Jaka jest maksymalna liczba kolumn lub wierszy?* | Biblioteka waliduje wartości względem specyfikacji DataBar. Wartości poza dozwolonym zakresem powodują wyrzucenie `ArgumentException`. Sprawdź dokumentację Aspose.BarCode, aby poznać dokładne limity. |
| *Czy muszę zwolnić zasoby `BarcodeGenerator`?* | Klasa implementuje `IDisposable`. Umieść generator w bloku `using`, jeśli tworzysz wiele instancji w pętli, aby szybko zwolnić zasoby niezarządzane. |
| *Jak zmienić rozmiar kodu kreskowego bez zmiany kolumn/wierszy?* | Użyj `barcodeGenerator.Parameters.Image.Width` i `Height`, aby skalować wyjściowy obraz, zachowując niezmieniony układ modułów. |

**Wskazówka:** Gdy generujesz kody kreskowe do druku wysokiej rozdzielczości, zwiększ wymiary wyjściowego obrazu (`Width`/`Height`) zamiast liczby kolumn lub wierszy. Takie podejście zachowuje standardowy rozmiar modułu określony przez symbologię, jednocześnie dając ostrzejszy obraz.

## Zakończenie

Teraz wiesz, jak ustawić kolumny i wiersze kodu kreskowego w C# przy użyciu klasy **BarcodeGenerator**. Poradnik obejmował inicjalizację generatora, konfigurowanie liczby kolumn i wierszy, zapisywanie kodu w formacie PNG oraz obsługę typowych wariacji, takich jak zmiana formatu obrazu i zwalnianie zasobów.

Następnie zapoznaj się z powiązanymi tematami, takimi jak **dostosowywanie kolorów kodu kreskowego**, **dodawanie tekstu czytelnego dla człowieka** oraz **osadzanie kodów kreskowych w dokumentach PDF**. Wszystkie te rozszerzenia opierają się na tym samym wzorcu konfiguracji przedstawionym tutaj, umożliwiając tworzenie w pełni funkcjonalnych rozwiązań kodów kreskowych dla dowolnej aplikacji .NET.

## Co warto nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z krok‑po‑kroku wyjaśnieniami, pomagając opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Przewodnik po kodzie DataBar Expanded Stacked – jak generować i ustawiać rozmiar w C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Przykład generatora kodów kreskowych w C# – ustaw szerokość i wysokość](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}