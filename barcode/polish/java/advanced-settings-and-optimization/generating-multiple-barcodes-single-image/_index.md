---
date: 2026-10-19
description: Dowiedz się, jak utworzyć QR code java i generować multiple barcodes
  na pojedynczym obrazie przy użyciu Aspose.BarCode for Java. Zawiera konfigurację,
  kod i rozwiązywanie problemów.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Generowanie multiple barcodes na pojedynczym obrazie
og_description: Utwórz QR code java i połącz kilka typów barcode w jednym obrazie
  przy użyciu Aspose.BarCode for Java. Postępuj zgodnie z przewodnikiem krok po kroku,
  zobacz fragmenty kodu i poznaj wskazówki dotyczące rozwiązywania problemów.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Utwórz QR code java – generuj multiple barcodes na jednym obrazie
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Utwórz QR code java – generuj multiple barcodes na jednym obrazie
url: /pl/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod QR w Javie – generuj wiele kodów kreskowych na jednym obrazie

## Wprowadzenie

W tym samouczku nauczysz się **jak utworzyć kod QR w Javie** i połączyć kilka różnych typów kodów kreskowych na jednej płaszczyźnie przy użyciu **Aspose.BarCode for Java**. Niezależnie od tego, czy potrzebujesz kompaktowej etykiety QR, kodu kreskowego produktu, czy mieszanki symbologii 2‑D i liniowych, ten przewodnik poprowadzi Cię przez każdy krok — od konfiguracji projektu po zapisanie ostatecznego połączonego obrazu — abyś mógł od razu rozpocząć integrację generowania kodów kreskowych w swoich aplikacjach Java.

## Szybkie odpowiedzi
- **Jakiej biblioteki powinienem używać?** Aspose.BarCode for Java zapewnia najbardziej kompletny zestaw symbologii.  
- **Czy mogę generować różne typy kodów kreskowych razem?** Tak, możesz mieszać CODE_39, QR, AZTEC i inne na jednej płaszczyźnie.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja komercyjna jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** Java 8 i nowsze są w pełni kompatybilne.  
- **Czy format wyjściowy jest konfigurowalny?** Możesz wyeksportować połączony obraz jako PNG, JPEG, BMP lub TIFF.

## Co to jest create QR code java?

`create QR code java` odnosi się do procesu przekształcania ciągu tekstowego w dwuwymiarową macierz, którą można skanować smartfonami lub czytnikami kodów kreskowych. Aspose.BarCode for Java wykonuje kodowanie i renderowanie, dzięki czemu możesz skupić się na logice biznesowej, a nie na obsłudze obrazu na poziomie pikseli.

## Dlaczego używać Aspose.BarCode Java do generowania kodów kreskowych w Javie?

Aspose.BarCode obsługuje **ponad 50 symbologii kodów kreskowych** — w tym QR, Data Matrix, Code 128, AZTEC i tradycyjne kody liniowe — co czyni go najbardziej wszechstronną biblioteką kodów kreskowych w Javie. Renderuje **obrazy antyaliasowane z rozdzielczością do 1200 dpi**, zapewniając wyraźne skany na ekranie i w druku. API wymaga jedynie JVM i oferuje płynny model konfiguracji, umożliwiający dostosowanie rozmiaru, koloru, marginesów i korekcji błędów w kilku linijkach kodu.

## Wymagania wstępne

- Solidna znajomość podstaw Javy.  
- Zainstalowany JDK 8 lub nowszy, skonfigurowany w zmiennej PATH.  
- Plik JAR Aspose.BarCode for Java (pobierz ze strony oficjalnej pobierania Aspose.BarCode for Java).  
- IDE, takie jak IntelliJ IDEA lub Eclipse, do edycji i uruchamiania przykładu.

## Importowanie przestrzeni nazw

Instrukcje importu wprowadzają klasy Aspose.BarCode, takie jak `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`, do zakresu, umożliwiając odwoływanie się do nich bez pełnych nazw kwalifikowanych.  
`BarcodeGenerator` jest główną klasą używaną do konfigurowania i generowania obrazów kodów kreskowych.  
`EncodeTypes` jest wyliczeniem w Aspose.BarCode, które określa symbologię kodu kreskowego do wygenerowania.  
`BarCodeImageFormat` definiuje format wyjściowego obrazu dla wygenerowanego kodu kreskowego.

## Krok 1: ustaw katalog zasobów

**Katalog zasobów** to folder w systemie plików, w którym będą zapisywane wszystkie wygenerowane obrazy kodów kreskowych. Zdefiniowanie go raz utrzymuje projekt w porządku i ułatwia usuwanie starych plików.

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

## Krok 2: utwórz kolekcję kodów kreskowych

`HashMap<String, EncodeTypes>` przechowuje ciąg danych każdego kodu kreskowego wraz z symbologią, której chcesz użyć. `HashMap` jest kolekcją Javy mapującą klucze na wartości. Ta kolekcja napędza pętlę generowania, która następuje. `EncodeTypes` jest wyliczeniem określającym, jaki typ kodu kreskowego wygenerować.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 3: generuj obrazy kodów kreskowych

