---
title: Generowanie wielu kodów kreskowych na jednym obrazie w Javie za pomocą Aspose.BarCode
linktitle: Generowanie wielu kodów kreskowych na jednym obrazie
second_title: Aspose.BarCode API Java
description: Bez wysiłku generuj wiele kodów kreskowych na jednym obrazie, używając Aspose.BarCode dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 19
url: /pl/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## Wstęp

W dynamicznym świecie programowania w języku Java efektywne tworzenie kodów kreskowych i zarządzanie nimi ma kluczowe znaczenie w różnych zastosowaniach. Aspose.BarCode dla Java upraszcza ten proces, umożliwiając programistom płynne generowanie wielu kodów kreskowych na jednym obrazie. Ten samouczek poprowadzi Cię przez kolejne kroki, aby to osiągnąć, używając Aspose.BarCode w środowisku Java.

## Warunki wstępne

Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:

- Podstawowa znajomość programowania w języku Java.
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Pobrano i skonfigurowano bibliotekę Aspose.BarCode dla Java. Możesz go pobrać[Tutaj](https://releases.aspose.com/barcode/java/).
- Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA.

## Importuj przestrzenie nazw

W projekcie Java zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.BarCode. Dodaj następujące instrukcje importu na początku klasy Java:

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

Zdefiniuj ścieżkę do katalogu zasobów, w którym będą zapisywane wygenerowane kody kreskowe. Ten katalog ma kluczowe znaczenie dla organizowania i zarządzania obrazami kodów kreskowych.

```java
// Ścieżka do katalogu zasobów.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Utwórz kolekcję kodów kreskowych

Zainicjuj HashMap, aby przechowywać dane kodu kreskowego. Każdy wpis w kolekcji reprezentuje kod kreskowy z odpowiednim typem kodowania.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 3: Wygeneruj obrazy kodów kreskowych

Iteruj po kolekcji i generuj obrazy kodów kreskowych przy użyciu biblioteki Aspose.BarCode. Przechowuj obrazy w ArrayList w celu dalszego przetwarzania.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 4: Utwórz połączony obraz

Określ maksymalną szerokość i całkowitą wysokość obrazów kodów kreskowych. Utwórz BufferedImage, aby połączyć poszczególne obrazy kodów kreskowych w jeden obraz wyjściowy.

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

## Wniosek

Gratulacje! Pomyślnie wygenerowałeś wiele kodów kreskowych na jednym obrazie przy użyciu Aspose.BarCode for Java. Ta potężna biblioteka upraszcza obsługę kodów kreskowych, co czyni ją nieocenionym narzędziem dla programistów Java.

## Często zadawane pytania

### P1: Czy mogę dostosować wygląd poszczególnych kodów kreskowych na wygenerowanym obrazie?

O1: Tak, Aspose.BarCode zapewnia szerokie możliwości dostosowywania wyglądu kodów kreskowych, umożliwiając dostosowanie stylu każdego kodu kreskowego do własnych preferencji.

### P2: Czy Aspose.BarCode jest kompatybilny z różnymi symbolikami kodów kreskowych?

A2: Absolutnie! Aspose.BarCode obsługuje szeroką gamę symboli, w tym CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 i AZTEC, jak pokazano w tym samouczku.

### P3: Jak mogę zintegrować Aspose.BarCode z moim projektem Java?

 O3: Po prostu pobierz bibliotekę Aspose.BarCode dla Java z[Tutaj](https://releases.aspose.com/barcode/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

### P4: Czy mogę używać Aspose.BarCode do zastosowań komercyjnych?

 A4: Tak, możesz uzyskać licencję od[Tutaj](https://purchase.aspose.com/buy) używać Aspose.BarCode w celach komercyjnych.

### P5: Czy dostępne są opcje próbne dla Aspose.BarCode?

 A5: Oczywiście! Możesz poznać funkcje Aspose.BarCode, uzyskując bezpłatną licencję próbną[Tutaj](https://releases.aspose.com/).