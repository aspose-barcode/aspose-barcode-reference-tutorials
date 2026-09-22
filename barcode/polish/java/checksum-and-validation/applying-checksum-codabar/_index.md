---
date: 2026-04-05
description: Dowiedz się, jak utworzyć obraz kodu kreskowego Codabar w Javie z sumą
  kontrolną i zobacz przykład czytnika kodów kreskowych w Javie przy użyciu Aspose.BarCode.
  Postępuj zgodnie z tym przewodnikiem krok po kroku, aby generować i rozpoznawać
  kody kreskowe.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: Zastosowanie sumy kontrolnej w CodaBar
second_title: Aspose.BarCode Java API
title: Jak utworzyć obraz kodu kreskowego Codabar w Javie z sumą kontrolną
url: /pl/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego codabar w Javie z sumą kontrolną

## Wprowadzenie

W tym samouczku **utworzysz obrazy kodu kreskowego codabar w Javie** z sumą kontrolną Mod 10 przy użyciu Aspose.BarCode dla Javy. Przeprowadzimy Cię przez generowanie kodu kreskowego CodaBar, włączenie sumy kontrolnej, a następnie weryfikację przy użyciu **przykładu czytnika kodów kreskowych w Javie**. Po zakończeniu będziesz mieć gotowy fragment kodu, który możesz wkleić do dowolnego projektu Java, niezależnie od tego, czy tworzysz system biblioteczny, drukarkę etykiet w laboratorium medycznym, czy rozwiązanie kasowe w handlu detalicznym.

## Szybkie odpowiedzi
- **Do czego służy suma kontrolna?** Weryfikuje integralność danych kodu kreskowego podczas skanowania.  
- **Jakiej biblioteki wymaga?** Aspose.BarCode for Java.  
- **Czy potrzebna jest licencja do rozwoju?** Tymczasowa licencja działa w testach; pełna licencja jest wymagana w produkcji.  
- **Czy mogę dostosować wygląd kodu kreskowego?** Tak – kolor, rozmiar i czcionka mogą być zmienione za pomocą parametrów generatora.  
- **Czy jest kompatybilny ze wszystkimi wersjami Javy?** Biblioteka obsługuje Javę 8 i nowsze.

## Jak utworzyć kod kreskowy codabar w Javie

Poniżej znajdziesz zwięzły przewodnik krok po kroku, który wyjaśnia **dlaczego każda linia ma znaczenie**, dzięki czemu możesz z pewnością dostosować kod do własnych projektów.

### Czym jest kod kreskowy CodaBar?

CodaBar to liniowa (jednowymiarowa) symbologia szeroko stosowana w bibliotekach, bankach krwi i handlu detalicznym. Koduje dane numeryczne oraz kilka znaków specjalnych, co czyni go idealnym do prostych, maszynowo odczytywalnych etykiet. Dodanie sumy kontrolnej (Mod 10) zwiększa dokładność odczytu, szczególnie przy wydrukach niskiej jakości.

### Dlaczego używać Aspose.BarCode dla Javy?

Aspose.BarCode oferuje **przykład czytnika kodów kreskowych w Javie**, który abstrahuje szczegóły niskiego poziomu generowania i rozpoznawania kodów kreskowych. Zapewnia:

* Pełną kontrolę nad trybami sumy kontrolnej.  
* Bezproblemową integrację z IDE Javy.  
* Rozbudowaną dokumentację i szybkie wsparcie.

### Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK) 8 lub nowszy.  
- Bibliotekę Aspose.BarCode for Java. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/java/).  
- Podstawową znajomość koncepcji programowania w Javie.

### Importowanie pakietów

W swoim projekcie Java zaimportuj niezbędne klasy do pracy z Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

### Przewodnik krok po kroku

#### Krok 1: Konfiguracja środowiska

Utwórz nowy projekt Java i dodaj plik JAR Aspose.BarCode do ścieżki kompilacji. Zdefiniuj folder, w którym będą zapisywane wygenerowane obrazy.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### Krok 2: Generowanie obrazu kodu kreskowego CodaBar z sumą kontrolną

Utwórz instancję `BarcodeGenerator`, włącz sumę kontrolną, wybierz tryb Mod 10 i zapisz obraz.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### Krok 3: Przykład czytnika kodów kreskowych w Javie – Rozpoznawanie kodu

Teraz odczytaj kod kreskowy, włączając weryfikację sumy kontrolnej, aby upewnić się, że dane są poprawne.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Uruchomienie kodu wyświetli zdekodowany tekst, typ symbologii oraz obliczoną sumę kontrolną, potwierdzając, że kod kreskowy został wygenerowany i poprawnie zweryfikowany.

### Typowe przypadki użycia

- **Zarządzanie biblioteką:** Koduj identyfikatory książek do szybkiego skanowania przy wypożyczeniu.  
- **Etykiety banku krwi:** Zapewnij dokładną identyfikację pacjenta dzięki ochronie sumy kontrolnej.  
- **Etykiety półek w handlu detalicznym:** Drukuj tanie, szybkie kody kreskowe do śledzenia zapasów.  

### Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Weryfikacja sumy kontrolnej nie powiodła się** | Sprawdź, czy `EnableChecksum` jest ustawione na `YES` oraz czy `CodabarChecksumMode` odpowiada trybowi użytemu podczas generowania (Mod 10). |
| **Błąd: plik nie znaleziony** | Upewnij się, że `dataDir` wskazuje istniejący folder oraz że wygenerowany obraz (`Codabar_Mod10.png`) jest tam zapisany przed odczytem. |
| **Nieobsługiwana wersja Javy** | Użyj Javy 8 lub nowszej; starsze wersje mogą nie posiadać wymaganych interfejsów API. |

## Najczęściej zadawane pytania

**Q: Czy Aspose.BarCode jest kompatybilny ze wszystkimi wersjami Javy?**  
A: Aspose.BarCode jest zaprojektowany do pracy z Javą 8 i nowszą. Sprawdź oficjalną dokumentację, aby uzyskać szczegółowe informacje o kompatybilności.

**Q: Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?**  
A: Tak, możesz zmieniać kolory, czcionki i format obrazu za pomocą API parametrów generatora.

**Q: Czy dostępne są tymczasowe licencje do celów testowych?**  
A: Tak, możesz uzyskać tymczasową licencję dla Aspose.BarCode [tutaj](https://purchase.aspose.com/temporary-license/).

**Q: Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?**  
A: Odwiedź [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), aby uzyskać wsparcie społeczności i dyskusje.

**Q: Czy dostępna jest bezpłatna wersja próbna?**  
A: Tak, możesz przetestować funkcje Aspose.BarCode, pobierając bezpłatną wersję próbną [tutaj](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2026-04-05  
**Testowano z:** Aspose.BarCode for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}