---
category: general
date: 2026-08-19
description: Dowiedz się, jak wygenerować plik PNG z kodem kreskowym w C# i dostosować
  jego wysokość, obejmując generowanie obrazów kodów kreskowych oraz łatwą zmianę
  wysokości kodu kreskowego.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: pl
lastmod: 2026-08-19
og_description: Utwórz plik PNG z kodem kreskowym w C# i dowiedz się, jak generować
  obrazy kodów kreskowych, regulować ich wysokość oraz zmieniać ją dla optymalnego
  skanowania.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Tworzenie pliku PNG z kodem kreskowym w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Jak utworzyć plik PNG z kodem kreskowym o regulowanej wysokości w C#
url: /pl/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć plik PNG z kodem kreskowym o regulowanej wysokości w C#

Jeśli potrzebujesz utworzyć **plik PNG z kodem kreskowym** w C#, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, gotowy do uruchomienia przykład, który demonstruje **jak generować obrazy kodów kreskowych** oraz jak **regulować wysokość kodu kreskowego** dla różnych zastosowań.

Tworzenie pliku PNG z kodem kreskowym jest powszechnym wymaganiem w systemach inwentaryzacji, terminalach punktu sprzedaży oraz w każdej aplikacji, która musi drukować lub wyświetlać dane odczytywane maszynowo. Po zakończeniu tego samouczka będziesz w stanie zmienić wysokość kodu kreskowego, zapisać wiele plików PNG oraz zrozumieć wpływ wysokości na niezawodność skanowania.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)  
* Pakiet NuGet **Aspose.BarCode for .NET** (przykład kodu używa tej biblioteki)  

Możesz dodać pakiet z wiersza poleceń:

```bash
dotnet add package Aspose.BarCode
```

> **Wskazówka:** Darmowa wersja ewaluacyjna Aspose.BarCode działa w środowisku deweloperskim i testowym. W produkcji należy uzyskać licencjonowany klucz.

## Zainstaluj bibliotekę kodów kreskowych

Pierwszym krokiem jest odwołanie do biblioteki w projekcie. Dodaj następujące dyrektywy `using` na początku pliku C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te przestrzenie nazw dają dostęp do `BarcodeGenerator`, `EncodeTypes` oraz `BarCodeImageFormat`.

## Utwórz plik PNG z kodem kreskowym

Teraz tworzymy instancję `BarcodeGenerator`, która wygeneruje **plik PNG z kodem kreskowym**. Przykład używa symboliki Databar OmniDirectional, ale możesz zamienić `EncodeTypes.DatabarOmniDirectional` na dowolny obsługiwany typ.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Ciąg znaków `"(01)12345678901231"` jest zgodny z formatem GS1 Application Identifier dla 14‑cyfrowego GTIN. Dostosuj dane do własnych identyfikatorów produktów.

## Ustaw wymiar X (opcjonalnie)

Wymiar X określa szerokość pojedynczego modułu kodu kreskowego. Wartość wyrażona w pikselach daje precyzyjną kontrolę nad rozmiarem obrazu.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Wartość `2` piksele dobrze sprawdza się na większości wyświetlaczy. Zwiększ ją, jeśli potrzebujesz większego kodu kreskowego przy drukowaniu.

## Regulacja wysokości kodu kreskowego i zapis pliku PNG

Właściwość **BarHeight** kontroluje pionowy rozmiar pasków. Zmiana tej wartości pozwala **regulować wysokość kodu kreskowego** bez wpływu na zakodowane dane.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Plik `DatabarBarHeight30Pixels.png` jest teraz **plikem PNG z kodem kreskowym** o wysokości 30 pikseli.  

Aby **zmienić wysokość kodu kreskowego** i utworzyć drugi obraz, po prostu przypisz nową wartość i ponownie wywołaj `Save`:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Masz teraz dwa pliki PNG — jeden o wysokości 30 px, a drugi 60 px — co demonstruje, jak **regulować wysokość kodu kreskowego** w locie.

### Dlaczego wysokość pasków ma znaczenie

