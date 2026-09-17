---
date: 2026-06-09
description: Dowiedz się, jak tworzyć kod kreskowy Code128 w Javie przy użyciu Aspose.BarCode.
  Ten przewodnik krok po kroku pokazuje, jak generować kod kreskowy w Javie, ustawiać
  własny tekst, regulować szerokość pasków i zapisywać obraz.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Ustawianie tekstu kodu
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Tworzenie kodu kreskowego Code128 w Javie – Ustawianie tekstu kodu przy użyciu
  Aspose.BarCode
url: /pl/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy Code128 w Javie – Ustaw tekst kodu przy użyciu Aspose.BarCode

W tym samouczku dowiesz się, jak **utworzyć kod kreskowy Code128 w Javie** przy użyciu biblioteki Aspose.BarCode Java. Niezależnie od tego, czy tworzysz system inwentaryzacji, rozwiązanie do śledzenia dokumentów, czy dowolną aplikację wymagającą kodów kreskowych, przeprowadzimy Cię przez każdy krok — od utworzenia kodu kreskowego **Code128** po dostosowanie tekstu kodu i precyzyjne ustawienie szerokości kreski. Na końcu będziesz mieć gotowy obraz, który możesz osadzić w dowolnym miejscu.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.BarCode for Java.  
- **Jaki typ kodu kreskowego jest demonstrowany?** CODE_128.  
- **Jak ustawić własny tekst kodu kreskowego?** Użyj konstruktora `BarcodeGenerator` lub metody `setCodeText`.  
- **Czy mogę zmienić szerokość kreski?** Tak — dostosuj `XDimension` (szerokość kreski) w milimetrach.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna dla wdrożeń nie‑testowych.

## Jak utworzyć kod kreskowy Code128 w Javie?

Załaduj `BarcodeGenerator` z symboliką `CODE_128` oraz żądanym tekstem, ustaw szerokość kreski za pomocą `XDimension`, a następnie wywołaj `save`, aby zapisać plik obrazu. Ten trzyetapowy wzorzec generuje wysokiej jakości kod kreskowy w ciągu kilku sekund i działa na dowolnym środowisku Java 8+, Windows, Linux lub macOS.

## Wymagania wstępne do generowania kodu kreskowego w Javie

- Podstawowa znajomość programowania w Javie.  
- Środowisko programistyczne Java (JDK 8 lub nowszy).  
- Biblioteka Aspose.BarCode for Java – pobierz ją **[tutaj](https://releases.aspose.com/barcode/java/)**.  
- Ulubione IDE (IntelliJ IDEA, Eclipse, itp.).

## Importowanie pakietów

Zaimportuj niezbędne przestrzenie nazw Aspose.BarCode, aby klasy były dostępne w Twoim projekcie.

## Co to jest klasa BarcodeGenerator?

`BarcodeGenerator` jest podstawową klasą Aspose.BarCode, która tworzy obrazy kodów kreskowych w pamięci. Udostępnia płynne API do ustawiania symboliki, tekstu kodu, wymiarów, kolorów oraz dodatkowych opcji renderowania przed wyeksportowaniem wyniku do formatów takich jak PNG, JPEG, SVG czy PDF. Możesz również dostosować podpisy, marginesy i poziomy korekcji błędów według potrzeb.

## Samouczek Generatora Kodów: Utwórz kod kreskowy Code128

### Krok 1: Utwórz instancję `BarcodeGenerator`

Konstruktor `BarcodeGenerator` przyjmuje dwa argumenty: symbolikę kodu kreskowego (`CODE_128`) oraz **własny tekst kodu**, który chcesz zakodować, np. "12345678".

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Krok 2: Dostosuj szerokość kodu kreskowego dla własnego tekstu kodu

Ustaw właściwość `XDimension` (szerokość kreski), aby kontrolować, jak szeroka jest każda kreska. W tym przykładzie używamy `0.5` mm, rozmiaru, który balansuje czytelność i przestrzeń etykiety w większości zastosowań.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Krok 3: Zapisz obraz kodu kreskowego

Wywołaj metodę `save`, podając ścieżkę wyjściową oraz format obrazu (JPEG, PNG, SVG itp.). Przykład zapisuje plik jako **`setCodeText.jpg`** w folderze dokumentów projektu.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Dlaczego używać Aspose.BarCode dla Java?

Aspose.BarCode dla Java oferuje kompleksowy zestaw funkcji, które upraszczają generowanie kodów kreskowych na różnych platformach. Obsługuje ponad sześćdziesiąt symbolik, dostarcza obrazy rastrowe i wektorowe o wysokiej rozdzielczości oraz zapewnia optymalizacje wydajności przy przetwarzaniu wsadowym, co czyni go idealnym rozwiązaniem dla aplikacji klasy korporacyjnej i płynnej integracji z istniejącymi projektami Java.

- **Szerokie wsparcie symbolik** – Ponad **60** typów kodów kreskowych, w tym Code128, QR, DataMatrix i PDF417.  
- **Renderowanie w wysokiej rozdzielczości** – Generuje wyraźne obrazy PNG, JPEG, SVG i PDF o szerokości do **2000 mm** bez utraty jakości.  
- **Skoncentrowane na wydajności** – Przetwarza partię 500 stron kodów kreskowych w mniej niż **2 sekundy** na standardowym sprzęcie serwerowym.  
- **Wieloplatformowość** – Pełna kompatybilność z Windows, Linux i macOS oraz działanie na dowolnym środowisku Java 8+.

## Częste problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Kod kreskowy jest rozmyty** | Zwiększ rozdzielczość obrazu lub wyeksportuj do formatu wektorowego (SVG, PDF). |
| **Tekst jest obcięty** | Powiększ `XDimension` i `BarHeight`, aby zapewnić symbolice wystarczającą przestrzeń. |
| **Licencja nie została zastosowana** | Umieść `Aspose.BarCode.lic` w katalogu głównym projektu i załaduj ją za pomocą `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Najczęściej zadawane pytania

**Q:** *Jaka jest różnica między `CODE_128` a innymi wariantami Code128?*  
**A:** `CODE_128` automatycznie wybiera najbardziej efektywne kodowanie (A, B lub C) w zależności od danych wejściowych, zapewniając optymalną gęstość i szybkość.

**Q:** *Czy mogę zmienić format wyjściowy na PNG zamiast JPEG?*  
**A:** Tak — użyj `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Czy można dodać czytelny dla człowieka podpis pod kodem kreskowym?*  
**A:** Oczywiście. Ustaw `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` i zdefiniuj tekst podpisu za pomocą `setText`.

**Q:** *Czy Aspose.BarCode obsługuje znaki Unicode?*  
**A:** Tak. Dostarcz tekst zakodowany w UTF‑8 i upewnij się, że wybrana symbolika obsługuje dany zestaw znaków.

**Q:** *Jak mogę generować wiele kodów kreskowych w pętli?*  
**A:** Utwórz nową instancję `BarcodeGenerator` wewnątrz pętli, przypisz unikalny tekst dla każdej iteracji i wywołaj `save` z odrębną nazwą pliku.

---

**Ostatnia aktualizacja:** 2026-06-09  
**Testowano z:** Aspose.BarCode 24.12 dla Java  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz kod macierzy danych i ustaw lokalizację tekstu kodu w Javie](/barcode/java/text-and-styling/setting-code-text-location/)
- [Jak ustawić kolor tekstu kodu kreskowego w Javie przy użyciu Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Generuj kod kreskowy w Javie – Ustaw rozdzielczość obrazu przy użyciu Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```