---
category: general
date: 2026-09-26
description: Dowiedz się, jak tworzyć kod kreskowy w C# przy użyciu Aspose.BarCode.
  Ten przewodnik krok po kroku zawiera przykład generatora kodów kreskowych i pokazuje,
  jak dostosować wysokość pasków.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: pl
lastmod: 2026-09-26
og_description: Tworzenie kodu kreskowego w C# przy użyciu Aspose.BarCode. Postępuj
  zgodnie z tym przewodnikiem, aby wygenerować kod kreskowy, dostosować wysokość pasków
  i zapisać obrazy PNG.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Utwórz kod kreskowy w C# z Aspose.BarCode – pełny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak utworzyć kod kreskowy w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć kod kreskowy w C# z Aspose.BarCode  

Jeśli potrzebujesz szybko **tworzyć kod kreskowy c#** w projektach, Aspose.BarCode udostępnia płynne API, które zajmuje się ciężką pracą. W tym samouczku zobaczysz kompletny **przykład generatora kodów kreskowych**, dowiesz się **jak dostosować wysokość pasków** i wyeksportujesz wynik jako pliki PNG.  

Niezależnie od tego, czy budujesz system kasowy w handlu detalicznym, generujesz etykiety inwentaryzacyjne, czy automatyzujesz etykiety wysyłkowe, możliwość programowego zmieniania wizualnego rozmiaru kodu kreskowego jest niezbędna. Ten przewodnik zakłada, że masz podstawową wiedzę o C# oraz środowisko programistyczne, takie jak Visual Studio 2022.  

## Wymagania wstępne  

Zanim rozpoczniesz, upewnij się, że masz:  

