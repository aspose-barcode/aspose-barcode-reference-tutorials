---
date: 2026-04-12
description: Dowiedz się, jak tworzyć kod kreskowy Code128 z pustymi paskami w Javie
  przy użyciu Aspose.BarCode. Ten przewodnik pokazuje, jak szybko generować obrazy
  kodów kreskowych w Javie.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Generowanie kodu kreskowego z pustymi paskami
second_title: Aspose.BarCode Java API
title: Jak utworzyć kod kreskowy Code128 z pustymi paskami w Javie
url: /pl/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy Code128 z pustymi paskami w Javie

## Wprowadzenie

Integracja generowania kodów kreskowych w aplikacjach Java jest częstym wymaganiem, niezależnie od tego, czy tworzysz systemy inwentaryzacji, platformy biletowe czy rozwiązania punktu sprzedaży. Dzięki **Aspose.BarCode for Java** możesz **tworzyć obrazy kodów Code128** w zaledwie kilku linijkach kodu. W tym samouczku przeprowadzimy Cię krok po kroku przez proces **generowania obrazów kodów Java**, które zawierają puste (nie wypełnione) paski, dając pełną kontrolę nad stylem wizualnym kodu.

## Szybkie odpowiedzi
- **Która biblioteka?** Aspose.BarCode for Java  
- **Główny przypadek użycia?** Tworzenie kodów Code128 z pustymi paskami dla niestandardowych projektów UI  
- **Wymagania wstępne?** Java JDK 8+, Aspose.BarCode JAR, dostęp do zapisu w folderze dla obrazu wyjściowego  
- **Typowy czas implementacji?** 5‑10 minut dla podstawowego przykładu  
- **Czy mogę dostosować kolory?** Tak – API zapewnia rozbudowane opcje stylizacji  

## Co to jest kod kreskowy Code128?

Code128 to wysokiej gęstości liniowy symbolog kodu kreskowego, który koduje pełny zestaw znaków ASCII. Jest szeroko stosowany w logistyce, wysyłce i handlu detalicznym, ponieważ może zwarto reprezentować dane alfanumeryczne. Domyślnie Aspose.BarCode renderuje paski Code128 jako solidne prostokąty; ustawienie właściwości **FilledBars** na `false` zamienia je w puste (konturowe) paski, co jest przydatne przy stylizacji marki.

## Dlaczego używać Aspose.BarCode for Java?

- **Bogaty zestaw funkcji** – obsługuje ponad 50 typów kodów, w tym QR, DataMatrix i PDF417.  
- **Brak zewnętrznych zależności** – pojedynczy JAR działa na dowolnym środowisku Java.  
- **Precyzyjna kontrola** – możesz regulować szerokość pasków, kolory, czcionki oraz właściwość `FilledBars`.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS bez bibliotek natywnych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

1. **Środowisko programistyczne Java** – zainstalowany JDK 8 lub nowszy oraz skonfigurowane `JAVA_HOME`.  
2. **Aspose.BarCode for Java** – pobierz najnowszy JAR ze [strony pobierania](https://releases.aspose.com/barcode/java/).  
3. **Katalog dokumentów** – folder na komputerze, w którym zostanie zapisany wygenerowany obraz kodu kreskowego.

## Importowanie pakietów

W swoim projekcie Java zaimportuj klasy potrzebne do pracy z Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Te importy dają dostęp do generatora kodów, wyliczenia formatów obrazu oraz obsługi wyjątków.

## Krok 1: Skonfiguruj katalog zasobów

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` pełną ścieżką do folderu utworzonego w wymaganiach wstępnych. To miejsce, w którym zostanie zapisany plik PNG.

## Krok 2: Utwórz instancję generatora kodu kreskowego Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Tutaj tworzymy `BarcodeGenerator` z symbologią **CODE_128** oraz przykładowym tekstem `"TEXT"`. To **przykład generatora kodu kreskowego Java**, który możesz dostosować do dowolnego ciągu znaków do zakodowania.

## Krok 3: Ustaw właściwość FilledBars na false

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Ustawiając `FilledBars` na `false`, wygenerowany kod kreskowy wyświetli puste paski zamiast pełnych, uzyskując pożądany efekt wizualny.

## Krok 4: Zapisz obraz kodu kreskowego

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Metoda `save` zapisuje kod kreskowy w określonym katalogu w formacie PNG. Możesz zmienić `BarCodeImageFormat.PNG` na `JPG`, `BMP` lub `TIFF`, jeśli potrzebny jest inny typ obrazu.

## Typowe przypadki użycia

- **Niestandardowa identyfikacja wizualna** – puste paski mogą być nakładane na wzory tła lub kolory.  
- **Materiały gotowe do druku** – generuj obrazy PNG wysokiej rozdzielczości do faktur lub etykiet wysyłkowych.  
- **Dynamiczne generowanie** – twórz kody kreskowe w locie w usługach internetowych lub aplikacjach desktopowych.

## Wskazówki rozwiązywania problemów

- **Nieprawidłowa ścieżka** – upewnij się, że `dataDir` kończy się separatorem plików (`/` lub `\\`) lub łącz ją przy użyciu `File.separator`.  
- **Wymagana licencja** – wersja próbna działa w ocenie, ale pełna licencja jest potrzebna w produkcji.  
- **Nieobsługiwane znaki** – Code128 obsługuje pełny zestaw ASCII; unikaj znaków Unicode, chyba że przełączysz się na inną symbologię.

## Podsumowanie

Teraz wiesz, jak **tworzyć obrazy kodów Code128** z pustymi paskami przy użyciu Aspose.BarCode for Java. To proste podejście pozwala szybko generować konfigurowalne grafiki kodów kreskowych, niezależnie od tego, czy budujesz narzędzie do inwentaryzacji na pulpicie, czy chmurowe API.

## Najczęściej zadawane pytania

### Czy Aspose.BarCode jest kompatybilny ze wszystkimi środowiskami programistycznymi Java?
Tak, Aspose.BarCode został zaprojektowany tak, aby bezproblemowo integrować się z dowolnym IDE lub systemem budowania Java, w tym Maven, Gradle i projektami opartymi na zwykłych JAR-ach.

### Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?
Oczywiście! Oprócz `FilledBars` możesz modyfikować kolory, szerokość pasków, marginesy oraz dodawać tekst czytelny dla człowieka, korzystając z rozbudowanego API.

### Czy dostępna jest wersja próbna Aspose.BarCode?
Tak, możesz wypróbować możliwości Aspose.BarCode, uzyskując darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie dla Aspose.BarCode?
W razie pytań lub potrzebnej pomocy odwiedź [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Gdzie mogę znaleźć szczegółową dokumentację Aspose.BarCode?
Kompleksowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/barcode/java/).

**Dodatkowe pytania**

**Q: Jak wygenerować obraz kodu kreskowego w innym formacie, np. JPEG?**  
A: Zmień drugi argument metody `save` na `BarCodeImageFormat.JPEG`.

**Q: Czy mogę generować wiele kodów kreskowych w pętli?**  
A: Tak – utwórz nową instancję `BarcodeGenerator` wewnątrz pętli lub ponownie użyj tej samej instancji z nowym `CodeText`.

---

**Ostatnia aktualizacja:** 2026-04-12  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}