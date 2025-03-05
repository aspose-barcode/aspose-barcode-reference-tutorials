---
title: Stosowanie sumy kontrolnej dla CodaBar w Javie
linktitle: Stosowanie sumy kontrolnej dla CodaBar
second_title: Aspose.BarCode API Java
description: Dowiedz się, jak zastosować sumę kontrolną dla CodaBar w Javie przy użyciu Aspose.BarCode. Dzięki temu przewodnikowi krok po kroku możesz łatwo generować i rozpoznawać kody kreskowe.
type: docs
weight: 11
url: /pl/java/checksum-and-validation/applying-checksum-codabar/
---

## Wstęp

Witamy w tym samouczku krok po kroku dotyczącym stosowania sumy kontrolnej dla CodaBar w Javie przy użyciu Aspose.BarCode. Aspose.BarCode for Java to potężna biblioteka, która umożliwia programistom płynne generowanie i rozpoznawanie kodów kreskowych w aplikacjach Java. W tym samouczku skupimy się na konkretnym zadaniu stosowania sumy kontrolnej dla kodów kreskowych CodaBar.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
-  Aspose.BarCode dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/barcode/java/).
- Podstawowa znajomość programowania w języku Java.

## Importuj pakiety

W swoim projekcie Java pamiętaj o zaimportowaniu pakietów niezbędnych do pracy z Aspose.BarCode:

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

## Krok 1: Skonfiguruj środowisko

Zacznij od utworzenia nowego projektu Java i dołączenia biblioteki Aspose.BarCode do zależności projektu. Skonfiguruj środowisko programistyczne z wymaganymi zasobami.

```java
// Ścieżka do katalogu zasobów.
String dataDir = "Your Document Directory";
```

## Krok 2: Wygenerowanie kodu kreskowego CodaBar

Teraz wygenerujmy kod kreskowy CodaBar z włączoną sumą kontrolną.

```java
// Utwórz instancję obiektu BarcodeGenerator
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Ustaw właściwość EnableChecksum na wartość tak
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Ustaw tryb sumy kontrolnej Codabar
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Zapisz obraz w systemie
generator.save(dataDir + "Codabar_Mod10.png");
```

## Krok 3: Rozpoznanie kodu kreskowego CodaBar

Teraz zaimplementujmy część rozpoznawania kodu kreskowego CodaBar z sumą kontrolną.

```java
// Zainicjuj obiekt czytnika
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Ustaw właściwość ChecksumValidation czytnika na On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Uzyskaj wartość sumy kontrolnej
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Wykonaj poniższe kroki, aby bez wysiłku zastosować sumę kontrolną dla CodaBar w Javie, używając Aspose.BarCode.

## Wniosek

W tym samouczku omówiliśmy, jak zastosować sumę kontrolną dla kodów kreskowych CodaBar w Javie przy użyciu Aspose.BarCode. Ta biblioteka zapewnia prosty sposób generowania i rozpoznawania kodów kreskowych z różnymi opcjami dostosowywania.

---

## Często zadawane pytania

### Czy Aspose.BarCode jest kompatybilny ze wszystkimi wersjami Java?
Aspose.BarCode jest przeznaczony do pracy z różnymi wersjami Java. Upewnij się, że sprawdziłeś dokumentację pod kątem szczegółów kompatybilności.

### Czy mogę dostosować wygląd wygenerowanego kodu kreskowego?
Tak, Aspose.BarCode oferuje szerokie możliwości dostosowywania, pozwalając kontrolować wygląd generowanych kodów kreskowych.

### Czy dostępne są licencje tymczasowe do celów testowych?
 Tak, możesz uzyskać tymczasową licencję na Aspose.BarCode od[Tutaj](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę znaleźć dodatkowe wsparcie i zasoby?
 Odwiedzić[Forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) za wsparcie społeczności i dyskusje.

### Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz poznać funkcje Aspose.BarCode, pobierając bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).