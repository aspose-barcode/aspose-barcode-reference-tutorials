---
date: 2025-12-19
description: Naucz się odczytywać kody kreskowe w Javie z dokumentów Word przy użyciu
  Aspose.BarCode. Ten przewodnik obejmuje generowanie obrazów kodów kreskowych, wstawianie
  ich do Worda oraz wyodrębnianie obrazów w celu odczytu kodów kreskowych.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Jak odczytać kod kreskowy w Javie z dokumentów Word
url: /pl/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy java z dokumentów Word

## Wprowadzenie

Praca z kodami kreskowymi w aplikacjach Java jest powszechną potrzebą, szczególnie gdy kody te są osadzone w plikach Microsoft Word. W tym samouczku dowiesz się, **jak odczytać kod kreskowy java** z dokumentu Word przy użyciu Aspose.BarCode for Java. Przejdziemy przez generowanie obrazu kodu kreskowego, dodawanie go do pliku Word, wyodrębnianie obrazów z dokumentu Word oraz ostateczne dekodowanie kodu kreskowego przy użyciu przykładu czytnika kodów kreskowych w Javie.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.BarCode for Java (z Aspose.Words do obsługi obrazów)  
- **Czy mogę dodać kod kreskowy do Worda?** Tak – najpierw wygeneruj obraz, a następnie wstaw go przy pomocy Aspose.Words  
- **Jak wyodrębnić obrazy z Worda?** Użyj `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Czy istnieje przykład czytnika kodów kreskowych w Javie?** Kod w Kroku 3 przedstawia kompletny przykład  
- **Jakie są wymagania wstępne?** JDK, Aspose.BarCode for Java, środowisko IDE (Eclipse/IntelliJ)

## Czym jest rozpoznawanie kodów kreskowych w Javie?
Rozpoznawanie kodów kreskowych w Javie odnosi się do procesu wykrywania i dekodowania symboli kodów kreskowych z obrazów lub dokumentów przy użyciu biblioteki takiej jak Aspose.BarCode. Umożliwia aplikacjom automatyczne odczytywanie kodów produktów, identyfikatorów magazynowych lub dowolnych zakodowanych danych bez ręcznego wprowadzania.

## Dlaczego odczytywać kod kreskowy java z dokumentów Word?
Osadzanie kodów kreskowych bezpośrednio w plikach Word jest przydatne w umowach, etykietach wysyłkowych czy raportach, gdzie wymagana jest wizualna reprezentacja kodu. Możliwość **wyodrębniania obrazów z Worda** i ich programowego dekodowania eliminuje potrzebę ręcznego skanowania i zmniejsza liczbę błędów.

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz:

- **Java Development Kit (JDK)** – zainstalowany na komputerze aktualny JDK.  
- **Aspose.BarCode for Java** – pobierz bibliotekę z oficjalnej strony [here](https://releases.aspose.com/barcode/java/).  
- **Zintegrowane Środowisko Programistyczne (IDE)** – takie jak Eclipse lub IntelliJ IDEA do pisania i uruchamiania kodu.

## Importowanie pakietów

W swoim projekcie Java zaimportuj niezbędne pakiety Aspose.BarCode i Aspose.Words:

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

## Krok 1: Wygeneruj obraz kodu kreskowego (generate barcode image java)

Najpierw utwórz obraz kodu kreskowego przy użyciu Aspose.BarCode. Ten obraz zostanie później **added barcode to word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Krok 2: Wstaw obraz kodu kreskowego do dokumentu Word (insert image into word)

Teraz użyjemy Aspose.Words, aby **insert image into word** i zapisać dokument:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Krok 3: Rozpoznaj kody kreskowe z dokumentu Word (java barcode reader example)

Na koniec wyodrębniamy każdy obraz z pliku Word i uruchamiamy **java barcode reader example**, aby zdekodować kod kreskowy:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Uwaga:** Pętla powyżej demonstruje **extract images from word**, zapisuje każdy obraz i następnie dekoduje kod kreskowy przy użyciu tej samej ścieżki pliku obrazu. Dostosuj ścieżki (`dataDir`) do swojego środowiska.

## Typowe problemy i wskazówki

- **Niezgodności ścieżek plików** – Upewnij się, że `dataDir` wskazuje na istniejący folder; w przeciwnym razie czytnik zgłosi `FileNotFoundException`.  
- **Nieobsługiwane typy kodów kreskowych** – Przykład używa `CODE_39_STANDARD`. Jeśli potrzebujesz QR, DataMatrix itp., zmień zarówno `EncodeTypes`, jak i `DecodeType` odpowiednio.  
- **Wydajność** – W przypadku dużych dokumentów rozważ przetwarzanie obrazów w równoległych strumieniach, aby przyspieszyć rozpoznawanie.

## Najczęściej zadawane pytania (FAQ)

### P: Czy mogę używać Aspose.BarCode for Java w projektach komercyjnych?
Tak, Aspose.BarCode for Java jest dostępny do użytku komercyjnego. Szczegóły licencjonowania znajdziesz [here](https://purchase.aspose.com/buy).

### P: Czy dostępna jest darmowa wersja próbna Aspose.BarCode for Java?
Tak, możesz wypróbować funkcje Aspose.BarCode for Java, pobierając darmową wersję próbną [here](https://releases.aspose.com/).

### P: Jak uzyskać wsparcie dla Aspose.BarCode for Java?
W razie potrzeby pomocy lub pytań odwiedź forum Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### P: Czy dostępne są tymczasowe licencje dla Aspose.BarCode for Java?
Tak, tymczasowe licencje można uzyskać [here](https://purchase.aspose.com/temporary-license/).

### P: Gdzie znajdę dokumentację Aspose.BarCode for Java?
Kompletną dokumentację znajdziesz [here](https://reference.aspose.com/barcode/java/).

## Dodatkowe FAQ

**P: Czy mogę odczytywać inne symbologie kodów kreskowych poza Code 39?**  
O: Oczywiście. Wystarczy zmienić `EncodeTypes` przy generowaniu oraz `DecodeType` przy odczycie, aby dopasować pożądaną symbologię (np. `EncodeTypes.QR`, `DecodeType.QR`).

**P: Czy to podejście działa również z plikami .docx?**  
O: Tak. Aspose.Words obsługuje zarówno formaty `.doc`, jak i `.docx` bez dodatkowych zmian; ten sam kod działa w obu przypadkach.

**P: Jak mogę poprawić dokładność rozpoznawania przy niskiej rozdzielczości obrazów?**  
O: Zwiększ DPI przy zapisywaniu obrazu kodu kreskowego (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) lub użyj formatu obrazu wyższej jakości, takiego jak PNG.

---

**Ostatnia aktualizacja:** 2025-12-19  
**Testowano z:** Aspose.BarCode for Java 24.11 oraz Aspose.Words for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}