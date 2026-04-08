---
date: 2026-04-08
description: Dowiedz się, jak odczytywać kody kreskowe i sortować je w określonej
  kolejności przy użyciu Aspose.BarCode for Java. Ten przewodnik krok po kroku pokazuje,
  jak korzystać z Aspose, czytnika kodów kreskowych w Javie i dekodować kod kreskowy
  Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: Odczytywanie i sortowanie kodów kreskowych w określonej kolejności
second_title: Aspose.BarCode Java API
title: Jak odczytywać kody kreskowe w określonej kolejności w Javie
url: /pl/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytywać kody kreskowe w określonej kolejności przy użyciu Javy


## Wstęp

Jeśli potrzebujesz **jak odczytywać kody kreskowe** i następnie uporządkować je w określonej sekwencji, Aspose.BarCode for Java zapewnia czysty, wysokowydajny sposób realizacji tego zadania. W wielu aplikacjach Java — systemach inwentaryzacji, rozwiązaniach wysyłkowych czy terminalach POS — odczytywanie wielu kodów kreskowych i sortowanie ich według wartości tekstowej jest częstym wymogiem. Ten samouczek przeprowadzi Cię przez cały proces, od konfiguracji środowiska po wyświetlenie posortowanych wyników, abyś mógł szybko i pewnie zintegrować obsługę kodów kreskowych.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje odczyt kodów kreskowych?** Aspose.BarCode for Java  
- **Jaki typ kodu kreskowego jest użyty w przykładzie?** CODE_128  
- **Czy potrzebna jest licencja do rozwoju?** Tymczasowa licencja działa w trybie testowym; pełna licencja jest wymagana w produkcji.  
- **Czy mogę sortować według innych kryteriów?** Tak — zmodyfikuj comparator, aby sortować według lokalizacji, pewności odczytu itp.  
- **Jakiej wersji Javy wymaga biblioteka?** Java 8 lub nowsza (dowolny JDK obsługujący bibliotekę Aspose).

## Co oznacza „jak odczytywać kody kreskowe” w Javie?

Odczytywanie kodów kreskowych to dekodowanie wzoru wizualnego do pierwotnego ciągu danych. Aspose.BarCode udostępnia klasę `BarCodeReader`, która abstrahuje niskopoziomowe przetwarzanie obrazu, pozwalając skupić się na logice biznesowej, takiej jak sortowanie czy walidacja.

## Dlaczego warto używać Aspose.BarCode for Java?

- **Solidne dekodowanie** – obsługuje ponad 50 symbologii, w tym Code 128, QR, DataMatrix i inne.  
- **Wysoka dokładność** – zoptymalizowane algorytmy zmniejszają liczbę błędnych odczytów, nawet przy niskiej rozdzielczości obrazów.  
- **Proste API** – kilka linii kodu przenosi Cię od obrazu do tekstu.  
- **Wieloplatformowość** – działa na dowolnym środowisku Java, od komputerów stacjonarnych po serwery.

## Wymagania wstępne

Przed przystąpieniem do kodu upewnij się, że spełniasz poniższe wymagania:

- Java Development Kit (JDK): Aspose.BarCode for Java wymaga działającego JDK. Najnowszą wersję możesz pobrać [tutaj](https://www.oracle.com/java/technologies/javase-downloads.html).

- Biblioteka Aspose.BarCode: Upewnij się, że masz bibliotekę Aspose.BarCode. Możesz ją pobrać z [linku do pobrania](https://releases.aspose.com/barcode/java/).

## Importowanie pakietów

Rozpocznij od zaimportowania niezbędnych pakietów do projektu Java. Pakiety te dostarczają kluczowe klasy i metody do pracy z kodami kreskowymi.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Teraz przeanalizujemy kod krok po kroku:

## Krok 1: Konfiguracja katalogu zasobów

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Zastąp `"Your Document Directory"` rzeczywistą ścieżką do katalogu z dokumentami.

## Krok 2: Określenie ścieżki obrazu kodu kreskowego i inicjalizacja czytnika

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Krok 3: Odczyt kodów kreskowych i przechowywanie wyników

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Krok 4: Definicja comparatora do sortowania

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Krok 5: Sortowanie kodów kreskowych

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Krok 6: Wyświetlanie posortowanych kodów kreskowych

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Typowe pułapki i wskazówki

- **Nieprawidłowa ścieżka obrazu** – sprawdź, czy `dataDir` kończy się separatorem plików (`/` lub `\\`), aby pełna ścieżka została poprawnie zbudowana.  
- **Nieobsługiwany typ kodu kreskowego** – jeśli potrzebujesz dekodować inną symbologię, zmień `DecodeType.CODE_128` na odpowiednią wartość wyliczeniową (np. `DecodeType.QR`).  
- **Sortowanie według wartości liczbowej** – domyślny comparator sortuje leksykograficznie. Aby uzyskać sortowanie liczbowe, przetwórz `CodeText` na liczbę całkowitą wewnątrz comparatora.  
- **Czyszczenie zasobów** – `BarCodeReader` implementuje `Closeable`. W kodzie produkcyjnym otocz go blokiem try‑with‑resources, aby zapewnić zwolnienie strumienia.

## Najczęściej zadawane pytania

### P: Gdzie mogę znaleźć dokumentację Aspose.BarCode for Java?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/barcode/java/).

### P: Jak mogę pobrać Aspose.BarCode for Java?
Możesz pobrać ją z [linku do pobrania](https://releases.aspose.com/barcode/java/).

### P: Czy dostępna jest bezpłatna wersja próbna?
Tak, wersję próbną możesz wypróbować [tutaj](https://releases.aspose.com/).

### P: Jak uzyskać informacje o licencji tymczasowej?
Licencje tymczasowe można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### P: Gdzie mogę uzyskać wsparcie lub zadać pytania?
Odwiedź forum wsparcia [tutaj](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-04-08  
**Testowano z:** Aspose.BarCode 24.10 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}