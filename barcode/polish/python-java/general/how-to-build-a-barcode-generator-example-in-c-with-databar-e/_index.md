---
category: general
date: 2026-09-19
description: przykład generatora kodów kreskowych w C# pokazujący, jak generować kody
  kreskowe w C# przy użyciu Aspose.BarCode dla układów kolumnowych i wierszowych
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: pl
lastmod: 2026-09-19
og_description: Przykład generatora kodów kreskowych demonstruje, jak generować kod
  kreskowy w C# z układami kolumn i wierszy przy użyciu Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: przykład generatora kodów kreskowych – tworzenie kodów DataBar Expanded
  Stacked w C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak stworzyć przykład generatora kodów kreskowych w C# z DataBar Expanded Stacked
url: /pl/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych – tworzenie kodów DataBar Expanded Stacked w C#

Jeśli potrzebujesz **przykładu generatora kodów kreskowych**, który działa w projekcie .NET, ten przewodnik pokaże Ci dokładnie, jak generować kody kreskowe w C# przy użyciu biblioteki Aspose.BarCode. Zobaczysz, jak skonfigurować kod DataBar Expanded Stacked zarówno w układzie kolumnowym, jak i w układzie wierszowym, oraz otrzymasz gotowy do uruchomienia kod, który generuje obrazy PNG.

Samouczek obejmuje wszystko, od instalacji pakietu NuGet po zapisywanie końcowych obrazów, dzięki czemu możesz skopiować kod do własnego rozwiązania bez dodatkowych poszukiwań.

## Czego się nauczysz

* Jak zainstalować i odwołać się do Aspose.BarCode w projekcie C#.
* Jak stworzyć **przykład generatora kodów kreskowych**, który koduje długi ciąg danych.
* Jak ustawić układ 4‑kolumnowy i 3‑wierszowy dla tego samego typu kodu kreskowego.
* Jak zapisać wygenerowane obrazy jako pliki PNG.

Po zakończeniu tego artykułu będziesz mieć dwa gotowe do użycia pliki PNG: `ExpandedStackedCols4.png` (cztery kolumny) oraz `ExpandedStackedRows3.png` (trzy wiersze).

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7.2).
* Visual Studio 2022, VS Code lub dowolne IDE C#, którego preferujesz.
* Dostęp do Internetu w celu pobrania pakietu NuGet **Aspose.BarCode**.

Nie są wymagane dodatkowe usługi zewnętrzne.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję Aspose.BarCode do pliku projektu. Po przywróceniu pakietu możesz odwoływać się do jego przestrzeni nazw w plikach źródłowych C#.

## Krok 2: Dodaj wymagane dyrektywy using

Utwórz nową aplikację konsolową C# (lub dodaj kod do istniejącego projektu) i umieść następujące instrukcje `using` na początku pliku:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te dyrektywy zapewniają dostęp do klasy `BarcodeGenerator` oraz wyliczenia `EncodeTypes` używanych w **przykładzie generatora kodów kreskowych**.

## Krok 3: Utwórz przykład generatora kodów kreskowych z układem 4‑kolumnowym

Pierwsza część przykładu tworzy kod DataBar Expanded Stacked, który wykorzystuje czterokolumnowy układ. Poniższy kod odtwarza dokładne kroki pokazane w oryginalnym fragmencie, ale dodaje komentarze wyjaśniające, dlaczego każda linia jest potrzebna.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Dlaczego to działa**

* `EncodeTypes.DatabarExpandedStacked` informuje Aspose.BarCode, aby wygenerował symbol DataBar Expanded Stacked, który jest odpowiedni dla zastosowań detalicznych.
* Ustawienie `DataBar.Columns` na `4` zmusza generator do podzielenia symbolu na cztery pionowe sekcje, co poprawia czytelność na wąskich etykietach.
* `Save` zapisuje kod kreskowy na dysku; argument `BarCodeImageFormat.Png` zapewnia bezstratną jakość obrazu.

Uruchomienie tego bloku tworzy plik `ExpandedStackedCols4.png` w katalogu roboczym aplikacji. Plik zawiera wysokiej rozdzielczości kod kreskowy, który może być odczytany przez dowolny standardowy czytnik DataBar.

## Krok 4: Ponownie zainicjalizuj generator dla innego układu

