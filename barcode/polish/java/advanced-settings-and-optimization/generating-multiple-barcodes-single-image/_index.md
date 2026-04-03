---
date: 2026-04-03
description: Dowiedz się, jak tworzyć kody QR w Javie i generować wiele kodów kreskowych
  na jednym obrazie przy użyciu Aspose.BarCode for Java. Zawiera konfigurację, kod
  oraz rozwiązywanie problemów.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Generowanie wielu kodów kreskowych na jednym obrazie
second_title: Aspose.BarCode Java API
title: Tworzenie kodu QR w Javie – Generowanie wielu kodów kreskowych na jednym obrazie
url: /pl/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod QR w Javie – Generowanie wielu kodów kreskowych na jednym obrazie

## Wprowadzenie

W tym samouczku nauczysz się **jak tworzyć kod QR w Javie** i łączyć kilka różnych typów kodów kreskowych na jednym obrazie przy użyciu **Aspose.BarCode for Java**. Niezależnie od tego, czy potrzebujesz kompaktowej etykiety QR, kodu kreskowego produktu, czy mieszanki symbologii 2‑D i liniowych, ten przewodnik przeprowadzi Cię przez każdy krok — od konfiguracji projektu po zapisanie ostatecznego połączonego obrazu — abyś mógł od razu rozpocząć integrowanie generowania kodów kreskowych w swoich aplikacjach Java.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.BarCode for Java zapewnia najbardziej kompletny zestaw symbologii.  
- **Czy mogę generować różne typy kodów kreskowych razem?** Tak, możesz mieszać CODE_39, QR, AZTEC i inne na jednym płótnie.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Która wersja Javy jest wspierana?** Java 8 i nowsze są w pełni kompatybilne.  
- **Czy format wyjściowy jest konfigurowalny?** Możesz wyeksportować połączony obraz jako PNG, JPEG, BMP itp.  

## Co to jest tworzenie kodu QR w Javie?

Tworzenie kodu QR w Javie oznacza konwersję ciągu tekstowego na dwuwymiarową macierz, którą mogą skanować smartfony lub czytniki kodów kreskowych. **Aspose.BarCode for Java** obsługuje kodowanie i renderowanie, pozwalając skupić się na logice biznesowej zamiast na niskopoziomowym przetwarzaniu obrazu.

## Dlaczego warto używać Aspose.BarCode Java do generowania kodów kreskowych w Javie?

- **Szerokie wsparcie symbologii** – od klasycznych kodów liniowych po nowoczesne macierze 2‑D.  
- **Renderowanie wysokiej jakości** – wyjście z antyaliasingiem, które działa na każdym urządzeniu.  
- **Proste API** – tworzenie, dostosowywanie i łączenie kodów kreskowych za pomocą kilku wywołań metod.  
- **Brak zewnętrznych zależności** – wszystko działa na JVM bez bibliotek natywnych.  

## Wymagania wstępne

- Podstawowa znajomość programowania w Javie.  
- Zainstalowany Java Development Kit (JDK) na Twoim systemie.  
- Biblioteka Aspose.BarCode for Java pobrana i skonfigurowana. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/java/).  
- Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA.

## Importowanie przestrzeni nazw

W swoim projekcie Java zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.BarCode. Dodaj następujące instrukcje importu na początku swojej klasy Java:

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

Zdefiniuj ścieżkę do katalogu zasobów, w którym będą zapisywane wygenerowane kody kreskowe. Ten katalog jest kluczowy dla organizacji i zarządzania obrazami kodów kreskowych.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Utwórz kolekcję kodów kreskowych

Zainicjalizuj `HashMap`, aby przechowywać dane kodów kreskowych. Każdy wpis w kolekcji reprezentuje kod kreskowy wraz z odpowiednim typem kodowania.

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

Iteruj przez kolekcję i generuj obrazy kodów kreskowych przy użyciu biblioteki Aspose.BarCode. Przechowuj obrazy w `ArrayList` do dalszego przetwarzania.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 4: Utwórz połączony obraz

Określ maksymalną szerokość i całkowitą wysokość obrazów kodów kreskowych. Utwórz `BufferedImage`, aby połączyć poszczególne obrazy kodów kreskowych w jeden obraz wyjściowy.

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

Zapisz ostateczny połączony obraz w określonej lokalizacji pliku.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Typowe przypadki użycia generowania wielu kodów kreskowych

- **Etykiety opakowań** – łącz produkt, partię i kody wysyłkowe na jednej etykiecie.  
- **Bilety na wydarzenia** – osadź identyfikatory QR, Data Matrix i Code 128 dla różnych stanowisk skanowania.  
- **Zarządzanie zapasami** – wyświetl SKU, dane tagu RFID i numery seryjne razem dla szybkiego audytu.

## Rozwiązywanie problemów i wskazówki

- **Problemy z rozmiarem obrazu** – dostosuj zmienną `offset`, aby zwiększyć lub zmniejszyć odstępy między kodami kreskowymi.  
- **Nieobsługiwana symbologia** – sprawdź, czy Twoja wersja Aspose.BarCode obsługuje żądany typ kodu kreskowego.  
- **Wydajność** – ponownie używaj jednego obiektu `Graphics`, jeśli generujesz wiele obrazów w pętli.

## Najczęściej zadawane pytania

**Q1: Czy mogę dostosować wygląd poszczególnych kodów kreskowych w wygenerowanym obrazie?**  
A1: Tak, Aspose.BarCode oferuje rozbudowane opcje dostosowywania wyglądu kodów kreskowych, umożliwiając dopasowanie stylu każdego kodu do Twoich preferencji.

**Q2: Czy Aspose.BarCode jest kompatybilny z różnymi symbologiami kodów kreskowych?**  
A2: Zdecydowanie! Aspose.BarCode obsługuje szeroką gamę symbologii, w tym CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 i AZTEC, co zostało przedstawione w tym samouczku.

**Q3: Jak mogę zintegrować Aspose.BarCode w moim projekcie Java?**  
A3: Wystarczy pobrać bibliotekę Aspose.BarCode for Java z [tutaj](https://releases.aspose.com/barcode/java/) i postępować zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

**Q4: Czy mogę używać Aspose.BarCode w aplikacjach komercyjnych?**  
A4: Tak, możesz uzyskać licencję z [tutaj](https://purchase.aspose.com/buy), aby używać Aspose.BarCode do celów komercyjnych.

**Q5: Czy dostępne są opcje wersji próbnej Aspose.BarCode?**  
A5: Oczywiście! Możesz zapoznać się z funkcjami Aspose.BarCode, uzyskując darmową licencję próbną [tutaj](https://releases.aspose.com/).

**Q6: Jak wygenerować wysokiej rozdzielczości kod QR do druku?**  
A6: Ustaw żądane DPI w `BarcodeGenerator` przed wywołaniem `generateBarCodeImage()`, a następnie zapisz obraz w formacie bezstratnym, takim jak PNG.

**Q7: Co zrobić, gdy połączony obraz jest przycięty?**  
A7: Sprawdź, czy obliczenia `offset` i rozmiaru płótna prawidłowo uwzględniają wszystkie wysokości kodów kreskowych; zwiększenie wysokości płótna lub zmniejszenie rozmiarów poszczególnych kodów rozwiązuje większość problemów z przycinaniem.

---

**Ostatnia aktualizacja:** 2026-04-03  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}