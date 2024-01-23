---
title: Generování více čárových kódů na jednom obrázku v Javě pomocí Aspose.BarCode
linktitle: Generování více čárových kódů na jednom obrázku
second_title: Aspose.BarCode Java API
description: Vygenerujte více čárových kódů na jednom obrázku bez námahy pomocí Aspose.BarCode pro Java. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 19
url: /cs/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---
## Úvod

V dynamickém světě programování v jazyce Java je efektivní vytváření a správa čárových kódů pro různé aplikace zásadní. Aspose.BarCode for Java tento proces zjednodušuje a umožňuje vývojářům bezproblémově generovat více čárových kódů na jednom obrázku. Tento tutoriál vás provede kroky, jak toho dosáhnout pomocí Aspose.BarCode v prostředí Java.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

- Základní znalost programování v Javě.
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Knihovna Aspose.BarCode pro Java byla stažena a nastavena. Můžete si jej stáhnout[tady](https://releases.aspose.com/barcode/java/).
- Integrované vývojové prostředí (IDE), jako je Eclipse nebo IntelliJ IDEA.

## Importovat jmenné prostory

Do svého projektu Java importujte potřebné jmenné prostory pro přístup k funkci Aspose.BarCode. Na začátek třídy Java přidejte následující příkazy importu:

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

## Krok 1: Nastavte Resource Directory

Definujte cestu ke zdrojovému adresáři, kam se budou ukládat vygenerované čárové kódy. Tento adresář je zásadní pro organizaci a správu obrázků čárových kódů.

```java
// Cesta k adresáři prostředků.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Krok 2: Vytvořte sbírku čárových kódů

Inicializujte HashMap pro uložení dat čárového kódu. Každý záznam v kolekci představuje čárový kód s příslušným typem kódování.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Krok 3: Vygenerujte obrázky čárových kódů

Procházejte kolekci a generujte obrázky čárových kódů pomocí knihovny Aspose.BarCode. Uložte obrázky do ArrayList pro další zpracování.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Krok 4: Vytvořte kombinovaný obrázek

Určete maximální šířku a celkovou výšku obrázků čárových kódů. Vytvořte BufferedImage pro spojení jednotlivých obrázků čárových kódů do jednoho výstupního obrázku.

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
## Krok 5: Uložte výsledek

Uložte konečný kombinovaný obrázek do určeného umístění souboru.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Závěr

Gratulujeme! Úspěšně jste vygenerovali více čárových kódů na jednom obrázku pomocí Aspose.BarCode for Java. Tato výkonná knihovna zjednodušuje manipulaci s čárovými kódy, což z ní činí neocenitelný nástroj pro vývojáře v jazyce Java.

## FAQ

### Q1: Mohu upravit vzhled jednotlivých čárových kódů ve vygenerovaném obrázku?

Odpověď 1: Ano, Aspose.BarCode poskytuje rozsáhlé možnosti přizpůsobení vzhledu čárového kódu, což vám umožňuje přizpůsobit styl každého čárového kódu vašim preferencím.

### Q2: Je Aspose.BarCode kompatibilní s různými symboliky čárových kódů?

A2: Rozhodně! Aspose.BarCode podporuje širokou škálu symbologií, včetně CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 a AZTEC, jak je ukázáno v tomto tutoriálu.

### Q3: Jak mohu integrovat Aspose.BarCode do mého projektu Java?

 A3: Jednoduše si stáhněte knihovnu Aspose.BarCode for Java[tady](https://releases.aspose.com/barcode/java/) a postupujte podle pokynů k instalaci uvedených v dokumentaci.

### Q4: Mohu použít Aspose.BarCode pro komerční aplikace?

 A4: Ano, můžete získat licenci od[tady](https://purchase.aspose.com/buy) používat Aspose.BarCode pro komerční účely.

### Q5: Jsou k dispozici nějaké zkušební možnosti pro Aspose.BarCode?

 A5: Určitě! Můžete prozkoumat funkce Aspose.BarCode získáním bezplatné zkušební licence[tady](https://releases.aspose.com/).