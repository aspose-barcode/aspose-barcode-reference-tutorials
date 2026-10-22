---
category: general
date: 2026-10-21
description: Szybko utwórz kod kreskowy Databar Stacked przy użyciu C#. Dowiedz się,
  jak ustawić wymiar X, dostosować proporcje i zapisać obrazy PNG w tym kompletnym
  samouczku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: pl
lastmod: 2026-10-21
og_description: Utwórz kod kreskowy Databar stacked w C# z Aspose.BarCode. Postępuj
  zgodnie z tym przewodnikiem, aby skonfigurować wymiar X, zmienić proporcje i wyeksportować
  pliki PNG.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Tworzenie kodu kreskowego Databar Stacked w C# – pełny przewodnik programistyczny
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Jak stworzyć kod kreskowy Databar stacked w C# – przewodnik krok po kroku
url: /pl/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy databar stacked w C# – przewodnik krok po kroku

Jeśli potrzebujesz **create databar stacked barcode** w aplikacji .NET, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Zobaczysz, jak skonfigurować wymiar X, zmienić współczynnik proporcji i zapisać kod kreskowy jako pliki PNG.

Generowanie kodu kreskowego DataBar stacked nie wymaga skomplikowanego potoku budowania. Ten tutorial obejmuje wszystko, czego potrzebujesz: wymagane pakiety, wyjaśnienie kod po kodzie oraz wskazówki dotyczące typowych pułapek. Po zakończeniu będziesz mógł wygenerować wiele obrazów kodów kreskowych o różnych współczynnikach proporcji w jednej metodzie.

## Czego będziesz potrzebować

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE obsługujące C#)  
* **Aspose.BarCode for .NET** pakiet NuGet – biblioteka udostępniająca `BarcodeGenerator` i `EncodeTypes`  

Możesz dodać pakiet przy użyciu następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Skonfiguruj projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy lub dodaj kod do istniejącego. Zaimportuj wymagane przestrzenie nazw, aby kompilator rozpoznawał klasy kodów kreskowych.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Te instrukcje `using` udostępniają `BarcodeGenerator`, `EncodeTypes` oraz `BarCodeImageFormat` używane później w przykładzie.

## Krok 2: Zdefiniuj folder wyjściowy

Wybierz folder, w którym będą zapisywane wygenerowane pliki PNG. Użycie ścieżki bezwzględnej lub względnej działa tak samo; w przykładzie użyto względnego folderu o nazwie `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Tworzenie folderu programowo zapobiega błędom w czasie wykonywania, gdy katalog nie istnieje.

## Krok 3: Zainicjalizuj generator **create databar stacked barcode**

Utwórz instancję `BarcodeGenerator` z `EncodeTypes.DatabarStackedOmniDirectional`. Przykładowe dane `(01)12345678901231` są zgodne z formatem GS1‑128 wymaganym przez DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Obiekt generatora przechowuje wszystkie parametry wpływające na wygląd wizualny kodu kreskowego.

## Krok 4: Ustaw wymiar X (szerokość w pikselach najmniejszego paska)

Wymiar X kontroluje ogólny rozmiar kodu kreskowego bez zmiany zakodowanych danych. Wartość `2` piksele zapewnia wyraźny, możliwy do zeskanowania obraz dla większości rozdzielczości ekranu.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Dostosuj tę wartość, jeśli potrzebujesz większego lub mniejszego kodu kreskowego; zachowaj stały stosunek między szerokością a wysokością.

## Krok 5: Skonfiguruj współczynnik proporcji i zapisz pierwszy obraz

Współczynnik proporcji określa stosunek wysokości do szerokości kodu kreskowego DataBar stacked. Współczynnik `15` jest powszechnym domyślnym ustawieniem, które daje kompaktowy wygląd.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapisuje plik PNG w wcześniej określonym folderze. Nazwa pliku wyraźnie wskazuje użyty współczynnik proporcji.

### Oczekiwany wynik dla współczynnika proporcji 15

Wygenerowany plik `DatabarAspectRatio15.png` wygląda podobnie do poniższej ilustracji.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Tekst alternatywny:* `create databar stacked barcode image saved with aspect ratio 15`

## Krok 6: Zmień współczynnik proporcji i zapisz drugi obraz

Możesz ponownie użyć tej samej instancji `BarcodeGenerator`, aby tworzyć warianty. Zmiana `AspectRatio` na `30` podwaja wysokość każdego stosu pasków, co może być wymagane przy drukowaniu w wysokiej rozdzielczości.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Oczekiwany wynik dla współczynnika proporcji 30

Obraz `DatabarAspectRatio30.png` jest wyższy, zachowując tę samą szerokość, jednocześnie zwiększając czytelność dla skanerów z większej odległości.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Tekst alternatywny:* `create databar stacked barcode image saved with aspect ratio 30`

## Pełny kod źródłowy

Połączenie wszystkich kroków w jedną całość daje samodzielny program, który możesz uruchomić od razu.

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
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Skompiluj i uruchom program. Po wykonaniu w katalogu `Barcodes` znajdą się dwa pliki PNG, każdy reprezentujący **create databar stacked barcode** z innym współczynnikiem proporcji.

## Porady i typowe pułapki

* **Pro tip:** Utrzymuj wymiar X między 1 px a 4 px dla większości zastosowań ekranowych. Większe wartości zwiększają rozmiar pliku bez poprawy niezawodności skanowania.
* **Pitfall:** Zmiana wartości `EncodeTypes` po utworzeniu generatora nie aktualizuje wewnętrznego kodowania. Zawsze podawaj prawidłowy `EncodeTypes` w konstruktorze.
* **Pro tip:** Gdy potrzebujesz więcej niż dwóch współczynników proporcji, iteruj po tablicy wartości całkowitych i wywołuj `Save` w pętli. To zmniejsza duplikację kodu.
* **Pitfall:** Zapisywanie do ścieżki bez uprawnień do zapisu powoduje wyrzucenie `UnauthorizedAccessException`. Upewnij się, że aplikacja działa z odpowiednimi prawami systemu plików.

## Zakończenie

Teraz wiesz, jak **create databar stacked barcode** w C# przy użyciu Aspose.BarCode. Przewodnik obejmował konfigurację środowiska, ustawianie wymiaru X, dostosowywanie współczynnika proporcji oraz zapisywanie plików PNG. Dzięki tej bazie możesz generować dodatkowe warianty, integrować tworzenie kodów kreskowych z interfejsami API webowymi lub osadzać obrazy w raportach PDF.

Następnie, zapoznaj się z powiązanymi tematami, takimi jak najlepsze praktyki skanowania **DataBar Stacked Omnidirectional**, osadzanie kodów kreskowych w odpowiedziach **ASP.NET Core** lub generowanie **QR codes** przy użyciu tej samej biblioteki. Eksperymentuj z różnymi `EncodeTypes` i formatami obrazu, aby dopasować je do potrzeb Twojej aplikacji.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak tworzyć obrazy PNG databar w C# i Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Jak ustawić kolumny dla kodu kreskowego Databar Expanded Stacked – kompletny przewodnik C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode w C# – kompletny przewodnik](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}