---
date: 2026-04-08
description: Dowiedz się, jak odczytać kod kreskowy z pliku PDF w Javie przy użyciu
  Aspose.BarCode. Ten przewodnik pokazuje również, jak generować obraz kodu kreskowego
  w Javie oraz wyodrębniać obrazy z pliku PDF w Javie.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Rozpoznawanie kodów kreskowych z PDF
second_title: Aspose.BarCode Java API
title: Jak odczytać kod kreskowy z PDF w Javie przy użyciu Aspose.BarCode
url: /pl/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# odczytaj kod kreskowy z pdf w java

## Wprowadzenie

Witamy w naszym przewodniku krok po kroku, jak **odczytać kod kreskowy z PDF w Javie** przy użyciu Aspose.BarCode. Kody kreskowe są niezbędne do automatyzacji przechwytywania danych, a dzięki Aspose.BarCode możesz je bezproblemowo wykrywać w dokumentach PDF. W tym samouczku przeprowadzimy Cię przez wszystko, czego potrzebujesz — od konfiguracji licencji po generowanie obrazu kodu kreskowego Java, dodawanie go do PDF, wyodrębnianie obrazów z PDF Java oraz ostateczne odczytanie kodu kreskowego.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Czy mogę wygenerować obraz kodu kreskowego w Javie?** Tak – klasa `BarcodeGenerator` pozwala tworzyć obrazy PNG/JPEG.  
- **Jak wyodrębnić obrazy z PDF?** Użyj `PdfExtractor` z Aspose.PDF.  
- **Jaki typ kodu kreskowego jest pokazany?** CODE‑39 (standardowy).  
- **Czy potrzebna jest licencja?** Wymagana jest ważna licencja Aspose.BarCode i Aspose.PDF do użytku produkcyjnego.

## Dlaczego warto używać Aspose.BarCode dla Javy?
- **Wysoka dokładność** – obsługuje dziesiątki symbologii i działa na obrazach o niskiej rozdzielczości.  
- **Brak zewnętrznych zależności** – czysta Java, bez bibliotek natywnych.  
- **Pełna integracja z PDF** – połącz z Aspose.PDF, aby odczytywać lub osadzać kody kreskowe bezpośrednio w plikach PDF.

## Wymagania wstępne

Przed przystąpieniem do kodu upewnij się, że masz:

1. **Licencja Aspose.BarCode for Java** – uzyskaj ją z [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Licencja Aspose.PDF** – wymagana do manipulacji PDF; możesz ubiegać się o licencję [tutaj](https://purchase.aspose.com/temporary-license/).  
3. **Biblioteka Aspose.BarCode** – pobierz najnowszy plik JAR z [tutaj](https://releases.aspose.com/barcode/java/).  

Teraz, gdy masz wszystkie niezbędne elementy, zaimportuj wymagane pakiety i rozpocznij kodowanie.

## Importowanie pakietów

W swoim projekcie Java dodaj importy Aspose.BarCode i Aspose.PDF. Ten blok pozostaje niezmieniony w stosunku do oryginalnego samouczka:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Krok 1: Wygeneruj obraz kodu kreskowego Java

Najpierw tworzymy obraz kodu kreskowego, który później osadzimy w PDF. Demonstracja możliwości **generate barcode image java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Krok 2: Utwórz PDF i dodaj obraz kodu kreskowego

Następnie budujemy nowy dokument PDF i wstawiamy wygenerowany obraz kodu kreskowego.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Krok 3: Wyodrębnij obrazy z PDF Java

Po przygotowaniu PDF musimy wyciągnąć osadzony obraz, aby móc odczytać kod kreskowy. To wykorzystuje **extract images from pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Krok 4: Rozpoznaj kod kreskowy z wyodrębnionych obrazów

Na koniec przekazujemy każdy wyodrębniony obraz do `BarCodeReader`, aby uzyskać zakodowany tekst.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Powtarzaj te kroki w razie potrzeby, dostosowując nazwy plików i ścieżki do struktury swojego projektu.

## Typowe problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|-------|--------|-----|
| **Nie wykryto kodu kreskowego** | Jakość obrazu zbyt niska lub kod kreskowy za mały. | Zwiększ rozdzielczość obrazu przy zapisie (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` zgłasza wyjątek** | Plik PDF nie został znaleziony lub ścieżka jest nieprawidłowa. | Sprawdź, czy `strPdfDoc` wskazuje na istniejący plik i czy aplikacja ma uprawnienia do odczytu. |
| **Licencja nie zastosowana** | Komponenty Aspose działają w trybie próbnym, ograniczając wyniki. | Załaduj pliki licencji na początku programu: `new License().setLicense("Aspose.BarCode.lic");` i analogicznie dla Aspose.PDF. |

## Najczęściej zadawane pytania (FAQ)

### Q: Czy mogę używać Aspose.BarCode dla Javy bez licencji?
Chociaż Aspose.BarCode może być używany bez licencji, zaleca się jej uzyskanie, aby uzyskać pełną funkcjonalność i spełnić warunki licencyjne.

### Q: Jak mogę uzyskać tymczasową licencję dla Aspose.BarCode dla Javy?
Możesz uzyskać tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

### Q: Czy istnieją ograniczenia dotyczące typów kodów kreskowych obsługiwanych przez Aspose.BarCode?
Aspose.BarCode obsługuje szeroką gamę typów kodów kreskowych. Zapoznaj się z dokumentacją, aby zobaczyć pełną listę.

### Q: Czy dostępna jest wersja próbna Aspose.BarCode dla Javy?
Tak, wersję próbną możesz pobrać [tutaj](https://releases.aspose.com/).

### Q: Gdzie mogę uzyskać wsparcie lub zadać pytania dotyczące Aspose.BarCode dla Javy?
Odwiedź forum Aspose.BarCode [tutaj](https://forum.aspose.com/c/barcode/13), aby uzyskać wsparcie i dyskusje.

## Zakończenie

Gratulacje! Nauczyłeś się, jak **odczytać kod kreskowy z PDF w Javie** przy użyciu Aspose.BarCode, jak **wygenerować obraz kodu kreskowego Java**, oraz jak **wyodrębnić obrazy z PDF Java** do dalszego przetwarzania. Zachęcamy do eksploracji dodatkowych funkcji, takich jak przetwarzanie wsadowe, obsługa różnych symbologii kodów kreskowych czy integracja z innymi produktami Aspose. Po więcej szczegółów sprawdź oficjalną [dokumentację](https://reference.aspose.com/barcode/java/).

---

**Ostatnia aktualizacja:** 2026-04-08  
**Testowano z:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}