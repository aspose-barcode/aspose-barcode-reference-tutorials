---
date: 2025-12-21
description: Dowiedz się, jak odczytywać obraz kodu kreskowego przy użyciu biblioteki
  Aspose.BarCode Java, obejmując generowanie kodu pdf417 w Javie oraz rozpoznawanie
  kodów Unicode.
linktitle: Recognizing Unicode Barcodes
second_title: Aspose.BarCode Java API
title: Jak odczytać obraz kodu kreskowego z kodami Unicode w Javie
url: /pl/java/document-barcode-recognition/recognizing-unicode-barcodes/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rozpoznawanie kodów kreskowych Unicode w Javie

## Wstęp

Jeśli potrzebujesz **jak odczytać obraz kodu kreskowego** w aplikacji Java, szczególnie gdy kod kreskowy zawiera znaki Unicode, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez każdy krok niezbędny do rozpoznania kodów kreskowych Unicode — takich jak arabski, chiński czy cyrylica — przy użyciu potężnej biblioteki Aspose.BarCode. Po zakończeniu będziesz w stanie generować i odczytywać te kody kreskowe z pewnością, rozszerzając zasięg swojego oprogramowania na globalną publiczność.

## Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do odczytu kodów kreskowych w Javie?** Aspose.BarCode for Java.
- **Czy mogę generować kody PDF417 z tekstem Unicode?** Tak, przy użyciu klasy `BarcodeGenerator`.
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.BarCode.
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze.
- **Czy dostępna jest wersja próbna?** Tak, możesz pobrać wersję próbną ze strony Aspose.

## Co oznacza „jak odczytać obraz kodu kreskowego” w Javie?

Odczyt obrazu kodu kreskowego oznacza dekodowanie wzoru wizualnego do pierwotnego ciągu danych. Gdy dane zawierają znaki Unicode, biblioteka musi poprawnie obsługiwać kodowanie i dekodowanie znaków, co Aspose.BarCode robi automatycznie po konwersji tekstu do odpowiedniego formatu kodowego.

## Dlaczego warto używać Aspose.BarCode do generowania kodów pdf417 w Javie?

Aspose.BarCode oferuje prosty interfejs API do **pdf417 barcode generation java**, obsługuje szeroką gamę symbologii i obsługuje kodowanie Unicode od razu. Dzięki temu jest idealny dla aplikacji klasy enterprise, które potrzebują niezawodnego i wydajnego przetwarzania kodów kreskowych.

## Wymagania wstępne

Zanim przejdziesz dalej, upewnij się, że masz:

- Praktyczną znajomość programowania w Javie.
- Bibliotekę Aspose.BarCode for Java zainstalowaną. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/java/).
- Ważną licencję na Aspose.BarCode. Możesz ją uzyskać [tutaj](https://purchase.aspose.com/buy).

## Importowanie pakietów

Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java. Biblioteka Aspose.BarCode zapewnia kompleksowy zestaw funkcji do generowania i rozpoznawania kodów kreskowych.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.IOException;
import java.io.UnsupportedEncodingException;
```

## Krok 1: Ustawienie katalogu zasobów

Zdefiniuj ścieżkę do katalogu zasobów.

```java
String dataDir = "Your Document Directory";
```

## Krok 2: Ustawienie licencji Aspose.BarCode

Wczytaj licencję Aspose.BarCode, aby odblokować pełny potencjał biblioteki.

```java
try {
    License lic = new License();
    lic.setLicense("aspose.barcode.lic");
} catch (Exception ex) {
    System.out.println(ex.getMessage());
}
```

## Krok 3: Generowanie kodu kreskowego Unicode

Utwórz kod kreskowy Unicode przy użyciu podanego tekstu.

```java
String file = dataDir + "pdf417_un.png";
String scodeText = "منحة";
System.out.println("codetext: " + scodeText);
String codeText = getCodeTextFromUnicode(scodeText);
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.PDF_417, codeText);
generator.save(file);
```

## Krok 4: Odczyt kodu kreskowego Unicode

Odczytaj wygenerowany kod kreskowy Unicode.

```java
BarCodeReader reader = new BarCodeReader(file, DecodeType.PDF_417);
for (BarCodeResult result : reader.readBarCodes()) {
    String rc = result.getCodeText();
    try {
        String s = getUnicodeFromCodeText(rc);
        System.out.println(s);
    } catch (UnsupportedEncodingException e) {
        e.printStackTrace();
    }
}
```

## Krok 5: Konwersja Unicode na tekst kodowy

Zaimplementuj metodę konwertującą Unicode na tekst kodowy.

```java
private static String getCodeTextFromUnicode(String s) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Krok 6: Konwersja tekstu kodowego na Unicode

