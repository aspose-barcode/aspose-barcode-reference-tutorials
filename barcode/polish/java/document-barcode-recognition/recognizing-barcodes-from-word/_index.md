---
title: Łatwe rozpoznawanie kodów kreskowych z dokumentów Word
linktitle: Rozpoznawanie kodów kreskowych z dokumentów Word
second_title: Aspose.BarCode API Java
description: Poznaj bezproblemową integrację rozpoznawania kodów kreskowych z aplikacjami Java za pomocą Aspose.BarCode. Skorzystaj z tego samouczka, aby rozpoznać kody kreskowe z dokumentów programu Word.
weight: 12
url: /pl/java/document-barcode-recognition/recognizing-barcodes-from-word/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Łatwe rozpoznawanie kodów kreskowych z dokumentów Word


## Wstęp

dynamicznym świecie programowania w języku Java potrzeba wydajnej pracy z kodami kreskowymi stale rośnie. Rozpoznawanie kodów kreskowych z dokumentów programu Word jest powszechnym wymaganiem i na szczęście Aspose.BarCode dla Java zapewnia solidne rozwiązanie. W tym samouczku przeprowadzimy Cię przez proces rozpoznawania kodów kreskowych z dokumentów programu Word przy użyciu Aspose.BarCode dla Java.

## Warunki wstępne

Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK): Aspose.BarCode dla Java wymaga środowiska programistycznego Java. Upewnij się, że masz zainstalowany najnowszy pakiet JDK w swoim systemie.

-  Aspose.BarCode dla Java: Pobierz i zainstaluj bibliotekę Aspose.BarCode dla Java. Możesz znaleźć link do pobrania[Tutaj](https://releases.aspose.com/barcode/java/).

- Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko IDE, takie jak Eclipse lub IntelliJ, i postępuj zgodnie z przykładami.

## Importuj pakiety

Aby rozpocząć, w swoim projekcie Java zaimportuj niezbędne pakiety Aspose.BarCode:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Krok 1: Wygeneruj obraz kodu kreskowego

Najpierw utwórz obraz kodu kreskowego za pomocą Aspose.BarCode. Ustaw tekst kodu i zapisz obraz:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Krok 2: Dodaj obraz do dokumentu programu Word

Teraz wstaw wygenerowany obraz kodu kreskowego do dokumentu Word za pomocą Aspose.Words:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Krok 3: Rozpoznaj kody kreskowe z dokumentu Word

Następnie wyodrębnij obrazy z dokumentu Word i rozpoznaj kody kreskowe za pomocą Aspose.BarCode:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Wyodrębnij obraz do pliku
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Rozpoznaj kod kreskowy z tego obrazu
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

Powtórz te kroki, a z powodzeniem rozpoznasz kody kreskowe z dokumentów programu Word przy użyciu Aspose.BarCode for Java.

## Wniosek

Podsumowując, wykorzystanie Aspose.BarCode dla Java upraszcza proces rozpoznawania kodów kreskowych z dokumentów Word. Wykonaj czynności opisane powyżej, a bezproblemowo zintegrujesz rozpoznawanie kodów kreskowych z aplikacjami Java.

## Często zadawane pytania (FAQ)

### P: Czy mogę używać Aspose.BarCode dla Java w projektach komercyjnych?
 Tak, Aspose.BarCode dla Java jest dostępny do użytku komercyjnego. Możesz znaleźć szczegóły licencji[Tutaj](https://purchase.aspose.com/buy).

### P: Czy dostępna jest bezpłatna wersja próbna Aspose.BarCode dla Java?
 Tak, możesz poznać funkcje Aspose.BarCode dla Java, pobierając bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### P: Jak uzyskać wsparcie dla Aspose.BarCode dla Java?
Aby uzyskać pomoc lub pytania, odwiedź forum Aspose.BarCode[Tutaj](https://forum.aspose.com/c/barcode/13).

### P: Czy dostępne są licencje tymczasowe dla Aspose.BarCode dla Java?
 Tak, możesz uzyskać licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).

### P: Gdzie mogę znaleźć dokumentację Aspose.BarCode dla Java?
 Zapoznaj się z obszerną dokumentacją[Tutaj](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
