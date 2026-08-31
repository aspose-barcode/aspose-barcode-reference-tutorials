---
category: general
date: 2026-07-15
description: Przykład generatora kodów kreskowych w C#, pokazujący, jak ustawić kolumny,
  jak ustawić wiersze oraz jak szybko wyeksportować obraz kodu kreskowego. Postępuj
  zgodnie z tym przewodnikiem krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: pl
lastmod: 2026-07-15
og_description: Przykład generatora kodów kreskowych w C# pokazuje, jak ustawić kolumny,
  jak ustawić wiersze oraz jak wyeksportować obraz kodu kreskowego. Poznaj pełny przepływ
  pracy w kilka minut.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Przykład generatora kodów kreskowych w C# – kolumny, wiersze i eksport obrazu
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Przykład generatora kodów kreskowych w C# – ustaw kolumny, wiersze i eksportuj
  obraz
url: /pl/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych w C# – Pełny przewodnik

Zastanawiałeś się kiedyś, jak stworzyć **przykład generatora kodów kreskowych** w C#, który pozwala dostosować kolumny, wiersze i następnie wyeksportować wynik jako obraz? Nie jesteś sam. Wielu programistów napotyka problem, gdy potrzebują szybkiego sposobu generowania kodów DataBar Expanded Stacked z własnymi opcjami układu. W tym tutorialu rozwiążemy ten problem krok po kroku, pokazując **jak ustawić kolumny**, **jak ustawić wiersze**, a na koniec **wyeksportować pliki obrazu kodu kreskowego** — wszystko przy użyciu czystego, gotowego do produkcji kodu.

Po przeczytaniu tego przewodnika będziesz mieć kompletny, uruchamialny program, który tworzy obraz kodu kreskowego, dostosowuje jego układ i zapisuje dwa pliki PNG na dysku. Bez tajemniczych bibliotek, bez ukrytej konfiguracji — po prostu czysty C# i niezawodny SDK do kodów kreskowych.

---

## Wymagania wstępne

Zanim przejdziemy dalej, upewnij się, że masz następujące rzeczy:

- **.NET 6.0** (lub nowszą wersję .NET). Kod kompiluje się również z .NET Framework, ale .NET 6+ zapewnia najnowsze ulepszenia środowiska uruchomieniowego.
- **Bibliotekę generowania kodów kreskowych**, która obsługuje DataBar Expanded Stacked. W przykładach użyjemy **Aspose.BarCode for .NET**, dostępnej w wersji próbnej i oferującej prosty interfejs API.
- Środowisko programistyczne — Visual Studio 2022, Rider lub VS Code będą odpowiednie.
- Uprawnienia do zapisu w folderze, w którym zostaną zapisane pliki PNG.

Jeśli nie masz jeszcze biblioteki, pobierz ją z NuGet:

```bash
dotnet add package Aspose.BarCode
```

Ten jedyny wiersz pobiera wszystko, co potrzebne, w tym klasę `BarcodeGenerator` oraz wyliczenie `BarCodeImageFormat` używane później.

---

## Krok 1: Utworzenie szkieletu projektu

Utwórz nową aplikację konsolową i dodaj niezbędne dyrektywy `using`:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Oto **kompletny** szkielet pliku `Program.cs`:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** Trzymaj metodę `Main` schludną; ciężkie operacje przeniesiemy do metod pomocniczych. Dzięki temu kod będzie łatwiejszy do testowania i ponownego użycia.

---

## Krok 2: Stworzenie przykładu generatora kodów kreskowych

Teraz zbudujemy rdzeniowy **przykład generatora kodów kreskowych**, który tworzy kod DataBar Expanded Stacked. To serce tutorialu.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Dlaczego oddzielamy to w osobnej metodzie? Izoluje to logikę **przykładu generatora kodów kreskowych**, co umożliwia jej ponowne użycie, jeśli później będziesz potrzebował generować wiele kodów z różnymi danymi.

---

## Krok 3: Jak ustawić kolumny

Format DataBar Expanded Stacked może być renderowany w układzie kolumnowym. Domyślnie SDK wybiera rozsądną wartość, ale często trzeba dopasować ją do konkretnego rozmiaru etykiety. Oto **jak ustawić kolumny** na cztery:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Dlaczego kolumny mają znaczenie:** Każda kolumna dodaje pionową przestrzeń, co może być kluczowe przy drukowaniu na wąskich etykietach. Ustawienie ich na `4` daje zrównoważony, czytelny kod kreskowy bez utraty niezawodności skanowania.