Aby zademonstrować układ wierszowy, potrzebujesz nowej instancji `BarcodeGenerator`. Ponowne zainicjalizowanie zapewnia, że poprzednie ustawienie kolumn nie wpłynie na nową konfigurację.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Krok 5: Skonfiguruj kod kreskowy do użycia układu 3‑wierszowego

API DataBar również obsługuje układ wierszowy. Ustawienie właściwości `Rows` określa, ile poziomych segmentów będzie zawierał symbol.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Dlaczego możesz wybrać wiersze zamiast kolumn**

Wiersze są przydatne, gdy wysokość etykiety jest ograniczona, a szerokość wystarczająca. Układ trzech wierszy kompresuje kod kreskowy w pionie, zachowując wymaganą ilość danych.

## Pełny plik źródłowy

Poniżej znajduje się kompletny, samodzielny plik `Program.cs`, który możesz skompilować i uruchomić bezpośrednio. Zawiera zarówno przykłady kolumn, jak i wierszy, więc uzyskasz dwa pliki PNG przy jednym uruchomieniu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Oczekiwany wynik

Po uruchomieniu programu zobaczysz dwa komunikaty w konsoli potwierdzające utworzenie plików:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Oba pliki PNG będą wyświetlać kod DataBar Expanded Stacked, który koduje ciąg `"Long data string"`. Zeskanowanie dowolnego obrazu standardowym skanerem kodów kreskowych zwróci pierwotne dane.

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|--------|
| **Czy mogę zmienić format obrazu?** | Tak. Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Tiff` w zależności od wymagań. |
| **Co jeśli ciąg danych jest krótszy?** | Format DataBar automatycznie dostosowuje rozmiar symbolu; nie musisz modyfikować ustawień układu. |
| **Jak ustawić rozmiar kodu kreskowego (szerokość/wysokość)?** | Użyj `generator.Parameters.Image.Width` i `generator.Parameters.Image.Height` przed wywołaniem `Save`. |
| **Czy można dodać czytelny dla człowieka podpis?** | Ustaw `generator.Parameters.Barcode.CodeText` i włącz `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Jakie wersje .NET są obsługiwane?** | Aspose.BarCode obsługuje .NET Standard 2.0, .NET 5/6 oraz .NET Framework 4.6.1+. |

Rozważenie tych wariantów sprawia, że **przykład generatora kodów kreskowych** jest wystarczająco solidny do użycia w produkcji.

## Porady profesjonalne

* **Używaj ponownie obiektu generatora tylko wtedy, gdy układ pozostaje taki sam.** Tworzenie nowej instancji dla każdego układu, jak pokazano w Krokach 4‑5, zapobiega przypadkowemu przenoszeniu właściwości.
* **Zweryfikuj wygenerowany kod kreskowy** przy użyciu `generator.Validate()`, jeśli musisz zapewnić zgodność ze standardami ISO/GS1.
* **Przetwarzanie wsadowe:** Umieść logikę kolumn i wierszy w pętli iterującej po liście konfiguracji układu. To zmniejsza duplikację kodu, gdy potrzebujesz wielu wariantów.

## Zakończenie

Ten **przykład generatora kodów kreskowych** pokazuje, jak **generować kod C#** tworzący zarówno 4‑kolumnowy, jak i 3‑wierszowy kod DataBar Expanded Stacked. Masz teraz kompletny, uruchamialny program, zrozumienie kluczowych właściwości (`Columns`, `Rows`) oraz praktyczne wskazówki, jak rozbudować rozwiązanie.

Następnie poznaj powiązane tematy, takie jak **dostosowywanie kolorów kodów kreskowych**, **osadzanie kodów kreskowych w dokumentach PDF** lub **generowanie kodów QR przy użyciu Aspose.BarCode**. Każdy z tych tematów opiera się na tych samych zasadach API omówionych tutaj.

Śmiało eksperymentuj z różnymi ciągami danych, formatami obrazów i kombinacjami układów. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Przykład generatora kodów kreskowych w C# – Ustaw kolumny, wiersze i eksportuj obraz](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generowanie kodu Databar Aspose.BarCode przy użyciu .NET API – Konfiguracja wierszy i kolumn](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Przykład generatora kodów kreskowych w C# – ustaw szerokość i wysokość](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}