Zaimplementuj metodę konwertującą tekst kodowy na Unicode.

```java
private static String getUnicodeFromCodeText(String cs) throws UnsupportedEncodingException {
    // Implementation details
}
```

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Zniekształcony wynik po odczycie | Nieprawidłowe kodowanie znaków | Upewnij się, że `getUnicodeFromCodeText` używa tego samego zestawu znaków (`UTF‑8`) co `getCodeTextFromUnicode`. |
| Czytnik zwraca `null` | Niepoprawny `DecodeType` | Użyj `DecodeType.PDF_417` dla kodów PDF417. |
| Licencja nie została zastosowana | Nieprawidłowa ścieżka do pliku licencji | Umieść `aspose.barcode.lic` w katalogu głównym projektu lub podaj pełną ścieżkę. |

## FAQ

### Czy wymagana jest licencja dla Aspose.BarCode?
Tak, wymagana jest ważna licencja dla Aspose.BarCode. Możesz ją uzyskać [tutaj](https://purchase.aspose.com/buy).

### Gdzie mogę znaleźć dokumentację Aspose.BarCode?
Dokumentacja jest dostępna [tutaj](https://reference.aspose.com/barcode/java/).

### Czy mogę wypróbować Aspose.BarCode za darmo?
Tak, darmową wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Jak uzyskać tymczasową licencję dla Aspose.BarCode?
Tymczasowe licencje można uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### Potrzebujesz wsparcia lub masz pytania?
Odwiedź [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Najczęściej zadawane pytania

**P: Czy mogę używać tego kodu z innymi symbologiami kodów kreskowych?**  
O: Oczywiście. Zmien `EncodeTypes.PDF_417` na dowolny obsługiwany typ, np. `EncodeTypes.CODE_128`, i dostosuj `DecodeType` odpowiednio.

**P: Co się stanie, jeśli tekst wejściowy zawiera emotikony?**  
O: Emotikony są znakami Unicode; zostaną poprawnie zakodowane, o ile metody konwersji obsługują UTF‑8.

**P: Czy istnieje sposób odczytu kodów kreskowych ze strumienia zamiast z pliku?**  
O: Tak, `BarCodeReader` akceptuje również `InputStream` jako pierwszy argument.

**P: Jak mogę przyspieszyć rozpoznawanie przy dużych partiach?**  
O: Ponownie używaj jednej instancji `BarCodeReader` i przetwarzaj obrazy w pętli, szybko zwalniając każdy wynik.

**P: Czy Aspose.BarCode obsługuje wielostronicowe pliki PDF do ekstrakcji kodów kreskowych?**  
O: Tak. Użyj `BarCodeReader` z ścieżką do pliku PDF; biblioteka automatycznie przeiteruje wszystkie strony.

## Zakończenie

Gratulacje! Opanowałeś **jak odczytać obraz kodu kreskowego** w Javie przy użyciu Aspose.BarCode, od generowania kodu PDF417 Unicode po jego dekodowanie do pierwotnego tekstu. Ta możliwość otwiera drzwi do aplikacji internacjonalizowanych, wielojęzycznych systemów inwentaryzacji i wszelkich scenariuszy wymagających globalnych zestawów znaków.

---

**Ostatnia aktualizacja:** 2025-12-21  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}