W głównym przepływie wywołamy tę metodę:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Krok 4: Jak ustawić wiersze

Czasami potrzebny jest bardziej zwarty układ, zwłaszcza przy drukowaniu na krótkiej, szerokiej etykiecie. Wtedy przydaje się **jak ustawić wiersze**. Przejście z układu kolumnowego na wierszowy może zmniejszyć rozmiar kodu kreskowego.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Wywołanie wygląda tak:

```csharp
SetRows(generator, 3);
```

> **Uwaga o przypadkach brzegowych:** Nie możesz jednocześnie ustawiać zarówno kolumn, jak i wierszy — SDK nada priorytet wierszom, jeśli przypiszesz nie‑zerową wartość do `Rows`. Dlatego przed zmianą układu wyczyść drugą właściwość:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Krok 5: Eksport obrazu kodu kreskowego

Po skonfigurowaniu układu, ostatnim elementem jest **eksport obrazu kodu kreskowego**. SDK obsługuje PNG, JPEG, BMP i inne. PNG jest bezstratny i dobrze sprawdza się w większości drukarek etykiet.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Połączenie wszystkiego w metodzie `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Oczekiwany wynik

Po uruchomieniu programu powinny pojawić się dwa pliki PNG w folderze `YOUR_DIRECTORY`:

- **DatabarCols4.png** – kod kreskowy wyrenderowany z czterema pionowymi kolumnami.
- **DatabarRows3.png** – te same dane, ale rozmieszczone w trzech poziomych wierszach.

Oba obrazy będą miały wymiary 300 × 150 px (ustawione w `CreateGenerator`) i będą gotowe do druku lub osadzenia w PDF.

---

## Typowe pułapki i wskazówki

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| **Błędy ścieżki pliku** | Użycie ścieżki względnej bez odpowiedniego katalogu może spowodować `DirectoryNotFoundException`. | Użyj `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` lub upewnij się, że folder istnieje przy pomocy `Directory.CreateDirectory`. |
| **Konflikt wierszy vs. kolumn** | Ustawienie obu właściwości powoduje, że SDK ignoruje kolumny. | Jawnie ustaw przeciwną właściwość na `0`, gdy przełączasz układy. |
| **Nieobsługiwany typ kodu kreskowego** | Nie wszystkie biblioteki obsługują DataBar Expanded Stacked. | Sprawdź, czy wersja Twojej biblioteki zawiera `EncodeTypes.DatabarExpandedStacked`. |
| **Niska jakość obrazu** | Domyślne DPI może być niewystarczające dla drukarek wysokiej rozdzielczości. | Zmień `generator.Parameters.Image.ResolutionX/Y` na `300` lub wyższą wartość. |

---

## Rozszerzanie przykładu generatora kodów kreskowych

Teraz, gdy masz solidny **przykład generatora kodów kreskowych**, możesz zastanawiać się, co jeszcze można zrobić.

1. **Dodaj kolory** – ustaw `generator.Parameters.Barcode.ForegroundColor` na `Color.Blue`.
2. **Koduj inne dane** – przekaż zmienną string zamiast sztywno zakodowanego `"Databar Expanded Stacked long"`.
3. **Przetwarzanie wsadowe** – iteruj po pliku CSV z kodami produktów, generując PNG dla każdego.
4. **Integracja z API webowym** – udostępnij endpoint, który zwraca kod kreskowy jako ciąg base64.

Każde z tych rozszerzeń podąża tym samym schematem: skonfiguruj instancję `BarcodeGenerator`, a następnie wywołaj `Save` lub `Export` w zależności od potrzeb.

---

## Zakończenie

Przeszliśmy przez kompletny **przykład generatora kodów kreskowych** w C#, który pokazuje **jak ustawić kolumny**, **jak ustawić wiersze** oraz **jak eksportować pliki obrazu kodu kreskowego**. Kod jest samodzielny, działa od razu z Aspose.BarCode i demonstruje najlepsze praktyki pod kątem czytelności i utrzymania.

Śmiało eksperymentuj — zamień ciąg danych, zmień wymiary obrazu lub przełącz się na inną symbologię kodu kreskowego. Koncepcje, które tu poznałeś — inicjalizacja generatora, konfiguracja parametrów układu i eksport — mają zastosowanie praktycznie do każdego typu kodu kreskowego obsługiwanego przez SDK.

Masz pytania dotyczące tworzenia programów generujących obrazy kodów kreskowych w C#, lub potrzebujesz pomocy z konkretną drukarką etykiet? Zostaw komentarz poniżej i powodzenia w kodowaniu!

---


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}