* **Czytelność:** Skanery oczekują minimalnej wysokości dla niezawodnego wykrywania. Zbyt krótki kod kreskowy może zostać pominięty, szczególnie przy kamerach o niskiej rozdzielczości.  
* **Estetyka:** Dopasowanie wysokości kodu kreskowego do otaczających elementów projektu tworzy czystszy interfejs.  
* **Ograniczenia druku:** Niektóre drukarki etykiet mają stałe szczeliny wysokości; regulacja wysokości kodu kreskowego zapewnia dopasowanie.  

**Najlepsza praktyka:** Utrzymuj wysokość jako wielokrotność wymiaru X (np. 30 px przy wymiarze X równym 2 px), aby zachować proporcje i uniknąć zniekształceń.

## Pełny przykład

Poniżej znajduje się pełny, samodzielny program, który możesz wkleić do aplikacji konsolowej i uruchomić od razu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu tworzy dwa pliki w katalogu roboczym wykonywalnego pliku:

* `DatabarBarHeight30Pixels.png` – plik PNG z kodem kreskowym o wysokości 30 pikseli  
* `DatabarBarHeight60Pixels.png` – plik PNG z kodem kreskowym o wysokości 60 pikseli  

Otwórz dowolny z plików PNG w dowolnym przeglądarce obrazów; zobaczysz wyraźny kod Databar OmniDirectional gotowy do skanowania.

## Przypadki brzegowe i rozwiązywanie problemów

| Sytuacja | Co sprawdzić | Zalecane rozwiązanie |
|-----------|---------------|-----------------|
| Kod kreskowy jest rozmyty | Wymiar X jest zbyt niski dla wybranej wysokości | Zwiększ `XDimension.Pixels` (np. z 2 do 3) |
| Skaner nie działa przy niskiej wysokości kodu | Wysokość poniżej minimalnej dla skanera | Ustaw `BarHeight.Pixels` na co najmniej 30 px (lub zgodnie ze specyfikacją skanera) |
| Plik PNG jest pusty lub uszkodzony | Ścieżka wyjściowa nieprawidłowa lub brak uprawnień do zapisu | Użyj ścieżki bezwzględnej lub upewnij się, że aplikacja ma dostęp do zapisu |
| Potrzebna inna symbolika | Obecny `EncodeTypes` nie jest odpowiedni | Zamień `EncodeTypes.DatabarOmniDirectional` na inną wartość wyliczenia (np. `EncodeTypes.Code128`) |

## Najczęściej zadawane pytania

**Q: Czy mogę generować inne formaty obrazu (JPEG, BMP)?**  
A: Tak. Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp` itd.

**Q: Jak wstawić PNG na stronę internetową?**  
A: Udostępnij wygenerowany PNG przez endpoint HTTP lub przekonwertuj go na ciąg Base64 i umieść w atrybucie `src` znacznika `<img>`.

**Q: Czy istnieje sposób, aby ustawić kolor tła?**  
A: Użyj `generator.Parameters.Image.BackgroundColor = Color.White;` (lub dowolny `System.Drawing.Color`).

## Zakończenie

Teraz wiesz, jak **generować plik PNG z kodem kreskowym** w C# i precyzyjnie **regulować wysokość kodu kreskowego**, aby spełnić wymagania skanowania lub projektu. Zmieniając właściwość `BarHeight.Pixels`, możesz **zmieniać wysokość kodu kreskowego** w locie i tworzyć wiele zasobów PNG z jednego kodu.

Następnie, odkryj inne opcje dostosowywania, takie jak kolor pierwszego planu, marginesy i dodawanie tekstu czytelnego dla człowieka. Możesz także eksperymentować z różnymi symbolikami (`EncodeTypes.Code128`, `EncodeTypes.QR`), aby rozszerzyć zakres danych, które możesz zakodować.

Powodzenia w kodowaniu i niech Twoje kody kreskowe zawsze skanują się za pierwszym razem!

## Co powinieneś nauczyć się dalej?

Następujące samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować i regulować wysokość kodu kreskowego dla jednowymiarowego Databar przy użyciu Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generować kody kreskowe – jednowymiarowe typy kodów](/barcode/english/net/one-dimensional-barcode-types/)
- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}