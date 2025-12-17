---
date: 2025-12-17
description: Dowiedz się, jak generować kod kreskowy w Javie przy użyciu Aspose.BarCode,
  obejmując dynamiczne generowanie kodów kreskowych, tworzenie kodów EAN‑13 oraz zapisywanie
  obrazów kodów kreskowych z danymi uzupełniającymi.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Jak wygenerować kod kreskowy z danymi uzupełniającymi w Javie
url: /pl/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wygenerować kod kreskowy z danymi uzupełniającymi w Javie

## Wprowadzenie

W dzisiejszym szybko zmieniającym się ekosystemie cyfrowym, **jak wygenerować kod kreskowy** efektywnie, jest pytaniem, z którym spotyka się wielu programistów Javy. Aspose.BarCode for Java oferuje potężne, łatwe w użyciu API, które obsługuje **dynamiczne generowanie kodów kreskowych**, w tym tworzenie **kodów kreskowych EAN‑13** z danymi uzupełniającymi. Niezależnie od tego, czy tworzysz systemy inwentaryzacji, aplikacje POS w handlu detalicznym, czy systemy śledzenia logistycznego, ten samouczek przeprowadzi Cię przez **przykład generatora kodów kreskowych w Javie**, który zapisuje obraz kodu kreskowego na dysku i pozwala dostosować część uzupełniającą.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do generowania kodów kreskowych w Javie?** Aspose.BarCode for Java.
- **Która symbologia tworzy 13‑cyfrowy kod numeryczny?** EAN‑13.
- **Czy mogę dodać dane uzupełniające do kodu EAN‑13?** Tak, przy użyciu API `Supplement`.
- **Jak zapisać wygenerowany kod kreskowy jako obraz?** Wywołaj `generator.save("path/filename.jpg")`.
- **Czy wymagana jest licencja do użytku produkcyjnego?** Tak, potrzebna jest licencja komercyjna; dostępna jest bezpłatna wersja próbna.

## Czym jest generowanie kodów kreskowych w Javie?

Generowanie kodów kreskowych oznacza konwersję danych — liczb, liter lub ich mieszanki — w wizualny wzór, który skanery mogą odczytać. Dzięki Aspose.BarCode możesz tworzyć **obrazy kodów kreskowych o wysokiej rozdzielczości** w locie, co czyni je idealnymi dla scenariuszy **dynamicznego generowania kodów kreskowych**, takich jak biletowanie w czasie rzeczywistym czy realizacja zamówień.

## Dlaczego warto używać Aspose.BarCode do dynamicznego generowania kodów kreskowych?

- **Pełna kontrola** nad symbologią, rozmiarem, kolorami i danymi uzupełniającymi.  
- **Brak zewnętrznych zależności** – czysta Java, działa na każdej platformie.  
- **Wbudowane wsparcie** dla dziesiątek typów kodów kreskowych, w tym **tworzenie kodu ean13**.  
- **Proste API**, które pozwala **zapisać obraz kodu kreskowego** jedną linią kodu.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- **Java Development Kit (JDK)** – dowolną aktualną wersję (8 lub nowszą).  
- **IDE** – IntelliJ IDEA, Eclipse lub ulubiony edytor.  
- **Aspose.BarCode for Java** – pobierz bibliotekę z oficjalnej strony **[tutaj](https://releases.aspose.com/barcode/java/)** i dodaj plik JAR do classpathu projektu.

## Importowanie pakietów

Po odwołaniu biblioteki, zaimportuj główną klasę, która steruje tworzeniem kodów kreskowych.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Przewodnik krok po kroku

### Krok 1: Zdefiniuj katalog dokumentu

Ustaw folder, w którym zostanie zapisany wygenerowany obraz.

```java
String dataDir = "Your Document Directory";
```

### Krok 2: Utwórz instancję generatora kodów kreskowych

Zainicjuj `BarcodeGenerator` z żądanym **codetext** i **symbology**. Tutaj **tworzymy kod ean13** używając ciągu numerycznego `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Krok 3: Ustaw dane uzupełniające

Dodaj 5‑cyfrowy ciąg uzupełniający. Jest to przydatne w przypadku czasopism, periodyków lub wszelkich sytuacji, w których dodatkowe informacje następują po głównym kodzie kreskowym.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Krok 4: Ustaw odstęp uzupełnienia

Dostosuj odstęp między głównym kodem kreskowym a jego uzupełnieniem. Wartość wyrażona jest w punktach.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Krok 5: Zapisz obraz kodu kreskowego

Na koniec zapisz obraz na dysku. Format jest wywnioskowany z rozszerzenia pliku (JPEG w tym przykładzie).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Wskazówka:** Możesz zmienić rozszerzenie pliku na `.png` lub `.bmp`, aby uzyskać inny format obrazu bez dodatkowego kodu.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **Obraz nie został zapisany** | `dataDir` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub utwórz go programowo (`new File(dataDir).mkdirs();`). |
| **Nieprawidłowa długość uzupełnienia** | Uzupełnienia EAN‑13 muszą mieć 2 lub 5 cyfr | Podaj dokładnie 2 lub 5 znaków; w przeciwnym razie zostanie zgłoszony wyjątek. |
| **Nieobsługiwane znaki** | Znaki nienumeryczne w codetext EAN‑13 | Używaj tylko cyfr 0‑9 dla EAN‑13; przełącz się na inną symbologię dla znaków alfanumerycznych. |

## Najczęściej zadawane pytania

### Czy Aspose.BarCode jest kompatybilny ze wszystkimi wersjami Javy?
Aspose.BarCode for Java jest zaprojektowany tak, aby być kompatybilnym z szerokim zakresem wersji Javy. Odwołaj się do **[dokumentacji](https://reference.aspose.com/barcode/java/)** po szczegółowe informacje.

### Czy mogę dostosować wygląd wygenerowanych kodów kreskowych?
Tak, Aspose.BarCode udostępnia różne parametry i ustawienia umożliwiające dostosowanie wyglądu kodów kreskowych. Zapoznaj się z dokumentacją po szczegółowe informacje.

### Czy dostępna jest wersja próbna?
Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej **[tutaj](https://releases.aspose.com/)**.

### Jak mogę uzyskać wsparcie dla Aspose.BarCode?
Odwiedź **[forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13)**, aby uzyskać pomoc od społeczności i ekspertów.

### Gdzie mogę kupić Aspose.BarCode dla Javy?
Możesz zakupić Aspose.BarCode dla Javy **[tutaj](https://purchase.aspose.com/buy)**.

---

**Ostatnia aktualizacja:** 2025-12-17  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}