---
category: general
date: 2026-11-20
description: Szybko utwórz obraz kodu pocztowego w C#. Dowiedz się, jak generować
  kody Planet i RM4SCC z konfigurowalnymi stylami pasków.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: pl
lastmod: 2026-11-20
og_description: Utwórz obraz kodu pocztowego w C# przy użyciu Aspose.BarCode. Ten
  samouczek pokazuje, jak wygenerować kod Planet, dostosować style pasków oraz tworzyć
  obrazy RM4SCC.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Tworzenie obrazu kodu pocztowego w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Utwórz obraz kodu kreskowego pocztowego i wygeneruj kod kreskowy planety
url: /pl/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego pocztowego i wygeneruj kod Planet

Utwórz obraz kodu kreskowego pocztowego w C# przy użyciu biblioteki Aspose.BarCode. Jeśli potrzebujesz generować kod Planet lub kody kreskowe RM4SCC do zastosowań pocztowych, ten samouczek zapewnia kompletną, gotową do uruchomienia rozwiązanie.

Generowanie kodów kreskowych dla usług pocztowych często wymaga precyzyjnych wymiarów oraz możliwości przełączania między stylami wypełnionych i pustych pasków. Ten przewodnik krok po kroku pokaże, jak skonfigurować folder wyjściowy, utworzyć zarówno wypełnione, jak i puste kody Planet oraz wygenerować kod RM4SCC z takimi samymi ustawieniami wizualnymi. Po zakończeniu będziesz mieć cztery pliki PNG, które możesz od razu wykorzystać w swoim procesie wysyłkowym.

## Wymagania wstępne

* .NET 6.0 lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE C#, którego używasz)  
* Pakiet NuGet **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Nie wymaga dodatkowej konfiguracji; kod używa wyłącznie domyślnej czcionki i enkodera PNG.

## Tworzenie obrazu kodu kreskowego pocztowego – przegląd

Kluczowym elementem procesu jest klasa `BarcodeGenerator`. Przyjmuje ona wartość `EncodeTypes`, która określa symbologię kodu (np. `EncodeTypes.Planet` dla kodu Planet). Po skonfigurowaniu generatora wywołujesz metodę `Save`, aby zapisać plik obrazu.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Przykład obrazu kodu kreskowego pocztowego pokazujący wypełnione i puste paski.*

## Krok 1: Ustaw folder wyjściowy

Najpierw zdefiniuj folder, w którym będą zapisywane pliki PNG. Użycie ścieżki bezwzględnej lub względnej działa tak samo; po prostu upewnij się, że folder istnieje lub pozwól kodowi go utworzyć.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Programowe tworzenie folderu zapobiega `DirectoryNotFoundException`, gdy samouczek uruchamiany jest na nowej maszynie.

## Krok 2: Wygeneruj kod Planet z wypełnionymi paskami

Kod Planet z wypełnionymi paskami jest domyślnym stylem wizualnym. Poniższy kod tworzy kod, ustawia wymiar X na 4 piksele (typowy rozmiar dla zastosowań pocztowych) i zapisuje obraz.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Dlaczego to działa:**  
* `EncodeTypes.Planet` informuje generator, aby użył symbologii Planet, która jest wymagana przez wiele usług pocztowych.  
* `XDimension.Pixels` kontroluje szerokość każdego paska; 4 px daje wyraźny, skanowalny obraz bez nadmiernego rozmiaru pliku.  
* Metoda `Save` automatycznie wybiera enkoder PNG na podstawie wyliczenia `BarCodeImageFormat`.

## Krok 3: Wygeneruj kod Planet z pustymi paskami

Niektóre specyfikacje pocztowe preferują puste (białe) paski na ciemnym tle. Możesz to osiągnąć, ustawiając `FilledBars` na `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Wskazówka:** Gdy `FilledBars` jest ustawione na `false`, generator rysuje paski w kolorze tła (domyślnie biały) i przestrzenie w kolorze pierwszego planu (czarny). Jeśli potrzebujesz innego schematu kolorów, dostosuj `Parameters.Barcode.ForeColor` i `BackColor`.

## Krok 4: Wygeneruj kod RM4SCC z wypełnionymi paskami

RM4SCC to kolejna symbologia pocztowa używana w Wielkiej Brytanii. Kroki tworzenia są analogiczne do przykładu Planet; jedynie wartość `EncodeTypes` się zmienia.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Czego się spodziewać:** Wynikowy PNG wyświetla kompaktowy kod RM4SCC, który spełnia brytyjskie wytyczne pocztowe. Rozmiar obrazu będzie podobny do kodów Planet, ponieważ wymiar X jest identyczny.

## Krok 5: Zweryfikuj wygenerowane obrazy

Po uruchomieniu programu otwórz cztery pliki w folderze `Barcodes`. Powinieneś zobaczyć:

* `PostalPlanetFilledBars.png` – ciemne paski na jasnym tle  
* `PostalPlanetEmptyBars.png` – jasne paski na ciemnym tle (odwrócone)  
* `PostalRM4SCCFilledBars.png` – standardowy wzór RM4SCC  

Jeśli którykolwiek obraz wygląda na zniekształcony, sprawdź następujące elementy:

* **X‑dimension** – zbyt mały (< 2 px) może powodować rozmycie; zbyt duży (> 10 px) może przekraczać limity rozmiaru etykiety.  
* **Data string** – wartość `"123456"` musi spełniać wymogi długości wybranej symbologii (Planet wymaga dokładnie 6 cyfr, RM4SCC również wymaga 6 cyfr).  
* **Folder permissions** – upewnij się, że aplikacja ma prawo zapisu w katalogu wyjściowym.

## Typowe wariacje i przypadki brzegowe

| Scenariusz | Dostosowanie |
|------------|--------------|
| **Inne dane kodu kreskowego** | Zastąp `"123456"` dowolnym prawidłowym ciągiem numerycznym. Dla Planet długość musi wynosić dokładnie 6 cyfr; RM4SCC również wymaga 6 cyfr. |
| **Niestandardowe kolory** | Ustaw `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` oraz `BackColor = System.Drawing.Color.LightYellow;`. |
| **Wyższa rozdzielczość** | Zwiększ `XDimension.Pixels` do 6 lub 8, aby uzyskać większe wydruki. |
| **Inne formaty obrazu** | Użyj `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp` w wywołaniu `Save`. |
| **Generowanie wsadowe** | Przejdź pętlą po kolekcji ciągów i wywołaj tę samą logikę generatora wewnątrz pętli, ponownie używając ścieżki `outputFolder`. |

## Pełny, działający przykład

Skopiuj poniższy kod do nowego projektu konsolowego C#. Kompiluje się z .NET 6.0 i automatycznie tworzy wszystkie cztery obrazy kodów kreskowych.



## Co warto nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć obraz kodu kreskowego pocztowego z niestandardowymi wysokościami w C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Jak utworzyć kod RM4SCC i wygenerować kod Planet w C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Utwórz obraz kodu kreskowego pocztowego w C# – przewodnik krok po kroku](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}