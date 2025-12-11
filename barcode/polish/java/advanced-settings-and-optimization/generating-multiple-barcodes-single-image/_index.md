---
date: 2025-12-10
description: Dowiedz się, jak generować kody kreskowe na jednym obrazie w Javie przy
  użyciu Aspose.BarCode. Ten przewodnik obejmuje integrację Aspose.BarCode w Javie
  oraz generowanie wielu kodów kreskowych.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Jak generować kody kreskowe na jednym obrazie w Javie
url: /pl/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie wielu kodów kreskowych na jednym obrazie w Javie z Aspose.BarCode

## Wprowadzenie

Jeśli szukasz niezawodnego sposobu **jak generować kody kreskowe** w aplikacji Java, trafiłeś we właściwe miejsce. Dzięki Aspose.BarCode for Java możesz umieścić kilka różnych typów kodów kreskowych na jednym obrazie w zaledwie kilku linijkach kodu. Ten samouczek przeprowadzi Cię przez cały proces — od konfiguracji projektu po zapisanie połączonego obrazu — abyś od razu mógł rozpocząć korzystanie z generowania kodów kreskowych w własnych rozwiązaniach.

## Szybkie odpowiedzi
- **Jaką bibliotekę powinienem używać?** Aspose.BarCode for Java zapewnia najpełniejszy zestaw symbologii.  
- **Czy mogę generować różne typy kodów kreskowych razem?** Tak, możesz mieszać CODE_39, QR, AZTEC i inne na jednej płaszczyźnie.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarczy do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze są w pełni kompatybilne.  
- **Czy format wyjściowy jest konfigurowalny?** Możesz eksportować połączony obraz jako PNG, JPEG, BMP itp.

## Co oznacza „jak generować kody kreskowe” w Javie?
Generowanie kodów kreskowych to przekształcanie ciągu danych w wizualny wzór, który skanery potrafią odczytać. Aspose.BarCode zajmuje się kodowaniem, renderowaniem i tworzeniem obrazu automatycznie, pozwalając Ci skupić się na logice biznesowej, a nie na niskopoziomowej obróbce grafiki.

## Dlaczego warto używać Aspose.BarCode for Java do generowania kodów kreskowych?
- **Szerokie wsparcie symbologii** – od klasycznych kodów liniowych po nowoczesne macierze 2‑D.  
- **Renderowanie wysokiej jakości** – wyjście antyaliasowane, działające na każdym urządzeniu.  
- **Proste API** – twórz, dostosowuj i łącz kody kreskowe za pomocą kilku wywołań metod.  
- **Brak zewnętrznych zależności** – wszystko działa na JVM bez bibliotek natywnych.

## Wymagania wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania:

- Podstawowa znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK).  
- Biblioteka Aspose.BarCode for Java pobrana i skonfigurowana. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/java/).  
- Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA.

## Import Namespaces

W swoim projekcie Java zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.BarCode. Dodaj następujące instrukcje importu na początku klasy Java:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Krok 1: Ustaw katalog zasobów

Zdefiniuj ścieżkę do katalogu zasobów, w którym będą zapisywane wygenerowane kody kreskowe. Ten katalog jest kluczowy dla organizacji i zarządzania obrazami kodów.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Utwórz kolekcję kodów kreskowych

Zainicjuj `HashMap`, aby przechowywać dane kodów kreskowych. Każdy wpis w kolekcji reprezentuje kod kreskowy wraz z odpowiednim typem kodowania.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 3: Generuj obrazy kodów kreskowych

Iteruj po kolekcji i generuj obrazy kodów kreskowych przy użyciu biblioteki Aspose.BarCode. Przechowuj obrazy w `ArrayList` do dalszego przetwarzania.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 4: Utwórz połączony obraz

Określ maksymalną szerokość i całkowitą wysokość obrazów kodów kreskowych. Utwórz `BufferedImage`, aby połączyć poszczególne obrazy w jeden wynikowy obraz.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Krok 5: Zapisz wynik

Zapisz finalny połączony obraz w określonej lokalizacji pliku.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Typowe scenariusze użycia generowania wielu kodów kreskowych

- **Etykiety opakowań** – łącz produkt, partię i kody wysyłkowe na jednej etykiecie.  
- **Bilety na wydarzenia** – osadź QR, Data Matrix i identyfikatory Code 128 dla różnych punktów skanowania.  
- **Zarządzanie zapasami** – wyświetl jednocześnie SKU, dane tagu RFID i numery seryjne dla szybkiego audytu.

## Rozwiązywanie problemów i wskazówki

- **Problemy z rozmiarem obrazu** – dostosuj zmienną `offset`, aby zwiększyć lub zmniejszyć odstępy między kodami kreskowymi.  
- **Nieobsługiwana symbologia** – sprawdź, czy Twoja wersja Aspose.BarCode obsługuje żądany typ kodu.  
- **Wydajność** – ponownie używaj jednego obiektu `Graphics`, jeśli generujesz wiele obrazów w pętli.

## FAQ

### Q1: Czy mogę dostosować wygląd poszczególnych kodów kreskowych w wygenerowanym obrazie?

A1: Tak, Aspose.BarCode oferuje rozbudowane opcje personalizacji wyglądu kodu, pozwalając dopasować styl każdego kodu do własnych preferencji.

### Q2: Czy Aspose.BarCode jest kompatybilny z różnymi symbologiami kodów kreskowych?

A2: Oczywiście! Aspose.BarCode obsługuje szeroką gamę symbologii, w tym CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 i AZTEC, co zostało zaprezentowane w tym samouczku.

### Q3: Jak mogę zintegrować Aspose.BarCode w moim projekcie Java?

A3: Po prostu pobierz bibliotekę Aspose.BarCode for Java z [tutaj](https://releases.aspose.com/barcode/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

### Q4: Czy mogę używać Aspose.BarCode w aplikacjach komercyjnych?

A4: Tak, możesz uzyskać licencję z [tutaj](https://purchase.aspose.com/buy), aby korzystać z Aspose.BarCode w celach komercyjnych.

### Q5: Czy dostępne są opcje wersji próbnej Aspose.BarCode?

A5: Z pewnością! Możesz wypróbować funkcje Aspose.BarCode, uzyskując darmową licencję próbną [tutaj](https://releases.aspose.com/).

**Dodatkowe pytania**

**Q: Jak wygenerować kod QR konkretnie w Javie?**  
A: Użyj `EncodeTypes.QR` przy tworzeniu instancji `BarcodeGenerator`, jak pokazano w przykładzie kolekcji.

**Q: Czy Aspose.BarCode obsługuje wyjście w wysokiej rozdzielczości do druku?**  
A: Tak, możesz określić DPI przy zapisywaniu obrazu, aby spełnić wymagania jakości druku.

---

**Ostatnia aktualizacja:** 2025-12-10  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}