---
date: 2026-08-28
description: Dowiedz się, jak tworzyć obrazy barcode w Javie przy użyciu Aspose Barcode
  Java, ustawiać symbole start i stop CODABAR oraz generować pliki PNG bez znaków
  wodnych.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Ustawianie symboli start i stop
og_description: Tworzenie obrazu barcode w Javie przy użyciu Aspose Barcode Java.
  Ten przewodnik pokazuje, jak ustawić symbole start/stop CODABAR i eksportować pliki
  PNG bez znaków wodnych.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Tworzenie obrazu barcode w Javie – przewodnik po symbolach start/stop
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Tworzenie obrazu barcode z symbolami start/stop
url: /pl/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Tworzenie obrazu kodu kreskowego z symbolami start/stop

## Wprowadzenie

W tym obszernej samouczku **tworzyć obraz kodu kreskowego w Javie** pliki z Aspose Barcode Java i nauczyć się **jak ustawić symbole start i stop** dla kodów kreskowych CODABAR. Niezależnie od tego, czy budujesz terminal punktu sprzedaży, system zarządzania magazynem, czy dowolną aplikację wymagającą niezawodnego generowania kodów kreskowych, dostosowanie tych symboli pozwala spełnić starsze specyfikacje, jednocześnie utrzymując kod czystym i łatwym w utrzymaniu. Przejdziemy krok po kroku, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i pokażemy, jak wyprodukować obraz PNG bez znaku wodnego wersji próbnej.

## Szybkie odpowiedzi
- **Jaka biblioteka tworzy obrazy kodów kreskowych w Javie?** Aspose.BarCode for Java.  
- **Czy mogę dostosować symbole start/stop?** Tak, używając `setCodabarStartSymbol` i `setCodabarStopSymbol`.  
- **Jaki typ kodu kreskowego jest używany w tym przykładzie?** CODABAR.  
- **Czy potrzebna jest licencja do produkcji?** Licencja komercyjna jest wymagana do użytku nie‑próbnego.  
- **Jaki format wyjściowy jest generowany?** Obraz PNG zapisany na dysku.

## Czym jest Aspose Barcode Java?

Aspose Barcode Java to **biblioteka Java niezależna od zależności, generująca ponad 70 symbologii kodów kreskowych**, od klasycznych kodów 1D, takich jak CODABAR, po nowoczesne kody 2D, takie jak QR i DataMatrix. Obsługuje wszystkie niskopoziomowe kodowania, dzięki czemu możesz skupić się na logice biznesowej, zapewniając jednocześnie zgodność ze standardami branżowymi.

## Dlaczego warto używać Aspose Barcode Java do generowania kodów kreskowych bez znaku wodnego?

