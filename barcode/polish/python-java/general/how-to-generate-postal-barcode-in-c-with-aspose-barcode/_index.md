---
category: general
date: 2026-08-19
description: Dowiedz się, jak generować kod kreskowy pocztowy w C# przy użyciu Aspere.BarCode.
  Ten przewodnik krok po kroku pokazuje, jak generować kod kreskowy w formatach Planet
  i RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: pl
lastmod: 2026-08-19
og_description: Wygeneruj kod kreskowy pocztowy w C# przy użyciu Aspose.BarCode. Przejdź
  do tego przewodnika, aby dowiedzieć się, jak generować kod kreskowy dla Planet i
  RM4SCC o niestandardowych wymiarach.
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: Generowanie kodu kreskowego pocztowego w C# – kompletny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: Jak wygenerować kod kreskowy pocztowy w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generować kod kreskowy pocztowy w C# z Aspose.BarCode

Jeśli potrzebujesz **generować kod kreskowy pocztowy** dla aplikacji pocztowych, ten przewodnik pokaże Ci dokładnie, jak wygenerować kod kreskowy przy użyciu biblioteki Aspose.BarCode. Zobaczysz kompletny, gotowy do uruchomienia przykład, który tworzy zarówno kod Planet (wysokość obliczana automatycznie), jak i kod RM4SCC z określoną wysokością kreski.

Generowanie kodu kreskowego pocztowego jest powszechnym wymogiem dla oprogramowania logistycznego, automatycznych drukarek etykiet oraz systemów masowej wysyłki. Po zakończeniu tego tutorialu będziesz w stanie zintegrować generowanie kodów kreskowych z dowolnym projektem .NET, dostosować wymiar X‑dimension oraz kontrolować wysokość kreski, gdy standardowy format na to pozwala.

**Czego się nauczysz**

* Jak skonfigurować Aspose.BarCode w projekcie C#.  
* Jak generować kody kreskowe pocztowe Planet i RM4SCC.  
* Jak regulować X‑dimension (szerokość modułu) i wysokość kreski.  
* Jak zapisać wynik jako obraz PNG.  

Żadne zewnętrzne usługi nie są wymagane — wszystko działa lokalnie po dodaniu pakietu Aspose.BarCode z NuGet.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy (kod działa również z .NET Framework 4.7+).  
* Visual Studio 2022, Visual Studio Code lub dowolne IDE dla C#, które preferujesz.  
* Pakiet Aspose.BarCode for .NET – zainstaluj go poprzez NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Generowanie kodu kreskowego pocztowego z Aspose.BarCode

Poniższe sekcje przeprowadzą Cię krok po kroku, od tworzenia obiektów generatora po zapisanie finalnych plików PNG.

### Krok 1: Utwórz kod Planet (automatyczna wysokość)

Planet to kod kreskowy używany w wielu krajach do sortowania poczty. Gdy tworzysz kod Planet, biblioteka automatycznie określa optymalną wysokość kreski na podstawie zakodowanych danych.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**Dlaczego to działa** – `EncodeTypes.Planet` informuje Aspose.BarCode, aby użył symboliki Planet. Właściwość `XDimension` kontroluje szerokość najmniejszej kreski (modułu). Ponieważ Planet nie wymaga stałej wysokości kreski, biblioteka automatycznie oblicza odpowiednią wysokość, co upraszcza kod.

### Krok 2: Utwórz kod RM4SCC z określoną wysokością

RM4SCC to kolejna symbolika pocztowa, która często wymaga konkretnej wysokości kreski dla kompatybilności ze skanerami. Poniższy kod pokazuje, jak ustawić tę wysokość ręcznie.

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Dlaczego ustawiasz wysokość** – Niektóre skanery pocztowe wymagają minimalnej wysokości kreski. Przypisując `BarHeight.Pixels = 100`, zapewniasz, że wygenerowany obraz spełnia te wymagania. Wymiar X‑dimension pozostaje spójny z kodem Planet, dzięki czemu oba obrazy mają taką samą gęstość wizualną.

