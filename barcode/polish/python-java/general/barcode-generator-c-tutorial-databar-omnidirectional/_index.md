---
category: general
date: 2026-11-14
description: Samouczek generatora kodów kreskowych w C#, który pokazuje, jak tworzyć
  kody DataBar Omnidirectional, ustawiać wymiar X oraz regulować wysokość kreski w
  pikselach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: pl
lastmod: 2026-11-14
og_description: Samouczek generatora kodów kreskowych w C# wyjaśnia krok po kroku,
  jak wygenerować kod kreskowy DataBar Omnidirectional, określić XDimension w pikselach
  oraz zmienić wysokość kreski dla wyjścia PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 'Generator kodów kreskowych C# – samouczek: tworzenie kodów DataBar'
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Generator kodów kreskowych C# – samouczek: DataBar Omnidirectional'
url: /pl/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

Jeśli szukasz **tutorialu generatora kodów kreskowych w C#**, trafiłeś we właściwe miejsce. Ten przewodnik przeprowadzi Cię przez tworzenie kodu DataBar Omnidirectional, konfigurowanie XDimension w pikselach oraz dostosowywanie wysokości pasków, aby uzyskać obrazy PNG.

Zobaczysz kompletny, gotowy do uruchomienia przykład, który obejmuje wszystko – od inicjalizacji generatora po zapisanie wielu obrazów o różnych wysokościach pasków. Nie potrzebujesz dodatkowej dokumentacji – po prostu skopiuj kod, uruchom go i otrzymasz dwa pliki z kodami kreskowymi gotowe do użycia.

## Prerequisites

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 lub nowszy zainstalowany  
* Referencję do biblioteki kodów kreskowych, która udostępnia `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat` (na przykład Aspose.BarCode for .NET)  
* Podstawową znajomość składni C# oraz Visual Studio lub ulubionego IDE  

> **Pro tip:** Jeśli używasz Aspose.BarCode, dodaj pakiet NuGet `Aspose.BarCode` do swojego projektu.

## Barcode generator C# tutorial – step 1: create the generator

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z typem kodowania `DatabarOmniDirectional` oraz danymi, które chcesz zakodować.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Dlaczego to ważne:* `EncodeTypes.DatabarOmniDirectional` instruuje bibliotekę, aby wygenerowała kod, który może być odczytany z dowolnego kierunku, co jest idealne dla opakowań detalicznych i logistyki.

## Set XDimension pixels for the barcode

Wymiar X definiuje szerokość najmniejszego modułu („piksela”) w kodzie kreskowym. Ustawienie go w pikselach daje precyzyjną kontrolę nad gęstością wizualną kodu.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Wyjaśnienie:* Wartość `2` piksele daje kod, który jest wystarczająco ostry dla większości skanerów, a jednocześnie utrzymuje rozmiar pliku w rozsądnych granicach.

## Adjust bar height and save images

Wysokość pasków określa, jak wysokie będą widoczne paski. Możesz generować wiele obrazów o różnych wysokościach, zmieniając właściwość `BarHeight.Pixels` i ponownie wywołując `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Wartość wyliczenia `BarCodeImageFormat.Png` zapewnia, że wynikowy plik jest bezstratnym PNG, co jest zalecanym formatem dla grafiki kodów kreskowych, ponieważ zachowuje dokładne wymiary.

## Change bar height to create multiple images

Często potrzebny jest ten sam kod w różnych rozmiarach – na przykład jeden na małą etykietę, a drugi na duży plakat. Zmień wysokość pasków i użyj tej samej instancji generatora:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Przypadek brzegowy:* Jeśli wysokość pasków jest ustawiona zbyt nisko (np. poniżej 10 px), niektóre skanery mogą mieć trudności z odczytaniem kodu. Zawsze testuj wygenerowane obrazy na docelowym sprzęcie skanującym.

## Full source code

Poniżej znajduje się kompletny program, który możesz skopiować i wkleić do nowego projektu konsolowego. Zawiera wszystkie wymagane dyrektywy `using` oraz demonstrację obu wariantów wysokości pasków.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Uruchom program, zamień `YOUR_DIRECTORY` na prawidłową ścieżkę folderu i znajdziesz dwa pliki PNG:

* `DatabarBarHeight30Pixels.png` – paski o wysokości 30 px  
* `DatabarBarHeight60Pixels.png` – paski o wysokości 60 px  

![tutorial generatora kodów kreskowych C# – wynik](images/databar-example.png "Tutorial generatora kodów kreskowych C# pokazujący dwa obrazy DataBar")

## Common questions

| Question | Answer |
|----------|--------|
| **Czy mogę zmienić format obrazu?** | Tak. Zamień `BarCodeImageFormat.Png` na `Jpeg`, `Bmp` lub `Gif` w zależności od potrzeb. PNG jest preferowane ze względu na jakość bezstratną. |
| **Co zrobić, jeśli potrzebuję innego XDimension?** | Dostosuj `generator.Parameters.Barcode.XDimension.Pixels` do dowolnej liczby całkowitej. Większe wartości zwiększają ogólną szerokość kodu. |
| **Czy DataBar Omnidirectional nadaje się do skanowania mobilnego?** | Tak, pod warunkiem że wydrukowany rozmiar spełnia minimalny rozmiar modułu skanera (zwykle 0,33 mm). XDimension oparty na pikselach pomaga spełnić ten wymóg. |
| **Jak wstawić kod kreskowy do PDF?** | Po zapisaniu PNG użyj biblioteki PDF (np. iTextSharp), aby wstawić obraz na stronę PDF. |

## Conclusion

Ten **tutorial generatora kodów kreskowych w C#** pokazał, jak stworzyć kod DataBar Omnidirectional, ustawić XDimension w pikselach oraz wygenerować pliki PNG o różnych wysokościach pasków. Masz teraz wielokrotnego użytku fragment kodu, który możesz dostosować do dowolnego projektu C# wymagającego tworzenia kodów kreskowych.

### What’s next?

* Poznaj inne `EncodeTypes`, takie jak `Code128` czy `QR`, aby poszerzyć swoją gamę kodów kreskowych.  
* Połącz wygenerowane PNG z biblioteką generującą PDF, aby tworzyć faktury do druku.  
* Eksperymentuj z `generator.Parameters.Barcode.Color`, aby dodać własne kolory, zachowując jednocześnie zgodność ze specyfikacjami skanerów.

Śmiało modyfikuj przykład, wypróbuj dodatkowe wysokości pasków lub zmień format wyjściowy. Powodzenia w kodowaniu!


## What Should You Learn Next?


Poniższe tutoriale obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}