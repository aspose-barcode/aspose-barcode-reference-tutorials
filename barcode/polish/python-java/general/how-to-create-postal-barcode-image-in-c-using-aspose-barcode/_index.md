---
category: general
date: 2026-10-02
description: Utwórz obraz kodu pocztowego w C# przy użyciu Aspose.BarCode. Dowiedz
  się, jak generować kody Planet i RM4SCC, dostosowywać wypełnione paski oraz zapisywać
  pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: pl
lastmod: 2026-10-02
og_description: Utwórz obraz kodu pocztowego w C# przy użyciu Aspose.BarCode. Ten
  samouczek pokazuje, jak generować kody kreskowe Planet i RM4SCC, regulować wypełnienie
  pasków oraz eksportować pliki PNG.
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: Tworzenie obrazu kodu kreskowego pocztowego w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak utworzyć obraz kodu kreskowego pocztowego w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego pocztowego w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć obraz kodu kreskowego pocztowego** w C#, Aspose.BarCode udostępnia przejrzyste API, które zajmuje się najtrudniejszymi zadaniami. Niezależnie od tego, czy budujesz system etykiet mailingowych, czy usługę weryfikacji adresów, ten przewodnik pokaże Ci dokładnie, jak generować kody kreskowe Planet i RM4SCC, przełączać się między wypełnionymi a pustymi kreskami oraz eksportować wynik jako pliki PNG.

Nauczysz się, jak skonfigurować rozmiar kodu kreskowego, kontrolować zachowanie wypełnienia kreskowych elementów oraz zapisać obraz na dysku — wszystko w jednym, gotowym do uruchomienia programie. Nie są wymagane żadne zewnętrzne narzędzia poza biblioteką Aspose.BarCode dla .NET.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+)
* Visual Studio 2022 lub dowolne IDE obsługujące C#
* Licencjonowaną lub ewaluacyjną kopię **Aspose.BarCode for .NET** (dostępną przez NuGet)

```bash
dotnet add package Aspose.BarCode
```

## Przegląd rozwiązania

Tutorial podzielony jest na trzy logiczne kroki:

1. **Utwórz kod kreskowy Planet z domyślnymi (wypełnionymi) kreskami** – pokazuje typowy wygląd używany przez usługi pocztowe.
2. **Utwórz kod kreskowy Planet z pustymi kreskami** – przydatne, gdy proces drukowania wymaga niewypełnionych kresek.
3. **Utwórz kod kreskowy RM4SCC z wypełnionymi kreskami** – kolejny popularny format pocztowy stosowany w wielu krajach.

Każdy krok stosuje ten sam schemat: tworzy się instancję `BarcodeGenerator`, ustawia `XDimension` (szerokość pojedynczej kreski w pikselach), opcjonalnie modyfikuje `FilledBars` i wywołuje `Save`, aby zapisać plik PNG.

---

## Utwórz obraz kodu kreskowego pocztowego przy użyciu Aspose.BarCode

Poniżej znajduje się kompletny, samodzielny program. Zapisz go jako `Program.cs` i uruchom z wiersza poleceń lub z poziomu IDE.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### Dlaczego każda linia ma znaczenie

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – enum `EncodeTypes.Planet` informuje Aspose.BarCode, że ma użyć symboliki *Planet*, będącej standardowym kodem pocztowym w wielu krajach. To jest sedno **generowania obrazów kodu kreskowego planet**.
* **`XDimension.Pixels = 4`** – szerokość pojedynczej kreski wpływa zarówno na niezawodność skanowania, jak i na rozmiar wizualny. Wartość 4 px sprawdza się w większości drukarek etykiet; możesz ją zwiększyć dla wyższej rozdzielczości.
* **`FilledBars = false`** – domyślnie kreski są wypełnione. Ustawienie `false` tworzy styl „pustych kresek”, wymagany przez niektóre specyfikacje mailingowe.
* **`Save(..., BarCodeImageFormat.Png)`** – PNG zachowuje jakość bezstratną, co czyni go idealnym dla obrazów kodów kreskowych, które muszą być odczytywane przez skanery.

### Oczekiwany wynik

Po uruchomieniu programu w folderze `YOUR_DIRECTORY` pojawią się trzy pliki PNG:

| Nazwa pliku                         | Opis wizualny |
|-------------------------------------|----------------|
| `PostalPlanetFilledBars.png`        | Kod kreskowy Planet z solidnymi czarnymi kreskami |
| `PostalPlanetEmptyBars.png`         | Kod kreskowy Planet, w którym kreski są obrysowane (puste) |
| `PostalRM4SCCFilledBars.png`        | Kod kreskowy RM4SCC z solidnymi kreskami |

Możesz otworzyć dowolny z tych obrazów w przeglądarce zdjęć lub osadzić go bezpośrednio w etykiecie PDF/HTML.

---

## Dalsze dostosowywanie kodu kreskowego (opcjonalnie)

### Zmiana formatu obrazu

Jeśli potrzebujesz innego formatu (np. JPEG do dystrybucji w sieci), zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. Pamiętaj, że JPEG wprowadza artefakty kompresji, które mogą wpływać na wydajność skanera.

### Regulacja rozmiaru obrazu bez skalowania

Zamiast zmieniać `XDimension`, możesz kontrolować całkowite wymiary obrazu poprzez `Parameters.Image.Height` i `Parameters.Image.Width`. Jest to przydatne, gdy masz stały rozmiar etykiety.

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### Użycie innej symboliki kodu kreskowego

Aspose.BarCode obsługuje dziesiątki symbolik pocztowych (np. **USPS Intelligent Mail**, **Japan Post**). Aby **generować alternatywne kody planet**, zamień `EncodeTypes.Planet` na odpowiednią wartość wyliczeniową.

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### Obsługa nieprawidłowych danych

Kody kreskowe pocztowe mają ścisłe reguły długości danych. Jeśli przekażesz ciąg, który nie spełnia specyfikacji, Aspose.BarCode zgłosi `ArgumentException`. Owiń tworzenie generatora w blok `try/catch`, aby wyświetlić przyjazny komunikat o błędzie.

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

---

## Typowe pułapki i wskazówki profesjonalne

| Pułapka | Dlaczego się pojawia | Wskazówka |
|---------|----------------------|-----------|
| **Użycie zbyt małego XDimension** | Kreski stają się cieńsze niż minimalna rozdzielczość skanera, co powoduje błędy odczytu. | Zacznij od `Pixels = 4` i testuj na docelowej drukarce; zwiększ w razie potrzeby. |
| **Zapisywanie do folderu tylko do odczytu** | `Save` zgłasza `UnauthorizedAccessException`. | Upewnij się, że `outputDir` wskazuje lokalizację z prawem zapisu, lub użyj `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`. |
| **Zaniedbanie zwolnienia generatora** | Duże obrazy mogą utrzymywać niezarządzane zasoby. | Umieść generator w instrukcji `using` lub wywołaj `Dispose()` po `Save`. |
| **Mieszanie formatów kodów kreskowych w jednym obrazie** | Niektóre drukarki oczekują jednej symboliki na etykiecie. | Generuj każdy kod osobno i łącz je przy pomocy biblioteki graficznej, jeśli to konieczne. |

---

## Weryfikacja wygenerowanych kodów kreskowych

Aby potwierdzić, że kody są prawidłowe, możesz skorzystać z darmowego serwisu **Aspose.BarCode Demo** lub dowolnej standardowej aplikacji skanującej kody kreskowe. Załaduj pliki PNG i zeskanuj je; zdekodowana wartość powinna wynosić `123456` zarówno dla przykładów Planet, jak i RM4SCC.

---

## Zakończenie

W tym tutorialu nauczyłeś się **tworzyć obrazy kodów kreskowych pocztowych** w C# przy użyciu Aspose.BarCode. Zobaczyłeś, jak **generować obrazy kodu planet** zarówno z wypełnionymi, jak i pustymi kreskami, jak wyprodukować kod RM4SCC oraz jak dostosować rozmiar, format i obsługę błędów. Dzięki kompletnemu, gotowemu do uruchomienia kodowi możesz teraz zintegrować generowanie kodów pocztowych z dowolną aplikacją .NET.

**Kolejne kroki**

* Poznaj inne symboliki pocztowe, takie jak `EncodeTypes.USPSIntelligentMail` (słowo kluczowe: postal barcode PNG).

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia, pomagające opanować dodatkowe funkcje API i eksplorować alternatywne podejścia w własnych projektach.

- [Create Postal Barcode Image in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}