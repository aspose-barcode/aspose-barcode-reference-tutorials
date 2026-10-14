---
category: general
date: 2026-10-05
description: Utwórz plik PNG z kodem kreskowym w C# i dowiedz się, jak ustawić współczynnik
  proporcji 15 dla warstwowych kodów DataBar omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: pl
lastmod: 2026-10-05
og_description: Utwórz kod kreskowy PNG w C# i dowiedz się, jak ustawić współczynnik
  proporcji 15 dla składanych kodów DataBar omnidirectional w kilku krokach.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Tworzenie kodu kreskowego PNG w C# – ustaw współczynnik proporcji 15 – poradnik
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak utworzyć plik PNG z kodem kreskowym o niestandardowym współczynniku proporcji
  w C#
url: /pl/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć plik PNG z kodem kreskowym o niestandardowym współczynniku proporcji w C#

Jeśli potrzebujesz **utworzyć plik PNG z kodem kreskowym** w C#, ten przewodnik pokaże Ci **jak ustawić współczynnik proporcji** 15 dla stosowanego kodu DataBar omnidirectional. Przejdziemy przez każde wywołanie API, wyjaśnimy, dlaczego współczynnik proporcji ma znaczenie, i dostarczymy kompletny, gotowy do uruchomienia przykład, który możesz wkleić do dowolnego projektu .NET.

Generowanie obrazu kodu kreskowego jest powszechnym wymogiem w systemach inwentaryzacji, etykietach wysyłkowych i aplikacjach detalicznych punktu sprzedaży. Po zakończeniu tego samouczka będziesz mieć plik PNG spełniający dokładne specyfikacje wizualne wymagane przez Twojego partnera biznesowego. Bez zewnętrznych narzędzi, bez ręcznej edycji obrazu — tylko kod.

## Wymagania wstępne

* .NET 6.0 lub nowszy (przykład używa .NET 6, ale działa z .NET 5+)
* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)
* Pakiet NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Uprawnienia do zapisu w folderze, w którym chcesz zapisać plik PNG

Te wymagania są minimalne; ten sam kod działa w .NET Core, .NET Framework lub aplikacji konsolowej.

## Utwórz plik PNG z kodem kreskowym przy użyciu Aspose.BarCode

Pierwszym krokiem jest utworzenie instancji klasy `BarcodeGenerator` z odpowiednim typem kodu kreskowego. W tym przypadku używamy `EncodeTypes.DatabarStackedOmniDirectional`, który generuje stosowany DataBar, który może być odczytany z dowolnego kierunku.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Dlaczego to ważne:* Konstruktor przyjmuje dwa argumenty — **symbologię kodu kreskowego** i **ciąg danych**. Format DataBar wymaga identyfikatora aplikacji GS1, dlatego przykładowe dane zaczynają się od `(01)`.

## Jak ustawić współczynnik proporcji dla stosowanego DataBar