* .NET 6.0 SDK lub nowszy zainstalowany.  
* Visual Studio 2022 (lub dowolne IDE C#).  
* Aktywną licencję Aspose.BarCode (bezpłatna wersja próbna wystarczy do nauki).  

Będziesz także musiał dodać pakiet NuGet Aspose.BarCode do swojego projektu:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Jeśli planujesz generować wiele kodów kreskowych w pętli, użyj jednej instancji `BarcodeGenerator` i modyfikuj tylko zmieniające się parametry. To zmniejsza alokacje pamięci i poprawia wydajność.

## Jak tworzyć kod kreskowy w C# z Aspose.BarCode  

Poniższe sekcje przeprowadzają krok po kroku przez **przykład generatora kodów kreskowych**. Kod jest samodzielny; skopiuj go do nowej aplikacji konsolowej i uruchom.  

### Krok 1: Importuj wymagane przestrzenie nazw  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te przestrzenie nazw dają dostęp do klasy `BarcodeGenerator` oraz wyliczenia `EncodeTypes`.  

### Krok 2: Zainicjalizuj generator kodu kreskowego  

Wygenerujemy symbol **Databar Omni‑Directional**, który koduje wartość GTIN‑14. Konstruktor przyjmuje symbologię i surowy ciąg danych.  

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Wartość `EncodeTypes.DatabarOmniDirectional` informuje Aspose.BarCode, którego standardu kodu kreskowego użyć. Ciąg danych jest zgodny z formatem identyfikatora aplikacji GS1, powszechnym w kodach kreskowych detalicznych.  

### Krok 3: Ustaw wspólne parametry kodu kreskowego  

Dwa parametry wizualne są najczęściej regulowane: wymiar X (szerokość wąskiego paska) oraz ogólna wysokość paska.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Wymiar X** kontroluje gęstość kodu, natomiast **BarHeight** określa pionowy rozmiar każdego paska. Dostosowanie **BarHeight** to dokładnie to, czego potrzebujesz, gdy chcesz **zmienić wysokość kodu kreskowego** dla różnych mediów drukowanych.  

### Krok 4: Zapisz pierwszy obraz (wysokość 30 pikseli)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapisuje wyrenderowany obraz na dysku. Nazwa pliku wyraźnie wskazuje używaną wysokość, co ułatwia porównywanie różnych wyników.  

### Krok 5: Zmień wysokość pasków na 60 pikseli  

Teraz demonstrujemy **jak dostosować wysokość paska** w czasie wykonywania. Ta sama instancja `generator` jest ponownie używana; zmienia się tylko właściwość `BarHeight`.  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Ponieważ generator zachowuje wszystkie pozostałe ustawienia (symbologia, dane, wymiar X), jedyną wizualną różnicą między dwoma plikami PNG jest pionowy rozmiar pasków.  

### Pełny kod źródłowy  

Po połączeniu wszystkiego razem otrzymujemy zwięzły, działający program:  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Oczekiwany wynik**  

Uruchomienie programu tworzy dwa pliki PNG w katalogu roboczym wykonywalnego pliku:

* `DatabarBarHeight30Pixels.png` – kod kreskowy z wysokością paska 30 px.  
* `DatabarBarHeight60Pixels.png` – ten sam kod, ale każdy pasek jest dwa razy wyższy.

Otwórz obrazy w dowolnym przeglądarce; zobaczysz, że ogólny wzór pozostaje identyczny, podczas gdy wymiar pionowy się zmienia, co potwierdza, że operacja **zmiany wysokości kodu kreskowego** zakończyła się sukcesem.  

## Zaawansowane warianty  

### Przełączanie na inną symbologię  

Jeśli potrzebujesz kodu QR zamiast Databar, zamień wartość `EncodeTypes`:  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Wszystkie pozostałe ustawienia parametrów (X‑dimension, BarHeight) nadal obowiązują tam, gdzie mają sens.  

### Używanie `BarHeight` w milimetrach  

Aspose.BarCode obsługuje także jednostki fizyczne. Aby ustawić wysokość 10 mm:  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

Jest to przydatne, gdy generujesz kody kreskowe do układów drukowanych wymagających dokładnych wymiarów.  

### Obsługa błędów  

Jeśli ciąg danych nie jest zgodny z wybraną symbologią, `BarcodeGenerator` zgłasza `ArgumentException`. Owiń logikę generowania w blok try‑catch, aby wyświetlić przyjazny komunikat:  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Najczęściej zadawane pytania  

* **Czy zmiana BarHeight wpływa na możliwość skanowania?**  
  Kod pozostaje skanowalny, o ile wymiar X i ogólna strefa ciszy spełniają specyfikacje symbologii. Zwiększenie wysokości wydłuża jedynie paski; nie zmniejsza kontrastu.  

* **Czy mogę ustawić różne wysokości dla poszczególnych pasków?**  
  Nie. Właściwość `BarHeight` ma zastosowanie jednolicie do całego symbolu. Dla projektów o zmiennej wysokości potrzebny byłby własny mechanizm renderowania, wykraczający poza zakres Aspose.BarCode.  

* **Czy PNG jest najlepszym formatem do druku?**  
  PNG zachowuje bezstratne dane pikseli, co czyni go idealnym do wyświetlania na ekranie. Do wysokiej rozdzielczości zadań drukarskich rozważ `BarCodeImageFormat.Tiff` lub `Pdf`, aby zachować informacje wektorowe.  

## Zakończenie  

Teraz wiesz, jak **tworzyć aplikacje barcode c#** z Aspose.BarCode, widziałeś kompletny **przykład generatora kodów kreskowych** i rozumiesz **jak dostosować wysokość paska**, aby spełnić różne wymagania układu. Ponowne użycie tej samej instancji generatora i jedynie modyfikowanie `BarHeight` pozwala efektywnie **zmienić wysokość kodu kreskowego** bez konieczności odtwarzania całego obiektu.  

Od tego momentu możesz eksplorować:

* Generowanie innych symbologii (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Eksport do SVG lub PDF w celu uzyskania grafiki skalowalnej.  
* Osadzanie kodów kreskowych bezpośrednio w dokumentach Word lub Excel przy użyciu Aspose.Words lub Aspose.Cells.  

Miłego kodowania i ciesz się elastycznością, jaką Aspose.BarCode wnosi do Twoich projektów kodów kreskowych w C#!  

## Co warto poznać dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}