Załaduj najpierw licencję, a biblioteka tworzy czyste obrazy — bez nakładki „Aspose Evaluation”. Oferuje także **precyzyjną kontrolę** (symbole start/stop, kolory, rozmiary) oraz **kompatybilność wieloplatformową** (dowolny runtime Java, w tym Android). Dzięki wsparciu **ponad 50 formatów wyjściowych** i możliwości strumieniowego przesyłania obrazów bezpośrednio w odpowiedziach HTTP, jest wyborem numer jeden dla wysokowydajnego, produkcyjnego generowania kodów kreskowych.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – Zainstaluj najnowszy JDK z [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Pobierz go z [download link](https://releases.aspose.com/barcode/java/).

Posiadanie ich zapewnia, że możesz **tworzyć obraz kodu kreskowego w Javie** bez brakujących komponentów.

## Importowanie pakietów

Poniższe importy dają dostęp do podstawowych klas potrzebnych do generowania kodów kreskowych:

Enum `CodabarSymbol` definiuje dozwolone znaki start/stop dla kodów CODABAR.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Przewodnik krok po kroku

### Jak określić folder wyjściowy dla obrazu kodu kreskowego?

Określ folder, w którym zostanie zapisany plik PNG. Użycie `Paths.get` sprawia, że kod jest przenośny między systemami Windows, macOS i Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Jak utworzyć generator kodu kreskowego dla CODABAR?

Klasa `BarcodeGenerator` tworzy obraz kodu kreskowego dla podanej symbologii i danych.  

Zainicjuj `BarcodeGenerator` z symbologią CODABAR oraz ciągiem danych, które chcesz zakodować.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Jak ustawić symbol startowy CODABAR?

`setCodabarStartSymbol` ustawia znak, który oznacza początek kodu CODABAR.  

Wywołaj `setCodabarStartSymbol` i przekaż jeden z obsługiwanych znaków (`A`, `B`, `C`, `D`). W tym przykładzie używamy `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Jak ustawić symbol stop CODABAR?

`setCodabarStopSymbol` ustawia znak, który oznacza koniec kodu CODABAR.  

Użyj `setCodabarStopSymbol` z pasującym znakiem stop — w tym przypadku `D`.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Jak zapisać wygenerowany kod kreskowy jako plik PNG?

Enum `SaveFormat` określa format pliku przy zapisywaniu obrazu kodu kreskowego.  

Wywołaj metodę `save`, podając pełną nazwę pliku oraz wartość enum `SaveFormat.Png`. Obraz zostanie zapisany bez znaku wodnego po zastosowaniu ważnej licencji.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Częste pułapki i wskazówki

Klasa `License` ładuje plik licencyjny Aspose, aby włączyć tryb pełnych funkcji.

- **Nieprawidłowa ścieżka katalogu** – Upewnij się, że `dataDir` kończy się odpowiednim separatorem plików lub zbuduj ścieżkę przy użyciu `Paths.get`.  
- **Nieobsługiwane znaki start/stop** – CODABAR akceptuje tylko `A`, `B`, `C` lub `D`. Podanie innej wartości powoduje wyrzucenie `IllegalArgumentException`.  
- **Licencja nie zastosowana** – W trybie próbnym wynik zawiera znak wodny. Załaduj plik licencyjny przy użyciu `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` przed utworzeniem generatora, aby tego uniknąć.  
- **Generowanie na dużą skalę** – Przy generowaniu tysięcy kodów kreskowych, ponownie używaj jednej instancji `BarcodeGenerator` i zmieniaj tylko tekst kodu, aby zmniejszyć narzut tworzenia obiektów.

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.BarCode for Java w projekcie komercyjnym?

Tak. Zakup licencję komercyjną [zakup licencji komercyjnej](https://purchase.aspose.com/buy), aby usunąć znak wodny oceny i uzyskać pełne wsparcie techniczne.

### Czy dostępna jest darmowa wersja próbna?

Oczywiście. Pobierz wersję próbną [pobierz wersję próbną](https://releases.aspose.com/), aby ocenić wszystkie funkcje przed zakupem.

### Jak mogę uzyskać wsparcie dla Aspose.BarCode for Java?

Odwiedź forum Aspose.BarCode [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) w celu uzyskania pomocy społeczności lub otwórz zgłoszenie wsparcia przez portal swojego konta Aspose.

### Jak uzyskać tymczasową licencję do testów?

Możesz poprosić o tymczasową 30‑dniową licencję [poproś o tymczasową 30‑dniową licencję](https://purchase.aspose.com/temporary-license/). Pozwala to na przeprowadzanie testów produkcyjnych bez pełnego zakupu.

### Jakie inne symbologie kodów kreskowych obsługuje Aspose.BarCode?

Biblioteka obsługuje **ponad 70 symbologii**, w tym Code128, EAN‑13, QR, DataMatrix, PDF417 i wiele innych. Pełną listę znajdziesz w oficjalnej dokumentacji.

## Dodatkowe pytania i odpowiedzi (przyjazne AI)

**Q:** Jakie formaty obrazu mogę wyeksportować oprócz PNG?  
**A:** Aspose.BarCode obsługuje PNG, JPEG, BMP, GIF oraz TIFF. Wybierz żądany format, zmieniając wartość enum `SaveFormat` w wywołaniu `save`.

**Q:** Czy mogę generować obrazy kodów kreskowych w pamięci, bez zapisywania na dysku?  
**A:** Tak. Wywołaj `generator.save(OutputStream)`, aby zapisać bezpośrednio do strumienia — idealne dla interfejsów API webowych zwracających obraz jako odpowiedź HTTP.

**Q:** Czy biblioteka działa na Androidzie?  
**A:** Wersja Java działa na Androidzie, ale musisz ręcznie dołączyć wymagane zależności (brak Maven Central dla Androida). Podstawowe API pozostaje identyczne.

## Zakończenie

Teraz wiesz, jak **tworzyć obraz kodu kreskowego w Javie** i precyzyjnie **ustawiać symbole start/stop** dla kodu CODABAR przy użyciu Aspose Barcode Java. To podejście daje elastyczność spełniania starszych specyfikacji, jednocześnie utrzymując bazę kodu czystą i łatwą w utrzymaniu. Eksploruj dalsze możliwości dostosowywania — takie jak zmiana kolorów, dodawanie tekstu czytnika lub przełączanie na inne symbologie — przeglądając oficjalną referencję API w [dokumentacji](https://reference.aspose.com/barcode/java/).

---

**Ostatnia aktualizacja:** 2026-08-28  
**Testowano z:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Sprawdź sumę kontrolną i utwórz kod Codabar w Javie z Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Utwórz kod kreskowy z Aspose – ustaw wymiary X i Y w Javie](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Jak generować kod kreskowy w Javie: Utwórz dokładny obraz kodu kreskowego](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}