### Krok 3: Zweryfikuj wynik

Po uruchomieniu programu otwórz dwa pliki PNG znajdujące się w `YOUR_DIRECTORY`. Powinny się tam znajdować dwa odrębne kody kreskowe:

* `PostalPlanetBarHeightNone.png` – kod Planet z automatycznie obliczoną wysokością.  
* `PostalRM4SCCBarHeight100Pixels.png` – kod RM4SCC z wysokością kreski równą 100 pikseli.

Oba obrazy mogą być bezpośrednio podawane drukarkom etykiet lub wyświetlane w aplikacji internetowej.

![Generated postal barcode image using Aspose.BarCode](generated-postal-barcode.png)

*Tekst alternatywny obrazu:* **Wygenerowany kod kreskowy pocztowy** przy użyciu Aspose.BarCode (prezentuje, jak generować kod kreskowy pocztowy).

## Jak generować kod kreskowy z własnymi wymiarami (zaawansowane)

Jeśli potrzebujesz precyzyjnie dostroić inne parametry — takie jak marginesy, położenie tekstu czy kolor — Aspose.BarCode udostępnia rozbudowany obiekt `Parameters`. Poniżej szybki przykład, który dodaje białe tło i wyłącza tekst czytelny dla człowieka.

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**Kiedy to stosować** – Wyłączanie tekstu czytelnego dla człowieka jest typowe w automatycznym sortowaniu, gdzie liczy się wyłącznie wzór maszynowo odczytywalny. Ustawienie koloru tła zapewnia prawidłowy wydruk kodu na przezroczystym podłożu.

## Typowe pułapki i wskazówki ekspertów

| Problem | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Kod kreskowy wygląda na rozciągnięty | X‑dimension jest zbyt duża w stosunku do rozmiaru obrazu | Trzymaj `XDimension.Pixels` w przedziale 2‑5 dla większości kodów pocztowych |
| Skaner odrzuca obraz | Wysokość kreski jest poniżej minimalnego wymogu usługi pocztowej | Użyj `BarHeight.Pixels` ≥ 80 dla RM4SCC, chyba że specyfikacja mówi inaczej |
| Rozmiar pliku PNG jest duży | Rozdzielczość obrazu jest wyższa niż potrzebna | Zapisz jako PNG‑8 (`BarCodeImageFormat.Png8`) lub zmniejsz wymiary w pikselach |

**Wskazówka eksperta:** Zawsze testuj wygenerowany kod kreskowy na rzeczywistym skanerze przed wdrożeniem do produkcji. Małe różnice wizualne mogą wpływać na czytelność.

## Pełny kod źródłowy

Skopiuj cały blok poniżej do nowej aplikacji konsolowej (`Program.cs`). Dostosuj ścieżki wyjściowe do folderu, w którym proces ma prawo zapisu.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

Uruchomienie programu wypisze *„Barcodes generated successfully.”* i utworzy dwa pliki PNG w katalogu roboczym wykonywalnego pliku.

## Podsumowanie

Teraz wiesz, jak **generować kod kreskowy pocztowy** w C# z Aspose.BarCode, obejmując zarówno kody Planet o automatycznej wysokości, jak i kody RM4SCC o stałej wysokości. Przewodnik pokazał także, **jak generować kod kreskowy** z własnym X‑dimension, wysokością kreski i opcjami wizualnymi, zapewniając solidną bazę dla każdego projektu automatyzacji wysyłek.

Kolejne kroki, które możesz rozważyć:

* Zintegruj wygenerowane PNG z fakturą PDF przy użyciu Aspose.PDF.  
* Przełącz format wyjściowy na SVG, aby uzyskać skalowalną grafikę wektorową.  
* Użyj klasy `BarcodeReader`, aby programowo zweryfikować zakodowane dane.

Śmiało eksperymentuj z różnymi symbolikami (np. `EncodeTypes.Postnet`) i dziel się wynikami ze społecznością. Powodzenia w kodowaniu!


## Co powinieneś nauczyć się dalej?


Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}