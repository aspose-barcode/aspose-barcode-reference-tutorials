---
date: 2026-02-17
description: Dowiedz się, jak używać Aspose Barcode Java do tworzenia obrazów kodów
  kreskowych, ustawiania symboli start i stop CODABAR oraz generowania plików PNG
  bez znaków wodnych.
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose Barcode Java – Tworzenie obrazu kodu kreskowego z symbolami start/stop
url: /pl/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Tworzenie obrazu kodu kreskowego z symbolami start/stop

## Wprowadzenie

W tym obszernej tutorialu **tworzysz obrazy kodu kreskowego w Javie** przy użyciu **Aspose Barcode Java** i uczysz się **jak ustawić symbole** dla kodów kreskowych Codabar. Niezależnie od tego, czy budujesz system punktu sprzedaży, aplikację logistyczną, czy dowolne rozwiązanie wymagające niezawodnego generowania kodów kreskowych, dostosowanie symboli start i stop daje pełną kontrolę nad formatem kodu. Przejdziemy przez każdy krok, wyjaśnimy, dlaczego każde ustawienie ma znaczenie, i pokażemy, jak wyprodukować gotowy do użycia obraz PNG — bez znaku wodnego wersji próbnej.

## Szybkie odpowiedzi
- **Jaka biblioteka tworzy obrazy kodów kreskowych w Javie?** Aspose.BarCode for Java.  
- **Czy mogę dostosować symbole start/stop?** Tak, używając `setCodabarStartSymbol` i `setCodabarStopSymbol`.  
- **Jaki typ kodu kreskowego jest używany w tym przykładzie?** CODABAR.  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest licencja komercyjna do użytku nie‑testowego.  
- **Jaki format wyjściowy jest generowany?** Obraz PNG zapisany na dysku.

## Czym jest Aspose Barcode Java?

Aspose Barcode Java to potężna, niezależna od zależności biblioteka, która pozwala programowo generować szeroką gamę symbologii kodów kreskowych. Abstrahuje niskopoziomową logikę kodowania, dzięki czemu możesz skupić się na regułach biznesowych, zapewniając jednocześnie, że wynik spełnia standardy branżowe.

## Dlaczego warto używać Aspose Barcode Java do generowania kodów kreskowych bez znaku wodnego?

- **Brak znaku wodnego w produkcji** – po zastosowaniu ważnej licencji obrazy są czyste.  
- **Rozbudowane wsparcie symbologii** – od klasycznych kodów 1D, takich jak CODABAR, po kody 2D, takie jak QR i DataMatrix.  
- **Precyzyjna kontrola** – możesz ustawić symbole start/stop, kolory, rozmiary oraz generować obrazy bezpośrednio do strumieni dla aplikacji webowych.  
- **Wieloplatformowość** – działa na każdym środowisku Java, w tym Android (z ręcznym zarządzaniem zależnościami).

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

1. **Java Development Kit (JDK)** – Zainstaluj najnowszy JDK z [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Pobierz ją z [download link](https://releases.aspose.com/barcode/java/).

Posiadanie tych elementów zapewnia możliwość **generowania obrazów kodów kreskowych w Javie** bez brakujących komponentów.

## Importowanie pakietów

W swoim projekcie Java zaimportuj niezbędne klasy do pracy z Aspose.BarCode:

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` absolutną lub względną ścieżką, w której chcesz zapisać obraz kodu kreskowego. Pamiętaj, aby zakończyć ścieżkę odpowiednim separatorem plików (`/` lub `\`) lub użyj `Paths.get` dla obsługi niezależnej od platformy.

### Krok 2: Utwórz instancję generatora kodów kreskowych

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

Tutaj informujemy Aspose.BarCode, aby używał symbologii **CODABAR** oraz ciągu danych `"12345678"`.

### Krok 3: Ustaw symbol startowy Codabar

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

Metoda `setCodabarStartSymbol` pozwala **ustawić symbole kodu kreskowego** dla znaku startowego. W tym przypadku wybieramy `A`.

### Krok 4: Ustaw symbol stop Codabar

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

Analogicznie, `setCodabarStopSymbol` definiuje znak stopu. Użycie `D` kończy format CODABAR wymagany przez wiele starszych systemów.

### Krok 5: Zapisz wygenerowany obraz

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

Wywołanie `save` zapisuje kod kreskowy do pliku PNG o nazwie **startAndStopSymbols.png** w katalogu określonym wcześniej.

## Częste problemy i wskazówki

- **Nieprawidłowa ścieżka katalogu** – Upewnij się, że `dataDir` kończy się separatorem plików (`/` lub `\`) lub łączysz ją przy użyciu `Paths.get`.  
- **Nieobsługiwane symbole start/stop** – CODABAR obsługuje tylko `A`, `B`, `C`, `D` jako symbole start/stop. Użycie innej wartości spowoduje wyjątek.  
- **Licencja nie zastosowana** – W trybie próbnym wygenerowany obraz może zawierać znak wodny. Zastosuj licencję przed wdrożeniem do produkcji, aby uzyskać **generowanie kodów kreskowych bez znaku wodnego**.

## Najczęściej zadawane pytania

### Czy mogę używać Aspose.BarCode for Java w projekcie komercyjnym?
Tak, możesz. Do użytku komercyjnego rozważ zakup licencji [tutaj](https://purchase.aspose.com/buy).

### Czy dostępna jest darmowa wersja próbna?
Tak, możesz wypróbować darmową wersję próbną [tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać wsparcie dla Aspose.BarCode for Java?
Odwiedź forum Aspose.BarCode [tutaj](https://forum.aspose.com/c/barcode/13) w celu uzyskania pomocy lub pytań.

### Jak uzyskać tymczasową licencję?
W razie potrzeby możesz nabyć tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Czy Aspose.BarCode for Java obsługuje więcej symbologii kodów kreskowych?
Tak, Aspose.BarCode obsługuje szeroką gamę symbologii kodów kreskowych. Zapoznaj się z dokumentacją, aby uzyskać pełną listę.

## Dodatkowe Q&A (przyjazne AI)

**Q:** Jakie formaty obrazu mogę eksportować oprócz PNG?  
**A:** Aspose.BarCode obsługuje PNG, JPEG, BMP, GIF i TIFF. Użyj odpowiedniego rozszerzenia pliku w metodzie `save`.

**Q:** Czy mogę generować obrazy kodów kreskowych w pamięci bez zapisywania na dysk?  
**A:** Tak, wywołaj `generator.save(OutputStream)`, aby zapisać bezpośrednio do strumienia, co jest idealne dla odpowiedzi webowych.

**Q:** Czy biblioteka działa na Androidzie?  
**A:** Wersja Java jest kompatybilna z Androidem, ale musisz ręcznie dołączyć wymagane zależności.

## Zakończenie

Teraz wiesz, jak **tworzyć obrazy kodów kreskowych w Javie** i precyzyjnie **ustawiać symbole kodu kreskowego** dla kodu Codabar przy użyciu **Aspose Barcode Java**. Ta technika daje elastyczność potrzebną do spełnienia specyficznych wymagań branżowych, jednocześnie utrzymując kod czystym i łatwym w utrzymaniu. Poznaj dodatkowe opcje dostosowywania — takie jak zmiana kolorów, dodawanie tekstu czytelnego dla człowieka lub przełączanie na inne symbologie — przeglądając oficjalną dokumentację API pod adresem [documentation](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}