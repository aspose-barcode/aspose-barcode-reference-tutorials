---
category: general
date: 2026-10-18
description: Wygeneruj obraz kodu kreskowego dla symbologii Planet przy użyciu Javy.
  Dowiedz się, jak stworzyć kod kreskowy Planet z niestandardowymi wymiarami kodu
  i pustymi paskami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: pl
lastmod: 2026-10-18
og_description: Generuj obraz kodu kreskowego dla symboliki Planet w Javie. Ten samouczek
  pokazuje, jak stworzyć kod kreskowy Planet z niestandardowymi wymiarami i obrysowymi
  paskami.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Generowanie obrazu kodu kreskowego dla symbologii Planet – przewodnik Java
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Wygeneruj obraz kodu kreskowego dla symboliki Planet w Javie
url: /pl/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie obrazu kodu kreskowego dla symbologii Planet w Javie

Jeśli potrzebujesz **generate barcode image** dla symbologii Planet, ten przewodnik przeprowadzi Cię przez cały proces. Niezależnie od tego, czy budujesz system automatyzacji poczty, czy własne rozwiązanie śledzenia, dowiesz się, jak **create planet barcode** z **custom barcode dimensions** oraz paskami w formie konturu (pustymi).

Przykład używa biblioteki Aspose.BarCode for Java, która zapewnia płynne API dla każdego głównego standardu kodów kreskowych. Nie są wymagane dodatkowe narzędzia do przetwarzania obrazu, a kod działa na dowolnym środowisku Java 8+.

## Wymagania wstępne

* Zainstalowany Java 8 lub nowszy (tutorial został przetestowany z JDK 17).
* Maven lub Gradle do zarządzania zależnościami.
* Podstawowa znajomość składni Java oraz pojęcia kodu kreskowego.

Jeśli jesteś nowy w Mavenie, możesz utworzyć prosty projekt przy użyciu `mvn archetype:generate` i dodać zależność Aspose.BarCode pokazanej poniżej.

## Dodaj zależność Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Pro tip:** Zablokuj numer wersji, aby uniknąć nieoczekiwanych zmian łamiących kompatybilność, gdy biblioteka zostanie zaktualizowana.

## Krok 1: Zainicjalizuj generator kodu kreskowego dla symbologii Planet

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Dlaczego ten krok ma znaczenie:**  
`EncodeTypes.PLANET` informuje bibliotekę, aby użyła specyfikacji kodu kreskowego Planet, który jest powszechnie stosowany w usługach pocztowych. Ciąg danych `"123456"` jest ładunkiem, który pojawi się w wygenerowanym obrazie.

## Krok 2: Ustaw niestandardowe wymiary kodu kreskowego (wymiar X)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Dlaczego ten krok ma znaczenie:**  
Wymiar *X* określa, jak szeroki jest każdy pojedynczy pasek. Ustawiając go na **4 piksele**, otrzymujesz kod kreskowy, który jest łatwo czytelny dla większości skanerów, a jednocześnie mieści się na standardowej etykiecie. Zmiana tej wartości jest podstawowym sposobem uzyskania **custom barcode dimensions**.

## Krok 3: Użyj pustych (konturowych) pasków zamiast pełnych pasków

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Dlaczego ten krok ma znaczenie:**  
`setFilledBars(false)` instruuje renderer, aby rysował tylko kontury pasków, pozostawiając wnętrze przezroczyste. Ten styl jest często wymagany w kodach kreskowych pocztowych, gdzie tło może zawierać inne drukowane informacje.

## Krok 4: Zapisz obraz kodu kreskowego jako PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Dlaczego ten krok ma znaczenie:**  
Wybór `BarCodeImageFormat.Png` zapewnia obraz bezstratny, który zachowuje ostre krawędzie konturowych pasków. Ścieżka pliku może być dowolnym katalogiem, do którego masz prawo zapisu; w przykładzie używany jest folder `output` względem katalogu głównego projektu.

### Oczekiwany wynik

Uruchomienie programu tworzy plik podobny do obrazu poniżej:

![Wygenerowany obraz kodu kreskowego dla symbologii Planet](/images/planet-barcode.png){.align-center alt="Wygenerowany obraz kodu kreskowego pokazujący kod Planet z pustymi paskami konturowymi"}

Obraz wyświetla **Planet barcode** z cienkimi, pustymi paskami, dokładnie odpowiadającymi ustawionym przez Ciebie niestandardowym wymiarom.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Different data length** | Kody Planet obsługują do 12 znaków numerycznych. Zmień drugi argument konstruktora odpowiednio. |
| **Higher resolution** | Zwiększ wymiar X (`setPixels`) lub ustaw `YDimension`, aby kontrolować wysokość pasków. |
| **Color barcode** | Użyj `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);`, aby zmienić kolor pasków. |
| **Saving as SVG** | Zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Svg`, aby uzyskać wyjście wektorowe. |
| **Running on Android** | Użyj wersji Aspose.BarCode dla Androida kompatybilnej z Androidem i zamień ścieżki systemu plików na `Context.getFilesDir()`. |

> **Uwaga:** Ustawienie wymiaru X zbyt nisko (np. 1 piksel) może sprawić, że kod kreskowy będzie nieczytelny na drukarkach o niskiej rozdzielczości. Zawsze testuj na prawdziwym skanerze po zmianie wymiarów.

## Pełny kod źródłowy do szybkiego kopiowania

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Skopiuj kod do pliku o nazwie `PlanetBarcodeDemo.java`, umieść go w `src/main/java/com/example/barcode/`, uruchom `mvn compile exec:java`, a zobaczysz wynik **generate barcode image** w folderze `output`.

## Zakończenie

Teraz wiesz, jak **generate barcode image** dla symbologii Planet w Javie, jak **create planet barcode** z **custom barcode dimensions**, oraz jak przełączyć się z pełnych pasków na puste, aby uzyskać czystszy wygląd. Pełny przykład demonstruje każde wymagane wywołanie API, od inicjalizacji generatora po zapis pliku PNG.

**Kolejne kroki** – przeglądaj inne typy kodów kreskowych (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) i eksperymentuj z dodatkowymi opcjami obrazu, takimi jak kolor tła, marginesy i ustawienia DPI. Jeśli potrzebujesz osadzić kod kreskowy w PDF, połącz ten kod z Aspose.PDF for Java, aby uzyskać płynne rozwiązanie end‑to‑end.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i zbadać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak stworzyć kod Planet z wypełnionymi i pustymi paskami](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [utwórz obraz kodu Planet – przewodnik krok po kroku](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Jak generować kod kreskowy w Javie: Utwórz dokładny obraz kodu kreskowego](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}