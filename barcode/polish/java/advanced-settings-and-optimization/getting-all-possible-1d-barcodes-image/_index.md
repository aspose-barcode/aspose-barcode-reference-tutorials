---
date: 2025-11-29
description: Naucz się odczytywać kody kreskowe 1D w Javie za pomocą Aspose.BarCode
  – szybko dekoduj kody kreskowe z obrazu, korzystając z solidnej biblioteki kodów
  kreskowych dla Javy.
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Jak odczytywać kody kreskowe 1D w Javie przy użyciu Aspose.BarCode
url: /pl/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Odczytywanie kodów kreskowych 1D w Javie z Aspose.BarCode

## Wprowadzenie

W tym praktycznym przewodniku dowiesz się, jak **read 1D barcodes in Java** przy użyciu potężnej biblioteki **Aspose.BarCode**. Niezależnie od tego, czy musisz skanować etykiety produktów, tagi inwentaryzacyjne, czy dowolny liniowy kod kreskowy osadzony w obrazie, ten tutorial przeprowadzi Cię przez każdy krok — od konfiguracji środowiska po wyodrębnienie wszystkich możliwych kodów kreskowych, które zawiera obraz. Po zakończeniu będziesz w stanie **decode barcodes from image** za pomocą kilku linii kodu Java.

## Szybkie odpowiedzi
- **Do czego służy Aspose.BarCode?** Zapewnia w pełni funkcjonalną bibliotekę kodów kreskowych dla Javy, która może generować i dekodować kody 1D/2D.  
- **Czy mogę odczytać wiele kodów kreskowych z jednego obrazu?** Tak – metoda `BarCodeReader.readBarCodes()` zwraca wszystkie wykryte symbole.  
- **Czy potrzebuję licencji do rozwoju?** Tymczasowa licencja działa w testach; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje Javy są wspierane?** Java 8 + (zalecany JDK 11).  
- **Czy ta biblioteka jest wystarczająco szybka do skanowania w czasie rzeczywistym?** Zdecydowanie – jest zoptymalizowana pod kątem wysokowydajnego przetwarzania wsadowego.

## Co to jest „read 1d barcodes java”?

Odczytywanie kodów kreskowych 1D w Javie oznacza użycie **barcode library for Java** do analizy obrazu, wykrywania liniowych wzorców kodów kreskowych i zwracania zakodowanego tekstu wraz z metadanymi, takimi jak typ symbolu i orientacja. Aspose.BarCode abstrahuje ciężką pracę przetwarzania obrazu, pozwalając skupić się na logice biznesowej.

## Dlaczego wybrać Aspose.BarCode do dekodowania kodów kreskowych z obrazu?

- **Szerokie wsparcie symboli** – ponad 50 typów 1D i 2D.  
- **Accurate detection** – działa nawet przy niskim kontraście lub obróconych kodach.  
- **Simple API** – kilka wywołań metod wystarczy, aby uzyskać wszystkie wyniki.  
- **No external dependencies** – czysta Java, łatwa do osadzenia w każdym projekcie.  

## Wymagania wstępne

Zanim przejdziemy do kodu, upewnij się, że masz następujące:

- **Java Development Kit (JDK)** – wersja 8 lub nowsza. Pobierz go z oficjalnej [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – pobierz najnowszy plik JAR ze [Aspose release page](https://releases.aspose.com/barcode/java/).  

Teraz, gdy środowisko jest gotowe, rozpocznijmy kodowanie.

## Importowanie przestrzeni nazw

Dodaj wymagane instrukcje `import`, aby kompilator mógł znaleźć klasy Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Krok 1: Inicjalizacja obiektu BarCodeReader

Utwórz instancję `BarCodeReader` wskazującą na plik obrazu. Parametr `DecodeType` informuje silnik, jakich symboli szukać; użycie `CODE_128` jako przykładu działa dla wielu popularnych kodów 1D.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Wskazówka:** Jeśli chcesz skanować *wszystkie* obsługiwane typy 1D, przekaż `DecodeType.ALL_1D` zamiast pojedynczej symboliki.

## Krok 2: Odczyt wszystkich możliwych kodów kreskowych

Iteruj po kolekcji zwróconej przez `readBarCodes()`. Dla każdego `BarCodeResult` wypisujemy zdekodowany tekst, nazwę symboliki, kąt wykrycia oraz cztery współrzędne narożników regionu kodu.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

Pętla automatycznie przetwarza każdy znaleziony kod, więc nie musisz wywoływać czytnika wielokrotnie. Po zakończeniu pętli zmienna `iCount` zawiera łączną liczbę wykrytych kodów.

## Typowe problemy i jak je rozwiązać

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---------|--------------|----------|
| Nie zwrócono kodów kreskowych | Obraz jest zbyt rozmyty lub ma niski kontrast | Wstępnie przetwórz obraz (zwiększ kontrast, binarizuj) przed przekazaniem go do czytnika. |
| Zgłoszono nieprawidłową symbolikę | Użyto nieprawidłowego `DecodeType` | Użyj `DecodeType.ALL_1D`, aby silnik automatycznie wykrył dowolny typ 1D. |
| Wartości kąta są nieprawidłowe | Obraz obrócony | API już zwraca kąt obrotu; w razie potrzeby możesz obrócić obraz z powrotem. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.BarCode dla Javy nadaje się do projektów komercyjnych?**  
A: Tak. Licencja komercyjna usuwa wszystkie ograniczenia wersji ewaluacyjnej i daje pełne prawa do dystrybucji.

**Q: Czy mogę testować bibliotekę bez zakupu licencji?**  
A: Zdecydowanie. Uzyskaj tymczasową licencję ze [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) do rozwoju i testów.

**Q: Gdzie mogę znaleźć pełną dokumentację API?**  
A: Kompleksowa dokumentacja jest dostępna [tutaj](https://reference.aspose.com/barcode/java/).

**Q: Jak uzyskać pomoc, jeśli napotkam problem?**  
A: Zamieść pytanie na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), gdzie społeczność i inżynierowie Aspose mogą pomóc.

**Q: Czy dostępny jest bezpłatny trial do pobrania?**  
A: Tak – możesz pobrać wersję trial ze [strony z wydaniami Aspose](https://releases.aspose.com/).

## Podsumowanie

Teraz wiesz, jak **read 1D barcodes in Java** przy użyciu Aspose.BarCode, solidnej **barcode library for Java**, która sprawia, że dekodowanie kodów kreskowych z plików obrazów jest proste i niezawodne. Zintegruj ten fragment kodu w swoich aplikacjach, aby automatyzować skanowanie inwentarza, weryfikację biletów lub każdy scenariusz, w którym w obrazach pojawiają się liniowe kody kreskowe.

---

**Last Updated:** 2025-11-29  
**Tested With:** Aspose.BarCode 24.11 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}