Widzialna szerokość DataBar jest kontrolowana przez właściwość **aspect ratio**. Wyższy współczynnik powoduje szersze paski, co może poprawić niezawodność skanowania na drukarkach o niskiej rozdzielczości.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` definiuje rozmiar pojedynczego modułu (najmniejszego paska lub przerwy). Utrzymanie tej wartości na poziomie 2 px zapewnia wyraźny, wysokiej gęstości obraz odpowiedni dla większości drukarek etykiet.

## Ustaw współczynnik proporcji 15 — przegląd kodu

Teraz stosujemy wymóg **set aspect ratio 15**. To jest sedno samouczka i pokazuje dokładne wywołanie API, którego potrzebujesz.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Dlaczego 15?* Domyślny współczynnik proporcji dla stosowanego DataBar wynosi 12. Podniesienie go do 15 zwiększa szerokość każdego paska o 25 %, co często odpowiada specyfikacjom dostawców logistycznych, które wymagają szerszego kodu kreskowego dla szybszego skanowania.

## Zapisz kod kreskowy jako PNG

Po skonfigurowaniu generatora, ostatnim krokiem jest zapisanie obrazu na dysku. Metoda `Save` przyjmuje ścieżkę pliku oraz enum formatu obrazu.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Format PNG zachowuje jakość bezstratną, zapewniając, że kod kreskowy jest renderowany dokładnie tak, jak zaprojektowano, na każdym wyświetlaczu lub drukarce.

## Pełny przykład i oczekiwany wynik

Poniżej znajduje się pełny program, który możesz skopiować do metody `Main` aplikacji konsolowej. Zawiera wszystkie opisane powyżej kroki oraz krótką wiadomość weryfikacyjną.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu tworzy plik o nazwie `DatabarAspectRatio15.png` zawierający wyraźny, szeroki stosowany kod DataBar. Po otwarciu pliku PNG powinieneś zobaczyć poziomo rozciągnięty kod kreskowy, który nadal spełnia specyfikacje GS1 DataBar.

![PNG kodu kreskowego z współczynnikiem proporcji 15](barcode-aspect15.png)

*Tekst alternatywny obrazu:* **utwórz PNG kodu kreskowego pokazującego stosowany DataBar z współczynnikiem proporcji 15**

### Wskazówki i typowe pułapki

| Sytuacja | Zalecenie |
|-----------|----------------|
| **Obraz jest rozmyty** | Zwiększ `XDimension.Pixels` do 3 px lub wyżej, ale utrzymaj całkowity rozmiar obrazu poniżej 500 px, aby uniknąć zbyt dużych plików. |
| **Skaner nie może odczytać kodu** | Sprawdź, czy ciąg danych spełnia format GS1 (prefiks `(01)`). Upewnij się również, że rozdzielczość drukarki wynosi co najmniej 300 dpi. |
| **Potrzebny inny format pliku** | Zastąp `BarCodeImageFormat.Png` przez `Jpeg`, `Bmp` lub `Gif` — API obsługuje wszystkie popularne formaty rastrowe. |
| **Uruchamianie w aplikacji webowej** | Użyj `generator.Save(Stream, BarCodeImageFormat.Png)`, aby zapisać bezpośrednio do odpowiedzi HTTP bez korzystania z systemu plików. |

### Rozszerzanie przykładu

* **Wiele kodów kreskowych w jednym obrazie:** Utwórz dodatkowe instancje `BarcodeGenerator` i narysuj je na jednym `Bitmap` przy użyciu `Graphics`.  
* **Dodawanie tekstu czytelnego dla człowieka:** Ustaw `generator.Parameters.Caption.Visible = true` i dostosuj czcionkę za pomocą `generator.Parameters.Caption.Font`.  
* **Dynamiczny współczynnik proporcji:** Pobierz wartość współczynnika z pliku konfiguracyjnego lub bazy danych, aby generować kody kreskowe o zmiennych szerokościach w locie.

## Zakończenie

W tym samouczku nauczyłeś się, jak **utworzyć plik PNG z kodem kreskowym** w C# i precyzyjnie **ustawić współczynnik proporcji** 15 dla stosowanego kodu DataBar omnidirectional. Kompletny, gotowy do uruchomienia kod demonstruje każde wymagane wywołanie API, wyjaśnia, dlaczego każde ustawienie ma znaczenie, i dostarcza praktyczne wskazówki do wdrożeń w rzeczywistych warunkach.  

Następnie możesz zbadać **jak ustawić współczynnik proporcji** dla innych typów kodów kreskowych (np. QR Code lub Code 128) lub zintegrować generator z usługą ASP .NET Core, która zwraca obrazy kodów kreskowych na żądanie. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć obrazy PNG databar w C# i Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Jak utworzyć stosowany kod databar w C# z Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Dostosuj stosowany omnidirectional Aspect Ratio dla databar w .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}