Pętla generująca iteruje po `HashMap`, tworzy `BarcodeGenerator` dla każdego wpisu i wywołuje `generateBarCodeImage()`, aby uzyskać `BufferedImage`. `generateBarCodeImage()` tworzy `BufferedImage` zawierający wyrenderowany kod kreskowy. `BufferedImage` jest klasą Javy reprezentującą obraz w pamięci. Wszystkie obrazy są dodawane do `ArrayList<BufferedImage>` w celu późniejszego łączenia. `ArrayList` jest implementacją listy o zmiennym rozmiarze w Javie.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 4: utwórz połączony obraz

Najpierw algorytm oblicza **maksymalną szerokość** spośród wszystkich obrazów kodów kreskowych oraz **całkowitą wysokość** potrzebną do ich pionowego ułożenia z opcjonalnym odstępem. Następnie tworzy `BufferedImage` o tym rozmiarze i rysuje każdy kod kreskowy na płótnie przy użyciu obiektu `Graphics2D`. `Graphics2D` jest klasą Javy zapewniającą możliwości renderowania 2D do rysowania kształtów i obrazów.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 5: zapisz wynik

Na koniec połączony obraz jest zapisywany na dysku przy użyciu `ImageIO.write`, w formacie, który określiłeś (PNG, JPEG, BMP lub TIFF). `ImageIO.write` zapisuje `BufferedImage` do pliku w wybranym formacie. Ścieżka pliku jest względna względem wcześniej zdefiniowanego katalogu zasobów.

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

## Typowe przypadki użycia generowania wielu kodów kreskowych

- **Etykiety opakowań** – połącz kod produktu, partii i wysyłki na jednej etykiecie, aby obniżyć koszty druku.  
- **Bilety na wydarzenia** – osadź identyfikatory QR, Data Matrix i Code 128 dla różnych stanowisk skanowania na miejscu.  
- **Zarządzanie zapasami** – wyświetl jednocześnie SKU, dane tagu RFID i numery seryjne, aby szybko przeprowadzić audyt i zapewnić śledzenie.

## Rozwiązywanie problemów i wskazówki

- **Problemy z rozmiarem obrazu** – dostosuj zmienną `offset`, aby zwiększyć lub zmniejszyć odstęp między kodami kreskowymi.  
- **Nieobsługiwana symbologia** – sprawdź, czy Twoja wersja Aspose.BarCode obsługuje żądany typ kodu kreskowego; nowsze wydania dodają dodatkowe kody 2‑D.  
- **Wydajność** – ponownie używaj jednego obiektu `Graphics2D` przy generowaniu wielu obrazów w pętli, aby zminimalizować narzut alokacji obiektów.  

## Najczęściej zadawane pytania

**Q: Czy mogę dostosować wygląd poszczególnych kodów kreskowych w wygenerowanym obrazie?**  
A: Tak. Użyj właściwości `BarcodeGenerator`, takich jak `setBarColor`, `setBackgroundColor` i `setXDimension`, aby stylizować każdy kod kreskowy niezależnie przed dodaniem go do płótna.

**Q: Czy Aspose.BarCode jest kompatybilny z różnymi symbologiami kodów kreskowych?**  
A: Zdecydowanie tak. Biblioteka obsługuje ponad 50 symbologii, w tym CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 i AZTEC, co zostało pokazane w tym samouczku.

**Q: Jak zintegrować Aspose.BarCode z moim projektem Java?**  
A: Pobierz plik JAR ze strony pobierania biblioteki Aspose.BarCode for Java, dodaj go do classpath projektu i zaimportuj wymagane przestrzenie nazw, jak pokazano w sekcji „Importowanie przestrzeni nazw”.

**Q: Czy mogę używać Aspose.BarCode w aplikacjach komercyjnych?**  
A: Tak. Kup licencję na stronie zakupu licencji Aspose.BarCode, aby usunąć ograniczenia wersji próbnej i uzyskać pełne wsparcie produkcyjne.

**Q: Czy dostępne są opcje wersji próbnej dla Aspose.BarCode?**  
A: Oczywiście. Bezpłatna licencja próbna jest dostępna na stronie pobierania wersji próbnej Aspose.BarCode, zapewniając pełny dostęp do API w celu oceny.

**Q: Jak wygenerować wysokiej rozdzielczości kod QR do druku?**  
A: Ustaw właściwość `setResolutionDpi` w `BarcodeGenerator` przed wywołaniem `generateBarCodeImage()`, a następnie zapisz wynik w formacie bezstratnym, takim jak PNG.

**Q: Co zrobić, gdy połączony obraz jest przycięty?**  
A: Sprawdź, czy obliczenia `offset` i rozmiaru płótna prawidłowo uwzględniają wszystkie wysokości kodów kreskowych; zwiększenie wysokości płótna lub zmniejszenie rozmiarów poszczególnych kodów kreskowych rozwiązuje większość problemów z przycinaniem.

---

**Ostatnia aktualizacja:** 2026-10-19  
**Testowano z:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Powiązane samouczki

- [Jak utworzyć obraz kodu kreskowego w Javie – Dodaj obramowanie z Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Jak generować kod kreskowy w Javie: zapisywać do strumieni z Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Jak generować kod kreskowy w Javie i drukować kod kreskowy z Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}