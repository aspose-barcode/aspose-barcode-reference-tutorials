---
date: 2025-12-18
description: Dowiedz się, jak stworzyć obraz kodu kreskowego Codabar i zobacz przykład
  czytnika kodów kreskowych w Javie przy użyciu Aspose.BarCode. Generuj i rozpoznawaj
  kody kreskowe bez wysiłku dzięki temu przewodnikowi krok po kroku.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Jak utworzyć obraz kodu kreskowego Codabar z sumą kontrolną w Javie
url: /pl/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć obraz kodu kreskowego codabar z sumą kontrolną w Javie

## Wprowadzenie

W tym samouczku dowiesz się, jak **utworzyć obraz kodu kreskowego codabar** z sumą kontrolną w Javie przy użyciu Aspose.BarCode. Przejdziemy przez generowanie kodu CodaBar, włączenie sumy kontrolnej, a następnie odczytanie go za pomocą **przykładu czytnika kodów kreskowych w Javie**. Na koniec będziesz mieć gotowy fragment kodu, który możesz wkleić do dowolnego projektu Java.

## Szybkie odpowiedzi
- **Co robi suma kontrolna?** Weryfikuje integralność danych kodu kreskowego podczas skanowania.  
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode dla Javy.  
- **Czy potrzebna jest licencja do rozwoju?** Tymczasowa licencja wystarczy do testów; pełna licencja jest wymagana w produkcji.  
- **Czy mogę dostosować wygląd kodu kreskowego?** Tak – kolor, rozmiar i czcionkę można zmienić za pomocą parametrów generatora.  
- **Czy to działa ze wszystkimi wersjami Javy?** Biblioteka obsługuje Javę 8 i nowsze.

## Co to jest kod kreskowy CodaBar?

CodaBar to liniowa (jednowymiarowa) symbologia szeroko stosowana w bibliotekach, bankach krwi i handlu detalicznym. Koduje dane numeryczne oraz kilka znaków specjalnych, co czyni go idealnym do prostych, maszynowo odczytywalnych etykiet. Dodanie sumy kontrolnej (Mod 10) zwiększa dokładność odczytu, szczególnie przy niskiej jakości wydrukach.

## Dlaczego warto używać Aspose.BarCode dla Javy?

Aspose.BarCode oferuje **przykład czytnika kodów kreskowych w Javie**, który ukrywa niskopoziomowe szczegóły generowania i rozpoznawania kodów. Zapewnia:

* Pełną kontrolę nad trybami sumy kontrolnej.  
* Bezproblemową integrację z IDE Javy.  
* Rozbudowaną dokumentację i wsparcie.  

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz:

- Zainstalowany Java Development Kit (JDK).  
- Bibliotekę Aspose.BarCode dla Javy. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/java/).  
- Podstawową znajomość programowania w Javie.  

## Importowanie pakietów

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

## Przewodnik krok po kroku

### Krok 1: Konfiguracja środowiska

Utwórz nowy projekt Java i dodaj plik JAR Aspose.BarCode do ścieżki kompilacji. Zdefiniuj folder, w którym będą zapisywane wygenerowane obrazy.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Generowanie obrazu kodu CodaBar z sumą kontrolną

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

### Krok 3: Przykład czytnika kodów kreskowych w Javie – rozpoznanie kodu

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

Uruchomienie kodu wyświetli zdekodowany tekst, typ symbologii oraz obliczoną sumę kontrolną, potwierdzając, że kod został wygenerowany i poprawnie zweryfikowany.

## Typowe problemy i rozwiązania

| Problem | Rozwiązanie |
|-------|----------|
| **Weryfikacja sumy kontrolnej nie powiodła się** | Sprawdź, czy `EnableChecksum` jest ustawione na `YES` oraz czy `CodabarChecksumMode` odpowiada trybowi użytemu podczas generacji (Mod 10). |
| **Błąd „plik nie znaleziony”** | Upewnij się, że `dataDir` wskazuje istniejący folder i że wygenerowany obraz (`Codabar_Mod10.png`) został tam zapisany przed odczytem. |
| **Nieobsługiwana wersja Javy** | Użyj Javy 8 lub nowszej; starsze wersje mogą nie posiadać wymaganych API. |

## Najczęściej zadawane pytania

**P: Czy Aspose.BarCode jest kompatybilny ze wszystkimi wersjami Javy?**  
O: Aspose.BarCode został zaprojektowany do pracy z Javą 8 i nowszą. Szczegółową kompatybilność znajdziesz w oficjalnej dokumentacji.

**P: Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?**  
O: Tak, możesz modyfikować kolory, czcionki i format obrazu za pomocą API parametrów generatora.

**P: Czy dostępne są tymczasowe licencje do testów?**  
O: Tak, tymczasową licencję dla Aspose.BarCode możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

**P: Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?**  
O: Odwiedź [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), aby uzyskać pomoc społeczności i dyskusje.

**P: Czy dostępna jest darmowa wersja próbna?**  
O: Tak, możesz wypróbować funkcje Aspose.BarCode, pobierając darmową wersję próbną [tutaj](https://releases.aspose.com/).

---

**Ostatnia aktualizacja:** 2025-12-18  
**Testowano z:** Aspose.BarCode dla Javy 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}